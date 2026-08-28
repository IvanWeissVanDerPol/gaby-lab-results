# Data formats — Schema canónico

Este documento define los formatos de archivo canónicos para todos los datos del repositorio. Cualquier script, dashboard, o importador debe respetar estos esquemas.

## Filosofía

- **CSV plano**: máxima portabilidad, editables en Excel/Google Sheets
- **Una fila = un dato**: estilo "long format" — cada fila es una observación (no una matriz)
- **Identificadores estables**: `visit_id` y `loinc` permiten joins entre archivos
- **Status automático**: valores fuera de rango se marcan automáticamente pero la verdad siempre es el `value` crudo
- **Sin datos derivados en CSV**: las columnas calculadas (HOMA-IR, Bosniak score) viven en `references/` o se calculan al vuelo

---

## `biomarkers/blood-work.csv`

Esquema long-format para todos los resultados de laboratorio.

| Columna | Tipo | Ejemplo | Requerido | Notas |
|---|---|---|---|---|
| `date` | ISO date | 2026-08-26 | Sí | YYYY-MM-DD |
| `test_name` | string | "Colesterol Total" | Sí | Español, exactamente como aparece en el PDF |
| `value` | numeric o string | "246" o "No reactivo" | Sí | El valor crudo del laboratorio |
| `unit` | string | "mg/dL" o "" | Sí | Vacío para "No reactivo" |
| `reference_low` | numeric o string | 0 o "" | Sí | Vacío para "No reactivo" |
| `reference_high` | numeric o string | 200 o "" | Sí | Vacío para "No reactivo" |
| `lab` | string | "Centro Médico LA COSTA" | Sí | |
| `status` | enum | "Normal" / "High" / "Low" / "Borderline" / "Optimal" | Sí | Calculado por el script de ingesta vs `reference_low`/`reference_high` |
| `notes` | string | "Justo bajo 30 (deseable)" | No | Observaciones contextuales |
| `visit_id` | slug | "panel_2026-08-26" | Sí | Identificador del estudio/visita |
| `loinc` | string | "2093-3" | Sí | Código LOINC (ver `loinc/README.md`) |
| `panel` | enum | "lipids" / "chemistry" / "hematology" / "urinalysis" / "thyroid" / "immunology" | Sí | Para filtrar |

### `status` — reglas

- `Optimal`: dentro del rango y/o en el rango AHA/ADA "deseable" cuando difiere del rango del lab
- `Normal`: dentro del rango del laboratorio, sin punto de corte clínico diferente
- `Borderline`: dentro del rango del laboratorio pero cerca del límite, o en zona "insuficiente"/"límite" según guías
- `Low` / `High`: fuera del rango del laboratorio
- `NA`: solo para tests donde el rango no aplica (ej. "No reactivo")

### Ejemplo válido

```csv
date,test_name,value,unit,reference_low,reference_high,lab,status,notes,visit_id,loinc,panel
2026-08-26,Colesterol Total,246,mg/dL,0,200,Centro Médico LA COSTA,High,Límite AHA: ≥240 = Alto,panel_2026-08-26,2093-3,lipids
```

---

## `biomarkers/imaging.csv`

Una fila por estudio de imagenología.

| Columna | Tipo | Ejemplo | Notas |
|---|---|---|---|
| `date` | ISO date | 2026-08-18 | Fecha de realización |
| `study_type` | string | "CT" | |
| `body_region` | string | "Abdomen+Pelvis" | |
| `modality` | string | "Tomografía Computada Helicoidal" | |
| `contrast` | string | "Con contraste e.v. + oral negativo" | O "Ninguno" |
| `facility` | string | "Centro Médico LA COSTA" | |
| `radiologist` | string | "Dra. Carolina Servin (R.P. 6156)" | |
| `ordering_physician` | string | "Dr. Novais Peña Jose Maria" | |
| `reason` | string | "Evaluación de nódulos en riñón izquierdo" | |
| `findings_count` | int | 4 | Número de hallazgos separados |
| `impression` | string | "Formación nodular..." | Texto resumido |
| `recommendation` | string | "Seguimiento según criterio clínico" | |
| `raw_file` | string | "Pac8708526_GABRIELLA.pdf" | Path relativo al PDF original |

