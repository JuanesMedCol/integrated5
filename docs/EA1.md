# 🌍 Análisis Económico Global (1960–2023)

## **Proyecto Integrador 5**
 
* **Tema:** Unificación y análisis de indicadores macroeconómicos (PIB, exportaciones, importaciones e inflación)
* **Autor:** Juan Esteban Atehortúa Sánchez

---

* **Fuente de datos:**
  *	Global Imports of Goods and Services (1960–Present) — Frederick Salazar (2023)
  *	Global Exports of Goods and Services (1960–Present) — Frederick Salazar (2023)
  *	PIB (GDP) Global by Countries since 1960 to 2021 — Frederick Salazar (2023)
  *	Global Inflation Rate (1960–Present) — Frederick Salazar (2023)

---

## 🧠 Objetivo General

Analizar la evolución económica global entre 1960 y 2023 a partir de la integración de datos públicos del Banco Mundial relacionados con el Producto Interno Bruto (PIB), las exportaciones, las importaciones y la inflación. El propósito es comprender, mediante un enfoque analítico, las dinámicas del crecimiento económico y su relación con los principales indicadores comerciales y monetarios, identificando tendencias y comportamientos relevantes a nivel internacional. 

---

## 🎯 Objetivos Específicos

*	Analizar la evolución histórica del PIB global para interpretar las tendencias del crecimiento económico y sus variaciones entre 1960 y 2023 desde una perspectiva descriptiva y analítica.

*	Examinar las tendencias de las importaciones y exportaciones como proporción del PIB con el fin de interpretar los niveles de apertura comercial y su posible relación con los procesos de desarrollo económico global.

*	Analizar el comportamiento de la inflación anual a nivel mundial para identificar patrones vinculados con periodos de estabilidad y desequilibrio económico, considerando su incidencia en el desempeño general de las economías.

*	Explorar las relaciones entre el PIB, las importaciones, las exportaciones y la inflación para detectar comportamientos comunes, contrastes y dinámicas regionales que aporten a la comprensión integral del sistema económico global.

*	Visualizar e interpretar la evolución de los indicadores económicos mediante representaciones analíticas que faciliten la comprensión de las tendencias, correlaciones y transformaciones a lo largo del tiempo.

*	Reflexionar sobre los hallazgos obtenidos a partir del análisis de los datos, valorando su aporte para la interpretación de los fenómenos económicos internacionales y la formulación de perspectivas futuras de estudio.

---

## 🧭 Ejemplos de Aplicaciones Potenciales

| Línea de análisis                              | Descripción                                                                                                               |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **Correlación entre PIB y comercio exterior**  | Evaluar si los países con mayores niveles de exportación/importación presentan un crecimiento sostenido del PIB.          |
| **Efecto de la inflación en la productividad** | Medir cómo los altos niveles de inflación afectan el crecimiento económico a mediano plazo.                               |
| **Comparativo regional**                       | Contrastar América Latina vs Europa o Asia en términos de estabilidad macroeconómica.                                     |
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
│   └──project.db              ← Base de datos SQLite final
│
└── docs/
    ├── EA1.db                 ← Documentacion de Evidencia 1
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

## 📈 Resultados y Análisis

* Se obtuvo una base global unificada con más de **60 años** de datos económicos.
* Los indicadores muestran correlación entre **PIB**, **inflación** y **comercio exterior**.
* Se habilitan consultas por país, década y región.
* El modelo permite replicar fácilmente el análisis con nuevos indicadores del Banco Mundial.

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
