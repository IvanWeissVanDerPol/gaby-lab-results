# LOINC — Mapeo de tests para Gabriella Maria Gonzalez Pane

Mapeo LOINC + UCUM para todos los tests que aparecen en los estudios de Gabriella. Los códigos LOINC son la lingua franca internacional para análisis clínicos — cualquier software de salud puede ingerir estos datos con precisión.

## Fuentes

- LOINC release DB (loinc.org)
- `terravic/lab-report-to-fhir-skill` references/loinc_snomed_mapping.md
- `Centro Médico LA COSTA` panel impreso (referencia local del laboratorio)

## Hematología

| Test (es) | Test (en) | LOINC | UCUM unit | Panel LA COSTA |
|---|---|---|---|---|
| Glóbulos Rojos | Erythrocytes | 789-8 | {cells}/uL | Hemograma |
| Glóbulos Blancos | Leukocytes | 6690-2 | {cells}/uL | Hemograma |
| Hemoglobina | Hemoglobin | 718-7 | g/dL | Hemograma |
| Hematocrito | Hematocrit | 4544-3 | % | Hemograma |
| VCM | MCV | 787-2 | fL | Índices hematimétricos |
| HCM | MCH | 785-6 | pg | Índices hematimétricos |
| CHCM | MCHC | 786-4 | g/dL | Índices hematimétricos |
| RDW-CV | RDW | 788-0 | % | Índices hematimétricos |
| Neutrófilos Segmentados % | Neutrophils % | 770-8 | % | Fórmula leucocitaria |
| Neutrófilos Segmentados abs | Neutrophils # | 751-8 | {cells}/uL | Fórmula leucocitaria |
| Linfocitos % | Lymphocytes % | 731-0 | % | Fórmula leucocitaria |
| Linfocitos abs | Lymphocytes # | 850-8 | {cells}/uL | Fórmula leucocitaria |
| Monocitos % | Monocytes % | 742-7 | % | Fórmula leucocitaria |
| Monocitos abs | Monocytes # | 743-5 | {cells}/uL | Fórmula leucocitaria |
| Eosinófilos % | Eosinophils % | 713-8 | % | Fórmula leucocitaria |
| Eosinófilos abs | Eosinophils # | 711-2 | {cells}/uL | Fórmula leucocitaria |
| Recuento de Plaquetas | Platelets | 777-3 | {cells}/uL | Hemograma |
| MPV | MPV | 32623-1 | fL | Índices hematimétricos |
| Eritrosedimentación 1ra hora | ESR | 4537-7 | mm/h | Hematología |

## Química clínica

| Test (es) | Test (en) | LOINC | UCUM unit |
|---|---|---|---|
| Sodio | Sodium | 2951-2 | mmol/L |
| Potasio | Potassium | 2823-3 | mmol/L |
| Cloruros | Chloride | 2075-0 | mmol/L |
| Calcio | Calcium | 2000-8 | mg/dL |
| Fósforo | Phosphorus | 2777-1 | mg/dL |
| Magnesio | Magnesium | 19123-9 | mg/dL |
| Glucosa | Glucose | 2345-7 | mg/dL |
| Urea | Urea | 3091-6 | mg/dL |
| Creatinina | Creatinine | 2160-0 | mg/dL |
| Ácido Úrico | Uric acid | 3084-1 | mg/dL |
| Fosfatasa Alcalina | Alkaline phosphatase | 6768-6 | U/L |
| Bilirrubina Total | Total bilirubin | 1975-2 | mg/dL |
| Bilirrubina Directa | Direct bilirubin | 1971-1 | mg/dL |
| Bilirrubina Indirecta | Indirect bilirubin | 1971-1 (calc) | mg/dL |
| ALT/GPT | ALT | 1742-6 | U/L |
| AST/GOT | AST | 1920-8 | U/L |
| Gamma GT | GGT | 2324-2 | U/L |
| Hemoglobina Glicada (HbA1c) | HbA1c | 4548-4 | % |
| Insulina Basal | Insulin | 1032-1 | uIU/mL |

