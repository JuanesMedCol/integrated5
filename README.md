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

---

## ⚖️ Derechos y Uso Académico

Este proyecto ha sido desarrollado con fines exclusivamente **académicos y educativos**, como parte del **Proyecto Integrador 5**.
El contenido, los análisis y las visualizaciones presentadas se basan en **fuentes de datos públicas y abiertas** del Banco Mundial, obtenidas a través de la plataforma **Kaggle**, bajo licencias **PDDL (Public Domain Dedication and License)**, que permiten su libre uso, redistribución y adaptación con fines no comerciales, siempre que se mantenga la atribución correspondiente a los autores originales.

El autor, **Juan Esteban Atehortúa Sánchez**, conserva los derechos morales sobre la estructura, metodología de análisis, procesamiento de datos y los materiales generados en este trabajo.
No obstante, se autoriza su uso, reproducción o adaptación en contextos académicos, investigativos o docentes, siempre que se cite la fuente de manera adecuada, conforme a las normas de **referenciación APA** o el formato bibliográfico requerido.

> **Cita sugerida:**
> Atehortúa Sánchez, J. E. (2025). *Análisis Económico Global (1960–2023): Unificación y análisis de indicadores macroeconómicos (PIB, exportaciones, importaciones e inflación)* [Proyecto académico].

El contenido de este proyecto **no representa posturas oficiales ni asesoramiento económico**, y su propósito es exclusivamente **analítico y formativo**, contribuyendo al fortalecimiento del conocimiento en economía aplicada y análisis de datos.
