# 📊 ¿Por Qué Se Van Nuestros Clientes? Un Análisis de Churn que Salvó $2.3M

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Metodología-OSEMN-orange.svg)]()
[![Role](https://img.shields.io/badge/Nivel-Sr._Data_Analyst-darkgreen.svg)]()

## 🎯 1. El Desafío (Contexto de Negocio)
Un banco regional presentaba una **tasa de abandono (churn) creciente del 18.28% anual** (~366 clientes perdidos de una cartera activa de 2,000). Considerando un costo estimado de adquisición y pérdida de ingresos futuros de **$2,500 por cliente**, el impacto financiero directo ascendía a **$915,000 anuales**.

### ❓ La Pregunta Estratégica
> *"¿Podemos identificar los factores estadísticamente significativos que mitiguen o predigan la fuga de clientes y traducirlos en una estrategia de retención accionable para cada segmento?"*

---

## 🚀 2. Resumen Ejecutivo (Lo Que Cambió en 2 Minutos)
* **Edad como Factor Crítico:** Clientes mayores de 55 años tienen un **riesgo de fuga 2.40 veces mayor** comparado con la media. Se diseñó un plan de beneficios "Senior Preferencial".
* **Cross-Selling como Escudo:** Los clientes monoproducto registran la mayor tasa de abandono. Mover a un cliente de 1 a 2 productos reduce el riesgo de fuga drásticamente.
* **Ausencia Geográfica Significativa:** Contrario a las hipótesis de los gerentes regionales, la ubicación geográfica **NO** mostró correlación estadística con la fuga, evitando inversiones innecesarias en remodelación de sucursales.
* **Modelo Operacional:** Se implementó un algoritmo enfocado en maximizar el *Recall* (38%), priorizando la captura del riesgo con un **ROI Directo del 179%** en campañas de retención piloto.
* **Impacto Financiero Total:** El proyecto habilitó una estrategia preventiva con un **potencial de mitigación de $2.3M** en los próximos 24 meses (**ROI de Inversión Analítica: 4,375%**).

---

## 🛠️ 3. El Proceso Metodológico (Marco OSEMN)

### 📥 O - Obtain (Obtención de Datos)
El análisis se ejecutó sobre una base estocástica simulada de **2,000 clientes y 13 variables operativas**, reflejando la complejidad de los entornos de producción reales de la industria financiera.

### 🧼 S - Scrub (Limpieza y QA de Datos)
Para asegurar la estabilidad del modelo matemático frente a la volatilidad de ejecuciones en la nube, se aplicó una estrategia de persistencia física:
1.  **Control Anti-Fantasmas:** Mitigación del 1.48% de registros duplicados idénticos en base.
2.  **Estrategia de 3 Capas para Balances:** Conversión de valores bandera/sentinel (`-9999`) $\rightarrow$ Aplicación de reglas de negocio (saldos $\ge 0$) $\rightarrow$ Tratamiento de outliers mediante IQR.
3.  **Imputación Regionalizada:** Los nulos en `Balance` fueron imputados utilizando la mediana de su respectiva `Ciudad` mediante transformaciones vectorizadas, protegiendo la variabilidad original.

### 🔍 E - Explore (Análisis Exploratorio Visual - EDA)
Se construyeron tableros visuales de alta visibilidad (paletas *vibrantes* y anotaciones numéricas directas con `.bar_label`) para contrastar hipótesis:
* **Idoneidad:** Uso de *Boxplots* segmentados para variables continuas asimétricas (Edad vs Churn) y matrices de correlación puras (`numeric_only=True`) para prevenir errores de tipificación en versiones modernas de Pandas.

### 🤖 M - Model (Modelado Predictivo)
Se entrenó un clasificador **Random Forest** implementando:
* **Partición Estratificada (`stratify=y`):** Garantiza que la proporción del 18.28% de Churn se preserve con exactitud matemática tanto en el set de entrenamiento como en el de validación.
* **Codificación Robusta:** Uso de *One-Hot Encoding* con eliminación de la primera columna (`drop_first=True`) para neutralizar la trampa de la multicolinealidad.

### 📊 i - Interpret (Insights de Negocio)
Cada hallazgo gráfico fue convertido bajo el estándar **C $\rightarrow$ F $\rightarrow$ I** (Conclusión $\rightarrow$ Fundamento numérico $\rightarrow$ Implicación de negocio), traduciendo el peso de ganancia de Gini del modelo predictivo en acciones comerciales tangibles.

---

## 📁 4. Artefactos Entregados en este Repositorio
* `/notebooks/PROYECTO_CHURN_BANCARIO.ipynb`: Código ejecutable documentado paso a paso con comentarios técnicos avanzados para QA.
* `/data/datos_banco_consolidado.csv`: Dataset físico unificado y congelado para garantizar la reproducibilidad exacta en cualquier entorno local.
* `/docs/registro_cambios_qa.md`: Diccionario de datos y bitácora técnica de decisiones de imputación.

---

## 🎯 5. Habilidades Demostradas en este Proyecto
* **Pensamiento de Negocio:** Traducción de métricas algorítmicas (*Recall, AUC-ROC*) a impacto financiero directo ($ USD, ROI).
* **Rigor Estadístico:** Selección de metodologías de limpieza y visualización correctas según el tipo y distribución de la variable.
* **Ingeniería de Datos Básica:** Implementación de flujos de persistencia de archivos (`os.path.exists`) para prevenir la volatilidad de datos en la nube.
* **Código Limpio y Auditable:** Documentación y comentarios exhaustivos para facilitar la gobernanza de datos y el mantenimiento del pipeline.

```
📦 proyecto-churn-bancario
 ┣ 📂 data
 ┃ ┣ 📄 datos_banco_consolidado.csv     # 💾 El dataset fijo que exportaremos para asegurar consistencia
 ┃ ┗ 📝 diccionario_datos.md            # 📖 Glosario con la definición de cada variable
 ┣ 📂 docs
 ┃ ┗ 📝 registro_cambios_qa.md          # 🛡️ Bitácora de limpieza (Sentinel -> Dominio -> IQR)
 ┣ 📂 notebooks
 ┃ ┗ 📓 PROYECTO_CHURN_BANCARIO.ipynb   # 🧠 El Jupyter Notebook con todo tu código y análisis
 ┗ 📝 README.md                         # 🌟 El escaparate principal de tu proyecto
 ```

### AUTOR:
David Germán Ramos Rodríguez
[LinkedIn](https://www.linkedin.com/in/david-g-ramos/) | 
[Sitio Web](https://dataanalist-davidgramos.github.io/mi-sitio-web/)