## Lípidos

| Test (es) | Test (en) | LOINC | UCUM unit |
|---|---|---|---|
| Colesterol Total | Total cholesterol | 2093-3 | mg/dL |
| Triglicéridos | Triglycerides | 2571-8 | mg/dL |
| Colesterol HDL | HDL cholesterol | 2086-9 | mg/dL |
| Colesterol LDL (calculado) | LDL cholesterol (calc) | 13457-7 | mg/dL |
| Colesterol VLDL (calculado) | VLDL cholesterol (calc) | 13458-5 | mg/dL |
| Colesterol No-HDL | Non-HDL cholesterol | 43396-1 | mg/dL |

## Tiroides

| Test (es) | Test (en) | LOINC | UCUM unit |
|---|---|---|---|
| TSH Ultrasensible | TSH | 3016-3 | uIU/mL |
| T4 Libre | Free T4 | 3024-7 | ng/dL |

## Inmunología / Tamizaje

| Test (es) | Test (en) | LOINC | Notas |
|---|---|---|---|
| VDRL | VDRL/RPR | 5292-8 | Tamizaje; no diagnóstico |
| VIH Ag/Ab 4ta Generación | HIV Ag/Ab 4th gen | 56888-1 | Tamizaje; no diagnóstico |
| Vitamina D (25-OH) | 25-OH Vitamin D | 62292-8 | Inmunología |

## Orina

| Test (es) | Test (en) | LOINC | Notas |
|---|---|---|---|
| Densidad (orina) | Specific gravity | 5811-5 | |
| pH (orina) | Urine pH | 5803-2 | |
| Proteínas (orina) | Urine protein | 20454-5 | |
| Glucosa (orina) | Urine glucose | 2349-9 | |
| Cuerpos cetónicos (orina) | Urine ketones | 2514-0 | |
| Bilirrubina (orina) | Urine bilirubin | 5802-4 | |
| Urobilina (orina) | Urine urobilinogen | 1749-1 | |
| Esterasa leucocitaria (orina) | Urine leukocyte esterase | 5799-2 | |
| Nitritos (orina) | Urine nitrite | 32710-6 | |
| Sangre (orina) | Urine blood | 5794-3 | |
| Leucocitos (orina) | Urine WBC | 5821-4 | Microscopía |
| Hematíes (orina) | Urine RBC | 5808-1 | Microscopía |
| Células epiteliales (orina) | Urine epithelial cells | 5789-3 | Microscopía |
| Moco (orina) | Urine mucus | 824-1 | Microscopía |

## Imagenología

| Estudio | Tipo | LOINC |
|---|---|---|
| CT abdomen+pelvis | DiagnosticReport | 18748-4 |
| CT abdomen+pelvis con contraste | DiagnosticReport | 18748-4 |
| Renal cyst finding | Observation | 79310-9 |

## Paneles (DiagnosticReport.code)

| Panel | LOINC | Notas |
|---|---|---|
| Hemograma completo (CBC) | 57021-8 | "CBC W Auto Differential panel - Blood" |
| Perfil hepático | 24325-3 | "Comprehensive metabolic 2000 panel - Serum or Plasma" |
| Perfil lipídico | 57021-8 | No hay panel LOINC exacto — se usan observaciones individuales |
| Análisis de rutina (orina) | 24356-8 | "Urinalysis complete panel - Urine" |
| Perfil tiroideo básico | 3016-3 + 3024-7 | TSH + T4L; no hay panel único |

## Cómo usar este mapeo

1. Para agregar un resultado nuevo: buscar el test en la tabla, copiar LOINC + UCUM
2. Para exportar a FHIR R4: usar `terravic/lab-report-to-fhir-skill/scripts/convert.py` como referencia
3. Para portabilidad a otro sistema (EHR, app, segunda opinión): estos códigos son universales