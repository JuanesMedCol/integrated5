# 🌍 Análisis Económico Global (1960–2023)

* **Proyecto Integrador 5**
* **Tema:** Unificación y análisis de indicadores macroeconómicos (PIB, exportaciones, importaciones e inflación)
* **Autor:** Juan Esteban Atehortúa Sánchez
* **Fuente de datos:** Kaggle — *Frederick Salazar (2023)*

---

## 🧠 Objetivo General

Analizar la evolución económica global entre 1960 y 2023 mediante la integración de datos públicos del Banco Mundial disponibles en Kaggle, relacionados con el Producto Interno Bruto (PIB), exportaciones, importaciones e inflación. El propósito es desarrollar una base de datos unificada y analíticamente consistente que permita formular un caso de uso real, evaluando la relación entre el crecimiento económico y los indicadores comerciales y monetarios en distintos países.

---

## 🎯 Objetivos Específicos

1. **Integrar múltiples fuentes públicas del Banco Mundial** en una base estructurada que centralice los principales indicadores macroeconómicos globales (PIB, inflación, exportaciones e importaciones), asegurando coherencia y trazabilidad de los datos.

2. **Diseñar un proceso de limpieza y normalización reproducible** que permita transformar datasets heterogéneos en un modelo relacional (*star schema*) optimizado para análisis exploratorios y estadísticos.

3. **Analizar las tendencias históricas** del crecimiento económico global y regional, identificando patrones como:

   * La correlación entre el crecimiento del PIB y la apertura comercial (exportaciones e importaciones).
   * La relación entre la inflación y la estabilidad económica.
   * Las diferencias de comportamiento entre países desarrollados y en desarrollo.

4. **Desarrollar consultas analíticas y visualizaciones dinámicas** en Jupyter Notebook que faciliten:

   * Comparar el desempeño de países por década o región.
   * Calcular promedios, variaciones e indicadores derivados.
   * Detectar periodos de crisis o expansión económica.

5. **Proveer una base para modelos predictivos futuros**, en los que se puedan aplicar técnicas de **aprendizaje automático (machine learning)** para estimar variables como:

   * Crecimiento del PIB futuro en función del comercio exterior e inflación.
   * Riesgo de inflación alta o desaceleración económica según tendencias históricas.

6. **Fortalecer la toma de decisiones económicas** y el aprendizaje académico al ofrecer una estructura de datos reutilizable para investigadores, estudiantes y analistas de política pública.

---

## 🧭 Ejemplos de Aplicaciones Potenciales

| Línea de análisis                              | Descripción                                                                                                               |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **Correlación entre PIB y comercio exterior**  | Evaluar si los países con mayores niveles de exportación/importación presentan un crecimiento sostenido del PIB.          |
| **Efecto de la inflación en la productividad** | Medir cómo los altos niveles de inflación afectan el crecimiento económico a mediano plazo.                               |
| **Comparativo regional**                       | Contrastar América Latina vs Europa o Asia en términos de estabilidad macroeconómica.                                     |
| **Predicción del PIB**                         | Aplicar modelos de regresión lineal o redes neuronales para estimar el PIB futuro según inflación y comercio.             |
| **Monitoreo de crisis económicas**             | Identificar décadas con caídas simultáneas en PIB y exportaciones (crisis del petróleo, crisis asiática, pandemia, etc.). |

---

## 🧩 Enfoque metodológico orientado al uso de datos

1. **Recolección y limpieza de datos** → asegurar comparabilidad temporal y geográfica.
2. **Modelado relacional (SQLite)** → permitir consultas analíticas complejas.
3. **Exploración de patrones históricos** → uso de SQL + pandas + matplotlib.
4. **Generación de insights visuales** → dashboards y reportes comparativos.
5. **Proyección futura (opcional)** → uso de regresión o forecast en notebook posterior.

---

## 🗂️ Estructura del Proyecto

```
📦 proyecto_economico
├── README.md                  ← Documentación principal
├── run.ipynb                  ← Notebook ejecutable del pipeline y consultas
│
├── data/
│   ├── raw_data/              ← Datos originales descargados de Kaggle
│   ├── normalized_data/       ← Datos estandarizados a separacion por comas
│   ├── unified_data/          ← Primer resultado de integración
│   └── unified_clean/         ← Versión final limpia y normalizada (ETL)
│
├── db/
│   ├── project.db             ← Base de datos SQLite final
│   └── readme.md              ← Descripción técnica del esquema y vistas
│
└── docs/
    └── gantt.md               ← Planificación del proyecto

```

---

## 💾 Datasets Utilizados

