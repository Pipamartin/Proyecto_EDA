# Proyecto_EDA


## VOLVER A REVISAR
## QUITAR EMOTICONES


# 🛍️ Análisis Exploratorio de Datos (EDA) del Dataset Online Retail II

## 🎯 1. Objetivo del Proyecto

Este repositorio contiene un **Análisis Exploratorio de Datos (EDA)** detallado realizado sobre el dataset `Online Retail II`.

El objetivo principal fue aplicar las fases fundamentales del proceso de *Data Science*: **Carga, Exploración, Limpieza y Visualización Básica**, con el fin de comprender las características, la calidad y las distribuciones de los datos antes de cualquier análisis avanzado o modelado.

## 💾 2. Dataset Utilizado

* **Nombre del Dataset:** Online Retail II (Fuente: Kaggle/UCI Machine Learning Repository).
* **Descripción:** Contiene todas las transacciones de ventas al por menor en línea realizadas por una compañía con sede en el Reino Unido entre el 01/12/2009 y el 09/12/2011.
* **Volumen Inicial:** Aproximadamente **[CANTIDAD DE FILAS INICIALES]** registros.
* **Desafíos Identificados:** El dataset es un clásico de EDA por la presencia de valores nulos, duplicados y *outliers* lógicos (cantidades y precios negativos/cero) que requieren un tratamiento justificado.

## 📁 3. Estructura del Repositorio

La estructura del repositorio sigue las directrices del ejercicio:
├── data/ 
│ └── online_retail_II.csv # Dataset utilizado 
├── notebooks/ 
│ └── eda.ipynb # Notebook de Jupyter con el análisis completo 
└── README.md # Este documento
└── requirements.txt (opcional)

## 🛠️ 4. Análisis Realizado (Resumen de las Fases)

### 4.1. Exploración Inicial

* **Tipos de Datos:** Se identificaron inconsistencias, especialmente en las columnas `InvoiceDate` (tratada como *string* inicialmente) y `Customer ID` (tratada como *float*).
* **Valores Nulos:** Se detectaron nulos significativos en `Customer ID` (~25% de los datos) y nulos menores en `Description`.
* **Incoherencias:** Se confirmaron registros anómalos en `Quantity` y `Price` (valores $\le 0$).

### 4.2. Limpieza y Preprocesamiento

Se aplicaron las siguientes transformaciones, justificando cada decisión:

| Tarea de Limpieza | Justificación | Resultado |
| :--- | :--- | :--- |
| **Tratamiento de Nulos** en `Customer ID` | Eliminación de registros para enfocar el análisis en clientes identificados. | Dataset reducido a **[CANTIDAD FINAL]** filas. |
| **Corrección de Tipos** | `InvoiceDate` a `datetime`, `Customer ID` a `object`. | Coherencia para análisis temporal. |
| **Tratamiento de Incoherencias** | Eliminación de filas con `Quantity` $\le 0$ y `Price` $\le 0$. | Eliminación de devoluciones y transacciones anómalas. |
| **Creación de Métrica** | Creación de la columna `Sales` ($Quantity \times Price$). | Métrica clave para la visualización de valor. |

### 4.3. Hallazgos Clave de la Visualización

Las visualizaciones básicas revelaron:

1.  **Distribución de Ventas:** Una alta concentración de transacciones de bajo valor, confirmando la necesidad de aplicar filtrado para el estudio de los *outliers* de alto valor.
2.  **Dominio Geográfico:** **Reino Unido** representa la inmensa mayoría de las transacciones (más del 90%).
3.  **Tendencia Temporal:** Se observa una tendencia creciente en las ventas mensuales, con un notable pico estacional hacia el final del período de recolección de datos.

## 🔗 5. Enlace al Notebook

Puede consultar el análisis completo, incluyendo todo el código Python, las justificaciones de limpieza y las visualizaciones en el siguiente archivo:

[Enlace al Notebook `eda.ipynb` dentro del repositorio]

---
Autor: vicmary del Valle Martinez Perez