# 🛡️ Registro de Cambios y Control de Calidad (QA)

Este documento detalla las transformaciones aplicadas al dataset original para garantizar la robustez del modelo predictivo.

### 1. Eliminación de Duplicados
* **Hallazgo:** Se detectó un 1.48% de registros duplicados exactos en la base de datos de origen.
* **Acción:** Remoción definitiva mediante `.drop_duplicates()` para evitar el sobreajuste (*overfitting*) del modelo.

### 2. Sanación de la Variable 'Ciudad'
* **Hallazgo:** Errores de codificación de caracteres UTF-8 (`Ciudad de M√©xico`, `Bogot√±`).
* **Acción:** Unificación mediante expresiones regulares (`re.search`) y reemplazo explícito para consolidar los hubs geográficos reales.

### 3. Tratamiento del Balance (Estrategia de 3 Capas)
* **Capa 1 (Sentinel):** Identificación de valores bandera (`-9999.0`) utilizados por sistemas antiguos para denotar errores. Se convirtieron a valores nulos (`NaN`).
* **Capa 2 (Dominio):** Eliminación de registros con balances negativos inviables según las reglas del negocio.
* **Capa 3 (Outliers/Imputación):** Imputación de valores faltantes utilizando la **mediana segmentada por ciudad**, protegiendo la distribución original antes de evaluar con el algoritmo.