---

## `assessments/YYYY-MM-DD-description/`

Cada estudio mayor (panel, TC, consulta externa) vive en su propia carpeta.

```
assessments/
├── 2026-08-17-ct-abdomen-pelvis-sin-contraste/
│   ├── summary.md          ← resumen narrativo en español
│   ├── biomarkers.csv      ← versión por-visita del blood-work general (subset)
│   ├── findings.json       ← hallazgos estructurados (cuando aplique)
│   └── raw/                ← PDF original sin modificar
│       └── Pac8702431_GABRIELLA.pdf
└── 2026-08-26-perfil-completo-sangre/
    ├── summary.md
    ├── biomarkers.csv
    └── raw/
        └── resultado_gonzalez_pane_gabriella_maria_4437614_26082026095518_lc.pdf
```

### Naming convention

- `YYYY-MM-DD`: fecha del estudio (no de carga al repo)
- Después del guión: descripción corta kebab-case, en español
- 80 caracteres max para el nombre completo

### `summary.md` template

```markdown
# Resumen: [fecha] — [tipo de estudio]

**Paciente**: Gabriella Maria Gonzalez Pane (CI 1375421)
**Centro**: Centro Médico LA COSTA
**Solicitado por**: Dr(a). [nombre]
**Validado por**: [bioquímicos si aplica]

## Hallazgos principales

1. [Hallazgo 1]
2. [Hallazgo 2]

## Valores fuera de rango

| Test | Valor | Rango | Status |
|---|---|---|---|

## Diagnóstico / impresión

[texto del médico]

## Recomendación

[texto del médico]

## Ver también

- [link al otro assessment relacionado]
- [link al biomarker CSV]
- [link a references/]
```

---

## `loinc/README.md` y sub-tablas

Mapping de cada test de Gabriella a LOINC + UCUM. Ver `loinc/README.md` para el esquema completo.

- Cada test debe tener: LOINC + UCUM + descripción en español + descripción en inglés
- Sub-tablas por categoría (chemistry, hematology, lipids, thyroid, immunology, urinalysis)
- Si un test nuevo no tiene LOINC conocido, marcar como `PENDIENTE` y buscar en loinc.org antes de cerrar el assessment

---

## `references/biomarkers-reference.md` y `references/ct-findings-glossary.md`

Documentos educativos en español. Estructura por biomarcador:

```
### [Nombre del test] — LOINC [código]
- **Qué mide**: ...
- **Rango LA COSTA**: ...
- **Gabriella**: ... (valor + comentario contextual)
- **Bajo**: ...
- **Alto**: ...
```

---

## `doctor/*.md`

Documentos de cara a la familia y los médicos. Cada uno tiene su propio propósito (ver `doctor/README.md`).

---

## `archive_owner.json`

Ver `original_files/README.md` para el esquema completo. Es la **única** fuente de verdad para la identidad de Gabriella.

```json
{
  "patient": {
    "full_name": "Gabriella Maria Gonzalez Pane",
    "ci": "1375421",
    "dob": "1981-05-26",
    "sex": "F"
  },
  "repository_owner": "IvanWeissVanDerPol",
  "relationship": "familiar",
  "consent": "public",
  "last_verified": "2026-08-28"
}
```

---

## Versioning del esquema

Cambios incompatibles al esquema CSV → bumpear `biomarkers/SCHEMA_VERSION` y documentar en `docs/CHANGELOG.md`.

Cambios compatibles (nuevas columnas, nuevos valores `status`) → solo changelog.

## Scripts de validación

Pendientes en `scripts/`:
- `validate_biomarkers.py` — verifica que todas las filas cumplen el esquema
- `validate_loinc.py` — verifica que cada `loinc` está en el mapping canónico
- `dedup_visits.py` — verifica que no hay visit_ids duplicados