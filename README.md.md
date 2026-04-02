# GUÍA: CÓMO SUBIR TU PROYECTO A GITHUB

## PASO 1: Crear el Repositorio en GitHub

1. Ve a **github.com** e inicia sesión (o crea cuenta si no tienes)
2. Haz clic en el **+** (arriba derecha) → **New Repository**
3. Completa los datos:
   - **Repository name**: `Tarea01_Clustering_LDA` (o el nombre que prefieras)
   - **Description**: "Análisis de conglomerados con K-means y clasificación con LDA"
   - **Public** (para que sea visible)
   - Marca: "Add a README file"
   - **.gitignore**: Python
   - **License**: MIT (opcional)
4. Haz clic en **Create repository**

---

## PASO 2: Estructura de Carpetas Recomendada

```
Tarea01_Clustering_LDA/
├── README.md                          # Descripción del proyecto
├── requirements.txt                   # Dependencias de Python
├── .gitignore                        # Archivos a ignorar
│
├── notebooks/
│   └── Tarea01_Mod4.ipynb           # Tu notebook principal
│
├── datos/
│   ├── iris.csv                     # Si usas datos locales
│   └── wine.csv
│
├── imagenes/
│   ├── confusion_matrix.png         # Gráficos generados
│   └── clusters_visualization.png
│
├── scripts/
│   ├── preprocessing.py             # Scripts Python si aplica
│   └── clustering_analysis.py
│
└── resultados/
    ├── modelos_entrenados.pkl       # Modelos guardados
    └── metricas.json                # Resultados
```

---

## PASO 3: Preparar los Archivos

### 3.1 Crear `requirements.txt`

Ejecuta en tu terminal (en el directorio de tu proyecto):

```bash
pip freeze > requirements.txt
```

O copia esto manualmente:

```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
geopandas>=0.10.0
jupyter>=1.0.0
```

### 3.2 Crear `.gitignore`

Crea un archivo llamado `.gitignore` en la raíz con:

```
# Jupyter Notebook
.ipynb_checkpoints/
*.ipynb_checkpoints

# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
*.egg-info/
.installed.cfg
*.egg

# Entorno virtual
venv/
ENV/
env/

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Datos grandes
*.zip
*.rar
data/raw/
```

---

## PASO 4: Clonar el Repositorio Localmente

En tu terminal:

```bash
# Navega a donde quieras el proyecto
cd ~/Documentos

# Clona el repositorio (reemplaza TU_USUARIO y TU_REPO)
git clone https://github.com/TU_USUARIO/Tarea01_Clustering_LDA.git

# Entra a la carpeta
cd Tarea01_Clustering_LDA
```

---

## PASO 5: Agregar tus Archivos

```bash
# Copia tu notebook a la carpeta notebooks/
cp ~/Descargas/Tarea01_Mod4.ipynb ./notebooks/

# Copia el requirements.txt que creaste
cp ~/archivo/requirements.txt ./

# Si tienes datos locales, copialos a data/
cp ~/tus_datos/*.csv ./datos/
```

---

## PASO 6: Agregar y Hacer Commit

```bash
# Ver qué cambios hay
git status

# Agregar todos los archivos
git add .

# Crear un commit con mensaje descriptivo
git commit -m "Initial commit: Agregado notebook con análisis K-means y LDA"

# Subir a GitHub
git push origin main
```

---

## PASO 7: Crear un README.md Profesional

Copia esto en tu archivo `README.md`:

```markdown
# Análisis de Conglomerados y Clasificación - Métodos Multivariados

**Institución**: Universidad Autónoma de Sinaloa  
**Facultad**: Ciencias Físico-Matemáticas  
**Diplomado**: Estadística para Ciencia de Datos  
**Módulo**: IV - Métodos Multivariados  
**Tarea**: 01  

---

## Descripción

Implementación práctica de métodos de clustering y clasificación:

- **K-means Clustering**: Análisis de conglomerados para segmentación de datos
- **Linear Discriminant Analysis (LDA)**: Clasificación supervisada de vinos

Este proyecto demuestra la aplicación de técnicas multivariadas en datos reales.

---

## Contenidos

- `notebooks/Tarea01_Mod4.ipynb`: Notebook con análisis completo
- `datos/`: Datasets utilizados (Iris, Wine)
- `resultados/`: Modelos entrenados y métricas

---

## Tecnologías

- Python 3.8+
- scikit-learn (clustering, LDA)
- pandas, NumPy (manipulación de datos)
- matplotlib, seaborn (visualización)
- geopandas (visualización geográfica)

---

## Instalación

```bash
# Clonar repositorio
git clone https://github.com/TU_USUARIO/Tarea01_Clustering_LDA.git
cd Tarea01_Clustering_LDA

# Instalar dependencias
pip install -r requirements.txt

# Abrir notebook
jupyter notebook notebooks/Tarea01_Mod4.ipynb
```

---

## Resultados Principales

- Accuracy LDA: 97%+ en clasificación de vinos
- Clustering K-means: 3 conglomerados óptimos en dataset Iris
- Validación con multiple random states

---

## Autores

- Ángel Félix Velarde

---

**Fecha**: Enero 2026

```

---

## PASO 8: Actualizar si Hay Cambios

Cada vez que hagas cambios:

```bash
git add .
git commit -m "Descripción del cambio"
git push origin main
```

---

## COMANDOS GIT RÁPIDOS

```bash
# Ver estado
git status

# Ver historial de commits
git log

# Deshacer cambios
git restore nombre_archivo.ipynb

# Ver diferencias
git diff
```

---

## ERRORES COMUNES Y SOLUCIONES

### Error: "fatal: not a git repository"
```bash
# Asegúrate de estar en la carpeta correcta
cd tu_proyecto
git init  # Si no clonaste, inicializa git
```

### Error: "Please tell me who you are"
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

### Archivo muy grande (>100MB)
```bash
# Usa Git LFS (Large File Storage)
git lfs install
git lfs track "*.zip"
git add .gitattributes
```

---

## BONUS: Agregar Badge al README

En tu README.md, añade esto al inicio:

```markdown
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange?style=for-the-badge)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge)](https://jupyter.org/)
```

---

## RESUMEN RÁPIDO (5 MINUTOS)

```bash
# 1. Crear repo en github.com
# 2. Clonar
git clone https://github.com/TU_USUARIO/repo.git
cd repo

# 3. Copiar archivos
cp ~/archivo.ipynb ./notebooks/
echo "pandas, numpy, scikit-learn" > requirements.txt

# 4. Subir
git add .
git commit -m "Inicial"
git push origin main

# LISTO!
```

---

¿Necesitas ayuda con algo específico?
