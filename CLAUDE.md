# CLAUDE.md — Instrucciones para Claude / Hermes en este repo

> Este archivo se inyecta automáticamente cuando un agente Claude (Claude Code, Hermes) abre este repo. Define cómo trabajar aquí.

## Identidad del paciente

Antes de cualquier operación, **verificar la identidad del paciente**:

1. Leer `archive_owner.json`
2. Confirmar que cualquier PDF nuevo tiene el mismo nombre + CI + fecha de nacimiento
3. Si NO coincide → **detener y preguntar al owner** antes de procesar

```
Patient: Gabriella Maria Gonzalez Pane
CI: 1375421
DOB: 1981-05-26
```

## Stack técnico permitido

- **Python 3.11+** para scripts
- **SQLite** para base de datos local (cuando se implemente)
- **CSV plano** para todos los datos de biomarcadores (no JSON, no YAML)
- **Markdown** para documentación
- **NO** usar: bases de datos remotas, APIs externas con PHI, dependencias cloud

## Esquema canónico

Ver `docs/DATA-FORMATS.md`. Cualquier CSV nuevo debe cumplir ese esquema.

## Convenciones de naming

- **Carpetas de assessment**: `YYYY-MM-DD-descripcion-corta-en-espaol-kebab-case`
- **LOINC**: código numérico `XXX-X` o `XXXXX-X` (sin prefijo `LOINC:`)
- **status**: enum fijo (`Optimal`, `Normal`, `Borderline`, `Low`, `High`, `NA`)
- **Fechas**: siempre ISO `YYYY-MM-DD`
- **Unidades**: UCUM cuando aplique (`mg/dL`, `mmol/L`, `K/mm3`, etc.)

## Flujo de trabajo — agregar un estudio nuevo

```
1. Subir PDF a la raíz (temporal)
2. pypdf extract → texto crudo
3. Verificar identidad contra archive_owner.json
4. Calcular SHA-1 → si duplicado, abortar
5. Crear assessments/YYYY-MM-DD-descripcion/
   ├── summary.md
   ├── biomarkers.csv
   └── raw/Pac*.pdf
6. Insertar filas en biomarkers/blood-work.csv o imaging.csv
7. Actualizar README.md status table
8. Commit con mensaje descriptivo
9. Push
```

## Privacidad

- **El repo es público por decisión del owner.** Mantener este nivel de exposición.
- **NO** agregar nuevos campos de identificación sin consultar al owner (teléfono, dirección, email, número de historia clínica)
- **El CI (cédula) ya está en el repo.** Si se exporta FHIR Bundle fuera del repo → seudonimizar
- **NO** incluir en commits:
  - Claves de API
  - URLs internas con tokens
  - Screenshots de conversaciones con médicos

## Lenguaje

- **Español** para toda la documentación, README, doctor/, references/, summaries
- **Inglés** solo para LOINC + UCUM + nombres técnicos que no tienen buena traducción (ej. "Bosniak", "Fukuoka criteria")
- **CSV headers**: en inglés (son el estándar de facto para join con herramientas externas)

## Lo que NO hacer

- ❌ No inventar valores que no están en los PDFs
- ❌ No diagnosticar ("esto es cáncer", "esto es diabetes")
- ❌ No recomendar medicamentos ni dosis
- ❌ No traducir nombres propios de tests que el laboratorio usa en español
- ❌ No crear archivos nuevos sin actualizar README.md + STATUS
- ❌ No borrar `archive_owner.json`
- ❌ No commit a master directamente — usar branch + PR

## Cómo verificar que hiciste bien el trabajo

```bash
# 1. Validar CSV (futuro script)
python3 scripts/validate_biomarkers.py

# 2. Validar LOINC mapping
python3 scripts/validate_loinc.py

# 3. Verificar que README.md status table está al día
grep "✅\|❌\|🟡" README.md

# 4. Listar archivos modificados
git status
```

## Skills y referencias externas

Este repo sigue patrones de:
- `mslavov/personal-health-template` (CSV schema + folder layout)
- `rom4lk/personal-health-record` (3-layer archive + dedup + identity check)
- `terravic/lab-report-to-fhir-skill` (LOINC + FHIR R4 mapping)
- `daveremy/function-health-mcp` (MCP tool surface — futuro)

Ver `docs/ARCHITECTURE.md` para más detalle.