| Indicador                  | Dataset                                               | URL                                                                                                             | Licencia |
| -------------------------- | ----------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | -------- |
| **Importaciones (% PIB)**  | *Global Imports of Goods and Services (1960–Present)* | [🔗 Kaggle](https://www.kaggle.com/datasets/fredericksalazar/global-imports-goods-and-services-1960-present)    | PDDL     |
| **Exportaciones (% PIB)**  | *Global Exports of Goods and Services (1960–Present)* | [🔗 Kaggle](https://www.kaggle.com/datasets/fredericksalazar/global-exports-of-goods-and-services-1960-present) | PDDL     |
| **PIB Global (1960–2021)** | *PIB (GDP) Global by Countries since 1960 to 2021*    | [🔗 Kaggle](https://www.kaggle.com/datasets/fredericksalazar/pib-gdp-global-by-countries-since-1960-to-2021)    | PDDL     |
| **Inflación (% anual)**    | *Global Inflation Rate (1960–Present)*                | [🔗 Kaggle](https://www.kaggle.com/datasets/fredericksalazar/global-inflation-rate-1960-present)                | PDDL     |

---

## ⚙️ Proceso Metodológico (ETL)

### 1️⃣ Limpieza Inicial

* Conversión de separadores `;` → `,`.
* Estandarización de nombres de campos (`snake_case`).
* Detección de vacíos (`NaN` → `"N/A"`).

### 2️⃣ Normalización y Unificación

Ejecutado con el script:

```bash
python etl_unify_wdi.py --src data/normalized_data --out data/unified_clean
```

Este proceso:

* Deduplica por (`country_code`, `year`, `indicator_code`).
* Clasifica registros (`is_aggregate` = 1 para regiones).
* Genera tablas:

  * `dim_geo` — países, regiones y grupos.
  * `dim_indicator` — indicadores económicos.
  * `fact_indicators` — tabla de hechos normalizada.
  * `fact_wide` — pivote de indicadores por país/año.

---

## 🧮 Base de Datos (SQLite)

Archivo: `db/project.db`

### Tablas principales

| Tabla                | Descripción                                         |
| -------------------- | --------------------------------------------------- |
| `dim_geo`            | Dimensión geográfica (países y regiones)            |
| `dim_indicator`      | Catálogo de indicadores económicos                  |
| `fact_indicators`    | Hechos normalizados por país/año/indicador          |
| `fact_wide`          | Versión pivotada para análisis rápido               |
| `vw_exports_imports` | Vista SQL para comparar exportaciones/importaciones |

---

## 🔍 Consultas y Visualizaciones en Jupyter

### Ejemplo 1 — Exportaciones vs Importaciones (% del PIB)

```python
import sqlite3, pandas as pd, matplotlib.pyplot as plt
conn = sqlite3.connect("db/project.db")

query = """
SELECT 
  f.year,
  AVG(CASE WHEN f.indicator_code='NE.EXP.GNFS.ZS' THEN f.value END) AS exports,
  AVG(CASE WHEN f.indicator_code='NE.IMP.GNFS.ZS' THEN f.value END) AS imports
FROM fact_indicators f
JOIN dim_geo g ON f.country_code=g.country_code
WHERE g.country_name='Colombia'
GROUP BY f.year
ORDER BY f.year;
"""
df = pd.read_sql_query(query, conn)
df.plot(x='year', y=['exports','imports'], figsize=(8,4),
        title='Colombia: Exportaciones vs Importaciones (% del PIB)')
plt.show()
```

### Ejemplo 2 — Crecimiento promedio del PIB por década

```sql
SELECT 
  g.region,
  (f.year/10)*10 AS decade,
  ROUND(AVG(f.value),2) AS avg_gdp_growth
FROM fact_indicators f
JOIN dim_geo g USING (country_code)
WHERE f.indicator_code = 'NY.GDP.MKTP.KD.ZG'
  AND g.is_aggregate = 0
GROUP BY g.region, decade
ORDER BY g.region, decade;
```

---

## 📈 Resultados y Análisis

* Se obtuvo una base global unificada con más de **60 años** de datos económicos.
* Los indicadores muestran correlación entre **PIB**, **inflación** y **comercio exterior**.
* Se habilitan consultas por país, década y región.
* El modelo permite replicar fácilmente el análisis con nuevos indicadores del Banco Mundial.

---

## 📦 Entregables

| Entregable         | Descripción                                |
| ------------------ | ------------------------------------------ |
| `README.md`        | Documentación del proyecto                 |
| `run.ipynb`        | Notebook con ejecución completa y gráficos |
| `db/project.db`    | Base SQLite                                |
| `Documento APA`    | Resumen y análisis formal (Etapa 1)        |

---

## 📚 Referencias (APA)

Salazar, F. (2023). *Global Imports of Goods and Services (1960–Present)* [dataset]. Kaggle.
[https://www.kaggle.com/datasets/fredericksalazar/global-imports-goods-and-services-1960-present](https://www.kaggle.com/datasets/fredericksalazar/global-imports-goods-and-services-1960-present)

Salazar, F. (2023). *Global Exports of Goods and Services (1960–Present)* [dataset]. Kaggle.
[https://www.kaggle.com/datasets/fredericksalazar/global-exports-of-goods-and-services-1960-present](https://www.kaggle.com/datasets/fredericksalazar/global-exports-of-goods-and-services-1960-present)

Salazar, F. (2023). *PIB (GDP) Global by Countries since 1960 to 2021* [dataset]. Kaggle.
[https://www.kaggle.com/datasets/fredericksalazar/pib-gdp-global-by-countries-since-1960-to-2021](https://www.kaggle.com/datasets/fredericksalazar/pib-gdp-global-by-countries-since-1960-to-2021)

Salazar, F. (2023). *Global Inflation Rate (1960–Present)* [dataset]. Kaggle.
[https://www.kaggle.com/datasets/fredericksalazar/global-inflation-rate-1960-present](https://www.kaggle.com/datasets/fredericksalazar/global-inflation-rate-1960-present)

World Bank. (2023). *World Development Indicators*. The World Bank Group.
[https://databank.worldbank.org/source/world-development-indicators](https://databank.worldbank.org/source/world-development-indicators)
