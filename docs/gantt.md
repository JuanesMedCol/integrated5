# 📘 Etapa 1 – Evidencia 1

### *Formulación de una necesidad de ingeniería de datos*

2**Duración:** Semanas 1 a 3 (20 de octubre – 9 de noviembre 2025)
**Peso:** 35 % del proyecto
**Estado:** ✅ **Completada**
**Entrega:** Hasta el **9 de noviembre a las 23:59**

---

## 🧠 Objetivo de la Etapa 1

Identificar una necesidad de ingeniería de datos y desarrollar una solución que integre diversas fuentes públicas para crear una base de datos analítica coherente, limpia y documentada, que sirva como punto de partida para posteriores fases de análisis y visualización.

---

## 🧩 Actividades desarrolladas en la Etapa 1

| Nº | Actividad                                        | Descripción                                                                                                                                                   | Resultado / Evidencia                                      |
| -- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| 1  | **Definición del caso de uso**                   | Se definió el proyecto *Análisis Económico Global 1960–2023*, centrado en PIB, exportaciones, importaciones e inflación.                                      | Descripción del problema en documento APA y README.        |
| 2  | **Selección y descarga de datasets**             | Se eligieron cuatro datasets de Kaggle publicados por *Frederick Salazar (2023)* con datos históricos del Banco Mundial.                                      | Archivos en `/data/raw_data/` y fuentes citadas en README. |
| 3  | **Normalización de datos**                       | Se unificaron separadores, nombres de columnas y formato de valores. Se detectaron y reemplazaron nulos con `"N/A"`.                                          | Archivos en `/data/normalized_data/`.                      |
| 4  | **Integración y limpieza avanzada (ETL)**        | Se desarrolló un script `etl_unify_wdi.py` para automatizar la integración y generación de tablas `dim_geo`, `dim_indicator`, `fact_indicators`, `fact_wide`. | Archivos en `/data/unified_clean/`.                        |
| 5  | **Validación de calidad (QA)**                   | Se generó un reporte de verificación (`qa_report.csv`) sobre consistencia de códigos, años y duplicados.                                                      | Archivo en `/data/unified_clean/qa_report.csv`.            |
| 6  | **Creación de base de datos SQLite**             | Se materializó la base unificada en `db/project.db`, con las tablas y vistas correspondientes.                                                                | Archivo `/db/project.db`.                                  |
| 7  | **Exploración y consultas de prueba en Jupyter** | Se ejecutaron consultas SQL y gráficos iniciales (p. ej., Exportaciones vs Importaciones en Colombia).                                                        | Notebook `run.ipynb`.                                      |
| 8  | **Documentación y entrega parcial**              | Se elaboró el documento APA con objetivos, metodología, fuentes y estructura de resultados.                                                                   | Documento APA (Etapa 1) + README.md actualizado.           |

---

## 📦 Entregables de la Etapa 1

| Entregable                          | Ubicación                                         | Descripción                                          |
| ----------------------------------- | ------------------------------------------------- | ---------------------------------------------------- |
| **Documento APA (Etapa 1)**         | `/docs/` o entregado en LMS                       | Contiene portada, resumen, objetivos y metodología.  |
| **Dataset normalizado y unificado** | `/data/normalized_data/` y `/data/unified_clean/` | Datos limpios, coherentes y listos para análisis.    |
| **Base de datos SQLite**            | `/db/project.db`                                  | Modelo relacional completo con 4 tablas principales. |
| **Reporte de calidad (QA)**         | `/data/unified_clean/qa_report.csv`               | Resumen de validación y duplicados.                  |
| **Notebook exploratorio**           | `run.ipynb`                                       | Consultas SQL y gráficos de validación.              |
| **README.md**                       | Raíz del repositorio                              | Documentación general y fuentes citadas.             |

---

## 📊 Estado General del Proyecto

| Etapa                                              | Periodo         | Evidencia   | Avance    | Estado       |
| -------------------------------------------------- | --------------- | ----------- | --------- | ------------ |
| **Etapa 1 – Formulación y BD (EA1)**               | 20 oct – 9 nov  | Evidencia 1 | **100 %** | ✅ Completado |
| **Etapa 2 – Análisis y visualización (EA2)**       | 10 nov – 24 nov | Evidencia 2 | 0 %       | ⚪ Pendiente  |
| **Etapa 3 – Interpretación y entrega final (EA3)** | 25 nov – 7 dic  | Evidencia 3 | 0 %       | ⚪ Pendiente  |

---

## 🗓️ Gantt – Etapa 1 (Semanas 1–3)

| Actividad                            | Inicio     | Fin        | Duración (días) | Semana | % Avance |
| ------------------------------------ | ---------- | ---------- | --------------- | ------ | -------- |
| Estudio inicial de metodologia       | 20/10/2025 | 26/10/2025 | 06              | 1      | 100 %    |
| Selección del tema y fuentes         | 27/10/2025 | 07/11/2025 | 12              | 2 y 3  | 100 %    |
| Descarga y organización de datasets  | 07/11/2025 | 07/11/2025 | 01              | 3      | 100 %    |
| Limpieza y normalización             | 07/11/2025 | 07/11/2025 | 01              | 3      | 100 %    |
| Integración y creación de modelo ETL | 08/11/2025 | 08/11/2025 | 01              | 3      | 100 %    |
| Carga SQLite + QA                    | 08/11/2025 | 08/11/2025 | 01              | 3      | 100 %    |
| Elaboración Documento APA (Etapa 1)  | 08/11/2025 | 09/11/2025 | 02              | 3      | 100 %    |

----
``` mermaid
gantt
    title Proyecto Integrado – Etapa 1 (Evidencia 1)
    dateFormat  DD/MM/YYYY
    axisFormat  %d/%m
    section Planeación y Análisis Inicial
    Estudio inicial de metodología       :done, a1, 20/10/2025, 6d
    Selección del tema y fuentes         :done, a2, 27/10/2025, 12d
    section Preparación de Datos
    Descarga y organización de datasets  :done, a3, 07/11/2025, 1d
    Limpieza y normalización             :done, a4, 07/11/2025, 1d
    Integración y creación de modelo ETL :done, a5, 08/11/2025, 1d
    Carga SQLite + QA                    :done, a6, 08/11/2025, 1d
    section Documentación
    Elaboración Documento APA (Etapa 1)  :done, a7, 08/11/2025, 2d
```