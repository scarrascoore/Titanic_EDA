# Titanic - Análisis Exploratorio de Datos (EDA)

## Descripción del proyecto
Este proyecto presenta un análisis exploratorio de datos (EDA) del dataset **Titanic**, con el objetivo de comprender la estructura de los datos, identificar valores faltantes y explorar visualmente algunas relaciones importantes entre variables.

El análisis fue desarrollado en Python usando **Pandas**, **NumPy**, **Matplotlib** y **Seaborn**.

## Objetivo
Explorar el dataset Titanic para:
- conocer su estructura general,
- revisar tipos de datos,
- identificar valores faltantes,
- realizar un tratamiento básico de datos nulos,
- analizar distribuciones de variables categóricas y numéricas,
- observar relaciones entre algunas variables mediante correlación y visualizaciones.

## Dataset
El dataset utilizado corresponde a **Titanic**, comúnmente usado en proyectos introductorios de análisis de datos y machine learning.

## Herramientas utilizadas
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Librerías importadas
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

## Proceso realizado

### 1. Carga de datos
Se cargó el archivo `train.csv` desde la carpeta `data/raw/` y se visualizó una muestra inicial del dataset con `head()`.

## Acceso al dataset

El dataset puede consultarse en Kaggle en el siguiente enlace:

[Titanic Dataset - Kaggle](https://www.kaggle.com/datasets/heptapod/titanic)

Ejemplo de carga usando `kagglehub`:

```python
import kagglehub
from kagglehub import KaggleDatasetAdapter

file_path = ""

hf_dataset = kagglehub.load_dataset(
    KaggleDatasetAdapter.HUGGING_FACE,
    "heptapod/titanic",
    file_path
)

print("Hugging Face Dataset:", hf_dataset)
```


### 2. Exploración inicial
Se realizó una revisión general del dataset utilizando:
- `df.shape` para conocer dimensiones,
- `df.info()` para revisar tipos de datos y valores no nulos,
- `df.describe(include="all")` para obtener un resumen estadístico,
- `df.columns` para listar las columnas,
- `df.duplicated().sum()` para verificar registros duplicados.

### 3. Revisión de valores faltantes
Se analizaron los valores nulos con:
- `df.isnull().sum().sort_values(ascending=False)`
- cálculo del porcentaje de nulos por columna.

### 4. Tratamiento de valores faltantes
Se aplicó un tratamiento básico a dos variables:
- **Age**: se reemplazaron los valores faltantes con la **mediana**.
- **Embarked**: se reemplazaron los valores faltantes con la **moda**.

### 5. Análisis de variables categóricas
Se revisó la frecuencia de categorías en:
- `Sex`
- `Embarked`
- `Pclass`

Además, se generaron gráficos de conteo para estas variables usando `countplot`.

### 6. Análisis de variables numéricas
Se exploraron las distribuciones de:
- `Age`
- `Fare`
- `Parch`

para observar su comportamiento general mediante histogramas.

### 7. Correlación entre variables numéricas
Se calculó la matriz de correlación entre:
- `Pclass`
- `Age`
- `Parch`
- `Fare`

y se representó con un mapa de calor (`heatmap`).

### 8. Visualización exploratoria
Se realizaron visualizaciones adicionales para explorar relaciones entre variables:
- **Boxplot** de `Fare` según `Pclass`
- **Pairplot** entre `Age`, `Fare` y `Pclass`

## Visualizaciones realizadas
Durante el análisis se generaron las siguientes visualizaciones:
- gráficos de conteo de variables categóricas,
- histogramas de variables numéricas,
- mapa de calor de correlaciones,
- boxplot de tarifa por clase,
- pairplot de variables numéricas seleccionadas.

## Hallazgos generales del análisis
A partir de la exploración realizada, se pudo observar que:
- existen valores faltantes principalmente en algunas columnas del dataset,
- `Age` y `Embarked` requerían tratamiento de nulos para facilitar el análisis,
- `Pclass`, `Fare` y `Age` muestran patrones útiles para una exploración inicial,
- la tarifa (`Fare`) presenta diferencias según la clase del pasajero,
- la matriz de correlación permite identificar relaciones entre algunas variables numéricas.

## Estructura del proyecto
```text
titanic-eda/
│
├── data/
│   └── raw/
│       └── train.csv
│
├── notebooks/
│   └── eda_titanic.ipynb
│
└── README.md
```

## Cómo ejecutar el proyecto
1. Clonar este repositorio.
2. Instalar las librerías necesarias.
3. Abrir el notebook en VS Code o Jupyter Notebook.
4. Ejecutar las celdas paso a paso.

## Instalación de dependencias
```bash
pip install pandas numpy matplotlib seaborn
```

## Estado del proyecto
Este proyecto corresponde a una **primera etapa de análisis exploratorio de datos**.  
No incluye todavía:
- modelado predictivo,
- ingeniería de características,
- evaluación de modelos,
- tratamiento avanzado de outliers.

## Aprendizajes desarrollados
Este proyecto permitió practicar:
- carga y exploración de datos,
- lectura de estructura de un dataset,
- identificación y tratamiento básico de valores faltantes,
- análisis descriptivo,
- visualización exploratoria de datos,
- interpretación inicial de relaciones entre variables.

---

## Autor
**SHELVY CARRASCO ORÉ**
- GitHub: [@scarrascoore](https://github.com/scarrascoore)
- LinkedIn: [Shelvycarrascoore](https://linkedin.com/in/shelvycarrascoore)