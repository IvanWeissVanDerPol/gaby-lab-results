# gaby-lab-results

Registro longitudinal estructurado de los estudios médicos de **Gabriella Maria Gonzalez Pane** (CI 1375421, 45F), incluyendo laboratorio, imagenología, y material educativo/de consulta médica.

> ⚠️ **Esto NO es un archivo médico formal.** Es un repositorio personal-familiar para organizar, entender, y discutir los estudios con los médicos tratantes. Las decisiones clínicas las toman los profesionales con contexto completo del paciente.

---

## 📚 Tabla de contenidos

- [Main files — links directos](#-main-files--links-directos)
- [¿Qué hay aquí?](#qué-hay-aquí)
- [Estado de los estudios](#estado-de-los-estudios)
- [Cómo usar este repo](#cómo-usar-este-repo)
- [Hallazgos principales (resumen ejecutivo)](#hallazgos-principales-resumen-ejecutivo)
- [Estructura del repo](#estructura-del-repo)
- [Estado del proyecto](#estado-del-proyecto)
- [Privacidad y exposición pública](#privacidad-y-exposición-pública)
- [Cómo contribuir / mantener](#cómo-contribuir--mantener)
- [Referencias externas y fuentes](#referencias-externas-y-fuentes)

---

## 🔗 Main files — links directos

Todos los archivos importantes del repo, agrupados por uso. Los links son a GitHub (`github.com/IvanWeissVanDerPol/gaby-lab-results/...`) — funcionan tanto en local como en la web.

### 📄 Resúmenes por estudio (lo primero a abrir)

| Estudio | Resumen | Datos CSV |
|---|---|---|
| **TC abdomen+pelvis sin contraste** (17/08/26) | [summary.md](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/assessments/2026-08-17-ct-abdomen-pelvis-sin-contraste/summary.md) | — |
| **TC abdomen+pelvis con contraste** (18/08/26) | [summary.md](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/assessments/2026-08-18-ct-abdomen-pelvis-con-contraste/summary.md) | — |
| **Orina completa (rutina)** (24/08/26) | [summary.md](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/assessments/2026-08-24-orina-completa/summary.md) | [biomarkers.csv](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/assessments/2026-08-24-orina-completa/biomarkers.csv) |
| **Panel general de sangre** (26/08/26) | [summary.md](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/assessments/2026-08-26-perfil-completo-sangre/summary.md) | [biomarkers.csv](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/assessments/2026-08-26-perfil-completo-sangre/biomarkers.csv) |

### 🩺 Material para consulta médica (doctor/)

| Archivo | Para qué sirve |
|---|---|
| [**one-pager-imprimir.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/doctor/one-pager-imprimir.md) | Una página con todo. **Imprimir y llevar al médico.** |
| [**preguntas-para-Dr-Sachero.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/doctor/preguntas-para-Dr-Sachero.md) | 8 preguntas priorizadas para la consulta con el clínico (panel de sangre) |
| [**resumen-para-Dr-Novais.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/doctor/resumen-para-Dr-Novais.md) | Material específico para discutir las tomografías con el radiólogo |
| [**timeline-visual.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/doctor/timeline-visual.md) | Línea de tiempo ASCII de los 4 estudios |
| [README.md](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/doctor/README.md) | Índice del directorio |

### 📊 Datos estructurados (CSV + LOINC)

| Archivo | Qué contiene |
|---|---|
| [**biomarkers/blood-work.csv**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/biomarkers/blood-work.csv) | **El dataset maestro.** 62 filas long-format con TODOS los tests de sangre y orina, cada uno con su LOINC, UCUM, status, panel, y visit_id. |
| [**biomarkers/imaging.csv**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/biomarkers/imaging.csv) | Las 2 tomografías estructuradas (fecha, modalidad, contraste, hallazgos, path al PDF) |
| [**loinc/README.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/loinc/README.md) | Mapping LOINC + UCUM para todos los tests que aparecen en los estudios |

### 📚 Referencias educativas (qué significa cada resultado)

| Archivo | Qué contiene |
|---|---|
| [**references/biomarkers-reference.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/references/biomarkers-reference.md) | Guía en español de cada biomarcador: qué mide, rango LA COSTA, valor de Gabriella, qué significa bajo/alto. Con cross-reference a guías clínicas (ADA, AHA, ATA, KDIGO). |
| [**references/ct-findings-glossary.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/references/ct-findings-glossary.md) | Glosario de los términos radiológicos de las tomografías (quiste hemorrágico, Bosniak, islotes óseos, Hounsfield, etc.) |

### 📑 PDFs originales

Los 4 PDFs sin modificar, organizados por SHA-1 + admisión + fecha:

| Estudio | Link al PDF | Hash SHA-1 |
|---|---|---|
| TC abdomen+pelvis sin contraste (17/08/26) | [606c25f8...pdf](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/original_files/606c25f849c4de79_8702431_ct_2026-08-17.pdf) | `606c25f849c4de79` |
| TC abdomen+pelvis con contraste (18/08/26) | [fe3f7f01...pdf](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/original_files/fe3f7f011060862f_8708526_ct_2026-08-18.pdf) | `fe3f7f011060862f` |
| Análisis de orina (24/08/26) | [08fb1982...pdf](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/original_files/08fb19821c5b70be_4436979_orina_2026-08-24.pdf) | `08fb19821c5b70be` |
| Panel general de sangre (26/08/26) | [947a8817...pdf](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/original_files/947a8817b7cf281e_4437614_panel_2026-08-26.pdf) | `947a8817b7cf281e` |

### 🛠 Documentación técnica (para agentes / contributors)

| Archivo | Para qué sirve |
|---|---|
| [**CLAUDE.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/CLAUDE.md) | Instrucciones para Claude / Hermes / agentes que abran este repo |
| [**docs/DATA-FORMATS.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/docs/DATA-FORMATS.md) | Esquema canónico de todos los CSV / JSON / naming conventions |
| [**archive_owner.json**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/archive_owner.json) | Identidad del paciente — single source of truth |
| [**original_files/README.md**](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/original_files/README.md) | Por qué los PDFs usan SHA-1 en el nombre, y tabla de hashes |
| [LICENSE](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/LICENSE) | Nota sobre datos del paciente no reutilizables |

### 🗄 Legacy (mantenido por valor histórico)

| Archivo | Notas |
|---|---|
| [legacy_lab-extract-orina-2026-08-24.md](https://github.com/IvanWeissVanDerPol/gaby-lab-results/blob/hermes/improvements/legacy_lab-extract-orina-2026-08-24.md) | Extract markdown crudo original de la orina, antes de la migración al esquema estructurado |

---

## ¿Qué hay aquí?

4 estudios médicos del 17 al 26 de agosto de 2026, organizados cronológicamente con resúmenes en español, datos estructurados (CSV + LOINC), material educativo, y documentos preparados para consulta médica.

### Estudios individuales

| Fecha | Tipo | Resumen |
|---|---|---|
| **17/08/26** | TC abdomen+pelvis sin contraste | [summary](assessments/2026-08-17-ct-abdomen-pelvis-sin-contraste/summary.md) |
| **18/08/26** | TC abdomen+pelvis con contraste | [summary](assessments/2026-08-18-ct-abdomen-pelvis-con-contraste/summary.md) |
| **24/08/26** | Orina completa (rutina) | [summary](assessments/2026-08-24-orina-completa/summary.md) |
| **26/08/26** | Panel general de sangre | [summary](assessments/2026-08-26-perfil-completo-sangre/summary.md) |

---

## Estado de los estudios

### ✅ Completado (P0–P4 de la primera iteración)

- [x] Higiene del repo: duplicados eliminados, archivos renombrados correctamente
- [x] CSV maestro de biomarcadores con todos los tests mapeados a LOINC
- [x] CSV de imagenología con las 2 tomografías estructuradas
- [x] Mapeo LOINC para todos los tests
- [x] Glosario en español de biomarcadores y hallazgos radiológicos
- [x] Material de preparación para consulta médica (4 documentos)

### 🟡 Pendiente

- [ ] Mover PDFs originales de la raíz a `original_files/` con naming SHA-1
- [ ] Implementar scripts de validación (`scripts/validate_biomarkers.py`, etc.)
- [ ] Dashboard web (Chart.js) para visualizar tendencias
- [ ] Exportador FHIR R4 Bundle (para portabilidad entre sistemas)
- [ ] MCP server (`gaby-lab-mcp`) para que agentes consulten los datos conversacionalmente
- [ ] Cuestionario de seguimiento (estudios pendientes sugeridos)
- [ ] Versión PDF imprimible de `doctor/one-pager-imprimir.md`

---

## Cómo usar este repo

### Si sos Gabriella o su familia

→ Empezá por [**doctor/one-pager-imprimir.md**](doctor/one-pager-imprimir.md). Es la página única para imprimir y llevar al médico.

Después: [**doctor/timeline-visual.md**](doctor/timeline-visual.md) te da la secuencia de los 4 estudios en orden.

### Si sos médico tratante

→ Encontrarás todo lo relevante en `doctor/`:

- `preguntas-para-Dr-Sachero.md` — preguntas específicas sobre el panel de sangre
- `resumen-para-Dr-Novais.md` — material sobre las tomografías
- `one-pager-imprimir.md` — resumen de una página

### Si sos un agente / Claude Code / Hermes

→ Leé primero [**CLAUDE.md**](CLAUDE.md) para las convenciones del repo, después [**docs/DATA-FORMATS.md**](docs/DATA-FORMATS.md) para los esquemas canónicos.

### Si querés entender un valor específico

→ Buscá el test en [**references/biomarkers-reference.md**](references/biomarkers-reference.md) (lípidos, hematología, química, etc.) o [**references/ct-findings-glossary.md**](references/ct-findings-glossary.md) (términos radiológicos).

### Si querés los datos crudos para análisis

→ Los CSVs están en:

- `biomarkers/blood-work.csv` — todos los resultados de laboratorio en formato long
- `biomarkers/imaging.csv` — todos los estudios de imagen
- `loinc/README.md` — mapping LOINC + UCUM

---

## Hallazgos principales (resumen ejecutivo)

> **Contexto**: Gabriella tuvo una infección urinaria que no respondió al antibiótico inicial. Los estudios para investigar la causa revelaron **incidentalmente** hallazgos renales, pancreáticos y óseos que requieren seguimiento pero que — en su mayoría — son benignos o de muy bajo riesgo. **Ningún hallazgo actual sugiere malignidad.**

### Lo que requiere seguimiento

1. **Quiste hemorrágico renal izquierdo 30 mm** (Bosniak II probable) — control de imagen en 3–6 meses
2. **Quiste pancreático 6 mm** (incidentaloma, muy bajo riesgo por tamaño) — control según criterios de Fukuoka
3. **Islotes óseos pélvicos** (enostosis) — solo si son nuevos respecto a estudios previos
4. **Plaquetas elevadas (575 K/mm3)** — repetir hemograma en 4–6 semanas (probable trombocitosis reactiva a ITU)
5. **Dislipidemia** (LDL 165, No-HDL 180; HDL 66 protector) — evaluar riesgo CV a 10 años
6. **Vitamina D insuficiente (29.35 ng/mL)** — suplementación a considerar
7. **Insulina basal borderline (HOMA-IR 2.94)** — posible resistencia a insulina incipiente

### Lo que está normal

- Glóbulos blancos, hemoglobina (límite), creatinina, función hepática, tiroides, ESR
- Sin infección urinaria activa en el estudio de orina
- Sin realce en la lesión renal → muy tranquilizador (descarta tumor sólido)
- Sin metástasis, líquido libre, adenopatías, obstrucción

---

## Estructura del repo

```
gaby-lab-results/
├── README.md                              ← este archivo (entrada)
├── CLAUDE.md                              ← instrucciones para agentes
├── LICENSE
├── .gitignore
├── archive_owner.json                     ← identidad del paciente (single source of truth)
│
├── original_files/                        ← PDFs sin modificar, organizados por hash
│   └── README.md
│
├── biomarkers/                            ← datos estructurados
│   ├── blood-work.csv                     ← todos los labs (long format)
│   └── imaging.csv                        ← todas las imágenes
│
├── loinc/                                 ← mapping LOINC + UCUM
│   └── README.md
│
├── assessments/                           ← un directorio por estudio mayor
│   ├── 2026-08-17-ct-abdomen-pelvis-sin-contraste/
│   │   ├── summary.md
│   │   └── raw/Pac8702431_GABRIELLA.pdf
│   ├── 2026-08-18-ct-abdomen-pelvis-con-contraste/
│   │   ├── summary.md
│   │   └── raw/Pac8708526_GABRIELLA.pdf
│   ├── 2026-08-24-orina-completa/
│   │   ├── summary.md
│   │   ├── biomarkers.csv
│   │   └── raw/
│   └── 2026-08-26-perfil-completo-sangre/
│       ├── summary.md
│       ├── biomarkers.csv
│       └── raw/
│
├── doctor/                                ← material de preparación para consulta
│   ├── README.md
│   ├── one-pager-imprimir.md              ← IMPRIMIR Y LLEVAR
│   ├── preguntas-para-Dr-Sachero.md
│   ├── resumen-para-Dr-Novais.md
│   └── timeline-visual.md
│
├── references/                            ← educación (NO consejo médico)
│   ├── biomarkers-reference.md            ← cada test explicado en español
│   └── ct-findings-glossary.md            ← términos radiológicos explicados
│
├── docs/                                  ← documentación técnica del repo
│   └── DATA-FORMATS.md                    ← esquema canónico CSV/JSON
│
├── scripts/                               ← (futuro) herramientas de mantenimiento
│
├── patient_info.md                        ← legacy: nota clínica del usuario
├── lab_result_2_aug24_2026.md             ← legacy: extract markdown del panel de orina
│
└── (legacy PDFs raíz, a mover a original_files/)...
```

---

## Estado del proyecto

| Fase | Estado | Notas |
|---|---|---|
| **P0** Higiene | ✅ | Duplicado PDF eliminado, archivo mal titulado removido |
| **P1** CSV biomarkers | ✅ | `biomarkers/blood-work.csv` (62 filas) + `biomarkers/imaging.csv` (2 filas) |
| **P2** Mapping LOINC | ✅ | `loinc/README.md` con códigos para todos los tests realizados |
| **P3** Referencias educativas | ✅ | `references/biomarkers-reference.md` + `ct-findings-glossary.md` |
| **P4** Preparación médica | ✅ | 4 documentos en `doctor/` |
| **P5** Schema canónico | ✅ | `docs/DATA-FORMATS.md` |
| **P6** Archive owner | ✅ | `archive_owner.json` (single source of truth de identidad) |
| **P7** Claude instructions | ✅ | `CLAUDE.md` |
| **P8** Gitignore | ✅ | Excluye temporales, DB, crosswalks sensibles |
| **P9** Mover PDFs a original_files | ✅ | SHA-1 prefix naming, 4 PDFs en `original_files/` + copia en cada `assessments/{date}/raw/` |
| **P10** Scripts validación | 🔴 | No implementados |
| **P11** Dashboard web | 🔴 | No implementado |
| **P12** FHIR R4 export | 🔴 | No implementado |
| **P13** MCP server | 🔴 | No implementado |

✅ = hecho · 🟡 = pendiente próximo · 🔴 = futuro

---

## Privacidad y exposición pública

**Este repositorio es público por decisión del owner del repo (IvanWeissVanDerPol).** La paciente fue notificada.

Datos identificantes incluidos:

- Nombre completo: Gabriella Maria Gonzalez Pane
- CI (cédula): 1375421
- Fecha de nacimiento: 26/05/1981

**NO** se incluyen (a propósito):

- Dirección
- Teléfono
- Email
- Número de historia clínica
- Fotos
- Información de seguros médicos

Ver `archive_owner.json` para el manejo del campo CI. Si en algún momento se exportan datos fuera del repo (ej. FHIR Bundle), el CI debe seudonimizarse a `urn:uuid:...`.

---

## Cómo contribuir / mantener

### Agregar un estudio nuevo

1. Subir PDF al repo (temporal en la raíz)
2. Extraer texto con `pypdf` (no requiere poppler)
3. Verificar identidad contra `archive_owner.json`
4. Calcular SHA-1 → si existe, abortar (duplicado)
5. Renombrar PDF con convención `{sha1[:16]}_{admisión}_{tipo}_{YYYY-MM-DD}.pdf`
6. Crear carpeta `assessments/YYYY-MM-DD-descripcion/` con `summary.md`, `biomarkers.csv`, y `raw/`
7. Insertar filas en `biomarkers/blood-work.csv` (laboratorio) o `biomarkers/imaging.csv` (imagen)
8. Actualizar tabla "Estado de los estudios" en este README
9. Si el hallazgo es nuevo → agregar a `references/` (educación) y `doctor/` (preguntas)
10. Commit con mensaje descriptivo + branch + PR

### Convenciones

Ver [`CLAUDE.md`](CLAUDE.md) para reglas completas y [`docs/DATA-FORMATS.md`](docs/DATA-FORMATS.md) para el esquema CSV.

---

## Referencias externas y fuentes

### Repos de referencia (patrones levantados)

- [mslavov/personal-health-template](https://github.com/mslavov/personal-health-template) — CSV schema + folder layout
- [rom4lk/personal-health-record](https://github.com/rom4lk/personal-health-record) — 3-layer archive + dedup + identity check
- [terravic/lab-report-to-fhir-skill](https://github.com/terravic/lab-report-to-fhir-skill) — LOINC + FHIR R4 mapping
- [daveremy/function-health-mcp](https://github.com/daveremy/function-health-mcp) — MCP tool surface
- [markwk/awesome-biomarkers](https://github.com/markwk/awesome-biomarkers) — lista curada de biomarcadores

### Guías clínicas citadas

- **ADA Standards of Care 2023** — Diabetes mellitus (criterios de glucosa/A1c)
- **AHA/ACC 2018** — Manejo de colesterol en sangre (criterios de LDL/No-HDL)
- **ATA Guidelines** — Tiroides (rangos de TSH)
- **Endocrine Society** — Vitamina D (cortes de 20/30/100 ng/mL)
- **KDIGO 2012** — Función renal (creatinina, eGFR)
- **Bosniak Classification** — Quistes renales (I, II, IIF, III, IV)
- **Fukuoka Guidelines / ACR White Paper** — Quistes pancreáticos

---

*Última actualización: 28 de agosto de 2026*