# Análisis de Métodos Multivariados - Módulo IV: Clustering y Discriminant Analysis

**Diplomado en Estadística para Ciencia de Datos**  
Universidad Autónoma de Sinaloa - Facultad de Ciencias Físico-Matemáticas

---

## 📋 Descripción General

Este repositorio contiene la **Tarea 01 del Módulo IV** de Métodos Multivariados, donde se implementan y analizan dos técnicas fundamentales del aprendizaje no supervisado y supervisado:

1. **Clustering (Agrupación de Datos)** - Análisis de criminalidad en Estados Unidos
2. **Linear Discriminant Analysis (LDA)** - Clasificación de tipos de vino

---

## 📌 Contenido

### Problema 1: Métodos de Agrupación - US Arrests Dataset

#### Objetivo
Analizar los patrones de criminalidad en los 50 estados de Estados Unidos utilizando métodos de clustering no supervisado.

#### Metodología

**1. Dendrograma (Hierarchical Clustering)**
- Método de enlace completo con distancia Euclidiana
- Estandarización de variables (μ = 0, σ² = 1)
- Identificación de 4 clusters naturales

**2. K-Means Clustering**
- Aplicación del método Elbow para determinar número óptimo de clusters
- Selección de k = 4 para comparabilidad con el dendrograma
- Visualización geográfica de clusters en mapa de USA

#### Variables Analizadas
- **Murder**: Tasa de asesinatos (por 100,000)
- **Assault**: Tasa de asaltos (por 100,000)
- **UrbanPop**: Porcentaje de población urbana
- **Rape**: Tasa de violaciones (por 100,000)

#### Clusters Identificados

| Cluster | Características | Descripción |
|---------|-----------------|-------------|
| Oro | Baja criminalidad, baja urbanización | Estados rurales seguros |
| Azul | Baja criminalidad, alta urbanización | Estados urbanos seguros |
| Rojo | Alta criminalidad, baja urbanización | Estados rurales con problemas de seguridad |
| Verde | Alta criminalidad, alta urbanización | Estados urbanos con alto índice delictivo |

#### Hallazgos
- La variable **Assault** concentra la mayoría de la varianza en los datos
- La estandarización es crítica para comparar variables en diferentes escalas
- Los métodos de clustering (dendrograma y K-means) identifican patrones similares
- Los estados se agrupan naturalmente en 4 categorías basadas en crimen y urbanización

---

### Problema 2: Linear Discriminant Analysis - Wine Classification

#### Objetivo
Clasificar tipos de vino utilizando sus características químicas y análisis discriminante linear.

#### Metodología

**1. Exploración de Datos**
- Dataset: Wine Classification (sklearn.datasets)
- 178 observaciones de 3 clases diferentes
- 13 características químicas por vino

**2. Análisis Discriminante Linear (LDA)**

La función discriminante para cada clase se define como:

$$f_k(x) = \frac{1}{(2\pi)^{p/2}|\Sigma|^{1/2}} \exp\left(-\frac{1}{2}(x-\mu_k)^T \Sigma^{-1} (x-\mu_k)\right)$$

Donde:
- p: número de características
- μₖ: vector medio de la clase k
- Σ: matriz de covarianza común

**3. Optimización del Modelo**
- Estandarización de variables
- División train-test (80-20)
- Evaluación de diferentes números de componentes
- Mejor rendimiento con p = 1 componente

#### Resultados

| Métrica | Valor |
|---------|-------|
| **Exactitud General** | >90% |
| **Componentes Óptimas** | 1 |
| **Varianza Explicada** | ~70% |

#### Desempeño Detallado

- **Precisión, Recall y F1-Score** calculados por clase
- **Matriz de Confusión**: Análisis de clasificaciones correctas e incorrectas
- **Robustez**: Validación con múltiples random states (0, 1, 10, 100)

#### Interpretación

