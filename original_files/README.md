# Original files — naming y dedup

Esta carpeta contiene los PDFs originales **sin modificar**, organizados por hash SHA-1.

> **Regla de oro**: nunca modificar, renombrar, ni regenerar un archivo en `original_files/`. Si necesitás una versión procesada (sin metadatos, etc.), guardala en `original_files/redacted/` con nombre diferente.

## Naming convention

```
{sha1[:16]}_{study_id}_{study_type}_{YYYY-MM-DD}.pdf
```

Donde:
- `sha1[:16]`: primeros 16 caracteres del SHA-1 del archivo (suficiente para deduplicación)
- `study_id`: admisión del paciente (ej. `8702431`, `4437614`, `4436979`) o `panel` para análisis múltiples
- `study_type`: `ct`, `orina`, `panel`, `varios`
- `YYYY-MM-DD`: fecha del estudio (no de carga)

## Estado actual

| Hash SHA-1 (primeros 16) | Hash SHA-1 completo | Admisión | Estudio | Destino |
|---|---|---|---|---|
| `606c25f849c4de79` | `606c25f849c4de794d26f44a3fdcca79e91e836e` | 8702431 | TC abdomen+pelvis sin contraste | `606c25f849c4de79_8702431_ct_2026-08-17.pdf` |
| `fe3f7f011060862f` | `fe3f7f011060862f8082b7eef7cca9818025e807` | 8708526 | TC abdomen+pelvis con contraste | `fe3f7f011060862f_8708526_ct_2026-08-18.pdf` |
| `08fb19821c5b70be` | `08fb19821c5b70bec52e854736e029c86daab5d8` | 4436979 | Análisis de orina (rutina) | `08fb19821c5b70be_4436979_orina_2026-08-24.pdf` |
| `947a8817b7cf281e` | `947a8817b7cf281e2194167e41bbf0bbed10c5fa` | 4437614 | Panel general de sangre | `947a8817b7cf281e_4437614_panel_2026-08-26.pdf` |

**Verificación**: `find original_files/ -type f -name '*.pdf' | xargs sha1sum` debe coincidir con los hashes de arriba.

## Por qué SHA-1

- Inmutable: si el archivo cambia 1 byte, el hash cambia
- Identifica duplicados exactos sin abrir el archivo
- 16 caracteres hex = 64 bits → probabilidad de colisión aceptable para una colección personal
- Si crece a >1000 archivos, considerar SHA-256 + colisiones mucho más improbables

## Por qué NO usar el nombre del paciente

- **Privacidad**: el path del archivo es público si el repo es público
- **Estabilidad**: si el paciente cambia de nombre (matrimonio, etc.), los archivos no se invalidan
- **Deduplicación**: dos archivos del mismo estudio son idénticos byte-a-byte solo si el SHA-1 coincide

## Flujo de ingestión nuevo

1. Subir PDF → calcular SHA-1
2. Si el SHA-1 ya existe en `original_files/` → **rechazar** (duplicado)
3. Si no existe → renombrar con la convención, mover a `original_files/`
4. Crear/actualizar `json_extractions/{hash}.json` con la extracción estructurada
5. Insertar/actualizar filas en `biomarkers/blood-work.csv` o `biomarkers/imaging.csv`
6. Crear/actualizar carpeta `assessments/YYYY-MM-DD-description/` con `summary.md` y `raw/{renombrado}.pdf`

## Cross-reference

- **Identidad del paciente**: `archive_owner.json` (única fuente de verdad)
- **Esquema de metadatos**: `docs/DATA-FORMATS.md`
- **Mapping LOINC**: `loinc/README.md`