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