El modelo LDA logra clasificar los vinos de manera satisfactoria con una exactitud superior al 90%. La proyección a una dimensión (p=1) captura la mayor parte de la información discriminativa entre las clases, demostrando la efectividad de LDA para reducción de dimensionalidad.

---

## 🛠️ Requisitos Técnicos

### Librerías Utilizadas

```python
# Data Manipulation
pandas
numpy

# Visualization
matplotlib
seaborn

# Geographic Visualization
geopandas
requests
zipfile

# Machine Learning
scikit-learn
    - preprocessing.StandardScaler
    - cluster.KMeans
    - discriminant_analysis.LinearDiscriminantAnalysis
    - model_selection.train_test_split
    - metrics (confusion_matrix, accuracy_score)
    - datasets (load_wine)

# Clustering
scipy.cluster.hierarchy
    - linkage
    - fcluster
```

### Versión de Python
- Python 3.7+

### Instalación de Dependencias

```bash
pip install pandas numpy matplotlib seaborn geopandas scikit-learn scipy requests
```

---

## 📊 Estructura del Notebook

```
1. Encabezado y Metadatos (Universidad, Diplomado, Instructores)
2. Introducción y Descripción General
3. Problema 1: Clustering
   ├── Carga de datos (USArrests)
   ├── Exploración de datos
   ├── Estandarización
   ├── Análisis con Dendrograma
   ├── Análisis con K-Means
   └── Visualización geográfica
4. Problema 2: Linear Discriminant Analysis
   ├── Carga de datos (Wine)
   ├── Exploración de datos
   ├── Preparación y estandarización
   ├── División train-test
   ├── Entrenamiento de LDA
   ├── Visualización de componentes
   ├── Evaluación de desempeño
   └── Pruebas de robustez
```

---

## 🎯 Conceptos Clave

### Clustering Jerárquico
- Dendrograma como herramienta visual
- Distancia Euclidiana
- Método de enlace completo
- Determinación de número de clusters

### K-Means
- Método Elbow para selección de k
- Centros de cluster (centroids)
- Inercia como medida de compactness
- Comparación con clustering jerárquico

### Linear Discriminant Analysis
- Maximización de separabilidad entre clases
- Asunción de normalidad multivariada
- Matriz de covarianza común
- Reducción de dimensionalidad supervisada

---

## 📈 Visualizaciones Principales

1. **Dendrograma** - Agrupación jerárquica de estados
2. **Gráficos de Perfiles** - Características promedio por cluster
3. **Índice de Criminalidad vs Urbanización** - Scatter plot de clusters
4. **Mapas Geográficos** - Distribución de clusters en USA
5. **Elbow Plot** - Determinación de k óptimo
6. **Box Plots** - Distribución de variables por tipo de vino
7. **Histogramas LDA** - Proyección de datos en componente discriminante
8. **Matriz de Confusión** - Desempeño de clasificación

---

## 👨‍🏫 Instructores

- **Dr. Marco Tulio Gaxiola Leyva**
- **Dra. Norma Selomit Ramírez Uribe**

---

## 📚 Referencias y Bases de Datos

- **US Arrests Dataset**: [Kaggle - USArrests](https://raw.githubusercontent.com/selva86/datasets/master/USArrests.csv)
- **Wine Dataset**: [sklearn.datasets.load_wine()](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_wine.html)
- **Shapefiles**: [Natural Earth - Admin States/Provinces](https://www.naturalearthdata.com/)

---

## 📝 Notas Importantes

- Todos los datos numéricos fueron **estandarizados** antes de aplicar los algoritmos
- La **estandarización es crítica** debido a las diferentes escalas de las variables
- Los análisis incluyen tanto métodos no supervisados (clustering) como supervisados (LDA)
- Las visualizaciones geográficas requieren internet para descargar shapefiles de Natural Earth

---

## 📄 Licencia

Este trabajo es parte del Diplomado en Estadística para Ciencia de Datos de la Universidad Autónoma de Sinaloa.

---

**Última actualización**: Diplomado 2026 
**Estado**: Completo ✓
