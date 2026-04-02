# Análisis de Conglomerados y Clasificación - Métodos Multivariados

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange?style=for-the-badge)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge)](https://jupyter.org/)

---

## Información del Curso

**Institución**: Universidad Autónoma de Sinaloa  
**Facultad**: Ciencias Físico-Matemáticas  
**Diplomado**: Estadística para Ciencia de Datos  
**Módulo**: IV - Métodos Multivariados  
**Tarea**: 01  
**Profesor**: Dr. Marco Tulio Gaxiola Leyva, Dra. Norma Selomit Ramírez Uribe  
**Autor**: Ángel Félix Velarde  
**Fecha**: Enero 2026

---

## Descripción

Este proyecto implementa y analiza técnicas de **machine learning no supervisado y supervisado** aplicadas a datos reales:

- **K-means Clustering**: Segmentación automática de datos en grupos
- **Linear Discriminant Analysis (LDA)**: Clasificación supervisada con análisis discriminante

Se trabaja con dos datasets clásicos (Iris y Wine) para demostrar la efectividad de estos métodos multivariados.

---

## Objetivos

- Implementar K-means para clustering y determinar el número óptimo de conglomerados
- Aplicar LDA para clasificación supervisada
- Evaluar desempeño de modelos con métricas estándar
- Visualizar resultados en 2D y 3D
- Validar robustez de modelos con diferentes configuraciones

---

## Contenido del Proyecto

```
Tarea01_Clustering_LDA/
├── README.md                          # Este archivo
├── requirements.txt                   # Dependencias
├── .gitignore                        # Archivos a ignorar en Git
│
├── notebooks/
│   └── Tarea01_Mod4.ipynb           # Análisis completo
│
└── datos/
    └── (generados automáticamente)
```

---

## Metodología

### 1. Análisis de Conglomerados (K-means)

**Dataset**: Iris  
**Proceso**:
- Normalización de features con StandardScaler
- Elbow method para determinar k óptimo
- Entrenamiento de K-means con diferentes valores de k
- Visualización de clusters en 2D y 3D
- Análisis de centroides

**Resultados**:
- k óptimo: 3 conglomerados
- Interpretación de clusters según especies

### 2. Clasificación con LDA

**Dataset**: Wine  
**Proceso**:
- Preprocesamiento y normalización
- Entrenamiento de LDA con n_components=1
- Predicción en datos de prueba
- Matriz de confusión
- Cálculo de accuracy
- Validación con múltiples random states

**Resultados**:
- Accuracy: >97% en test set
- Consistente con diferentes random states (0, 1, 10, 100)
- LDA logra separación efectiva de clases

---

## Tecnologías y Bibliotecas

| Librería | Versión | Propósito |
|----------|---------|----------|
| **scikit-learn** | 1.0+ | Clustering, LDA, métricas |
| **pandas** | 1.3+ | Manipulación de datos |
| **numpy** | 1.21+ | Operaciones numéricas |
| **matplotlib** | 3.4+ | Visualización base |
| **seaborn** | 0.11+ | Visualización estadística |
| **geopandas** | 0.10+ | Visualización geográfica |

---

## Instalación

### Requisitos Previos
- Python 3.8 o superior
- pip (gestor de paquetes Python)
- Jupyter Notebook (opcional pero recomendado)

### Pasos

```bash
# 1. Clonar el repositorio
git clone https://github.com/AngelFelixV/Tarea01_Clustering_LDA.git
cd Tarea01_Clustering_LDA

# 2. Crear entorno virtual (recomendado)
python -m venv venv

# En Windows:
venv\Scripts\activate

# En macOS/Linux:
source venv/bin/activate

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Ejecutar Jupyter Notebook
jupyter notebook notebooks/Tarea01_Mod4.ipynb
```

---

## Estructura del Notebook

El notebook está organizado en secciones:

1. **Importaciones y Configuración**
   - Librerías necesarias
   - Configuración de visualización

2. **Carga y Exploración de Datos**
   - Dataset Iris
   - Estadísticas descriptivas
   - Visualizaciones exploratorias

3. **K-means Clustering**
   - Estandarización de datos
   - Elbow method
   - Entrenamiento de modelo
   - Visualización de clusters

4. **Análisis Adicional**
   - Gráficos 3D
   - Interpretación de resultados

5. **Linear Discriminant Analysis (LDA)**
   - Carga del dataset Wine
   - Normalización
   - Entrenamiento de LDA
   - Predicción y evaluación

6. **Evaluación de Modelos**
   - Matriz de confusión
   - Accuracy score
   - Validación robusta

---

## Resultados Principales

### K-means Clustering en Iris
- Número óptimo de clusters: 3
- Silhouette Score: ~0.55
- Clusters bien separados

### LDA en Wine Dataset
- Exactitud: 97%+
- Matriz de confusión muestra excelente separación
- Robusto a diferentes random states
- n_components=1 es suficiente para clasificación

---

## Cómo Ejecutar

### Opción 1: Jupyter Notebook (Recomendado)
```bash
jupyter notebook notebooks/Tarea01_Mod4.ipynb
```

### Opción 2: En Google Colab
1. Sube el notebook a tu Google Drive
2. Abre con Google Colab
3. Ejecuta las celdas en orden

---

## Contribuciones de Ángel Félix Velarde

- Implementación del pipeline completo de análisis
- Limpieza y preparación de datos
- Desarrollo de visualizaciones
- Evaluación y validación de modelos
- Documentación del código
- Análisis de resultados e interpretación

---

## Algoritmos Utilizados

### K-means
- Clustering no supervisado
- Minimiza la varianza intra-cluster
- Útil para segmentación exploratoria
- Complejidad: O(n*k*i*d)

### Linear Discriminant Analysis
- Clasificación supervisada
- Encuentra combinaciones lineales de features
- Maximiza separabilidad entre clases
- Asume distribución normal multivariada

---

## Librerías Clave

```python
from sklearn.cluster import KMeans
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
from sklearn.metrics import confusion_matrix, accuracy_score
```

---

## Referencias

- **scikit-learn Documentation**: https://scikit-learn.org/
- **K-means**: MacQueen, J. (1967). Some methods for classification
- **LDA**: Fisher, R. A. (1936). The use of multiple measurements

---

## Notas Importantes

- Los datos se cargan automáticamente desde scikit-learn
- La reproducibilidad se logra fijando random_state
- Normalización es esencial antes de clustering
- K-means es sensible a la inicialización

---

## Mejoras Futuras

- Implementar otros métodos de clustering (DBSCAN, Hierarchical)
- Comparar con Gaussian Mixture Models (GMM)
- Análisis de componentes principales (PCA)
- Validación cruzada para LDA
- Tuning de hiperparámetros

---

## Licencia

Este proyecto es para fines educativos dentro del Diplomado de la Universidad Autónoma de Sinaloa.

---

## Contacto

Para preguntas o sugerencias sobre este análisis:
- GitHub: [AngelFelixV](https://github.com/AngelFelixV)

---

**Estado**: Completado  
**Última actualización**: Enero 2026
