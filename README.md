# Predicción de Capturas Pesqueras en Argentina – Proyecto Final Integrador

Este repositorio contiene el código y los recursos para el Proyecto Final Integrador del Diplomado en Ciencia de Datos y Análisis Avanzado. El objetivo es predecir el volumen de captura pesquera mensual (en kg) en Argentina utilizando técnicas de Machine Learning, siguiendo la metodología CRISP-DM.

## Contenido

- `Trabajo_Integrador_Grupo_6.ipynb`: Notebook Jupyter con todo el análisis: carga de datos, EDA, ingeniería de variables, modelado (XGBoost, Random Forest, MLP, SARIMA), modelos segmentados por especie, evaluación de métricas y comparación de resultados.
- `data/`: Carpeta donde debe colocarse el archivo `captura-puerto-flota-2010-2019.csv` descargado del portal oficial (ver instrucciones más abajo).
- `README.md`: Este archivo, que describe el proyecto, requisitos y cómo ejecutar el notebook.

## Requisitos

- Python 3.10 o superior.
- Librerías de Python: `pandas`, `numpy`, `scikit-learn`, `xgboost`, `statsmodels`, `matplotlib`, `seaborn`. Opcionalmente, `plotly` si se desea visualizar el mapa geográfico interactivo.

## Instalación

1. Clona o descarga este repositorio.
2. Crea un entorno virtual (opcional pero recomendado):

   ```bash
   python -m venv env
   source env/bin/activate
   pip install -q xgboost statsmodels scikit-learn pandas matplotlib seaborn plotly umap-learn
   ```
   
# Si deseas usar visualizaciones interactivas:

   ```bash
   pip install plotly
   ```

## Descarga de Datos
1. Debes descargar los datos del portal oficial del Ministerio de Agricultura, Ganadería y Pesca de Argentina y colocar el archivo consolidado en la carpeta `data/` del repositorio. Sigue estos pasos:

Accede a las fuentes oficiales:
* [Dataset 1](https://datos.magyp.gob.ar/dataset/e2f12522-4dea-495e-877a-b6d2737ae6bf/archivo/1996a5ec-7075-4062-9a79-05868fc2a2e2)
* [Dataset 2](https://datos.magyp.gob.ar/dataset/e2f12522-4dea-495e-877a-b6d2737ae6bf/archivo/77a15b4a-71e1-4b81-9732-ae0b6863c8cc)

2. Descarga y consolida los archivos en un único archivo llamado `captura-puerto-flota-2010-2019.csv`.
3. Copia el archivo a la ruta `data/` en tu copia local del repositorio.

## Ejecución del Notebook
Abre el notebook captura_pesquera_ml.ipynb con Jupyter Notebook o JupyterLab:

   ```bash
   jupyter notebook captura_pesquera_ml.ipynb
   ```

### Ejecuta las celdas en orden. El notebook realiza los siguientes pasos:

 1. Importación de librerías y configuración.
 2. Carga del dataset y exploración inicial.
 3. Análisis exploratorio: series temporales, estacionalidad por especie, análisis geográfico y por flota.
 4. Ingeniería de variables y preparación de datos.
 5. Entrenamiento de modelos globales (XGBoost, Random Forest, MLP) y un modelo SARIMA sobre la serie agregada.
 6. Entrenamiento de modelos segmentados por especie agrupada (Top 5) y comparación contra el modelo global.
 7. Evaluación de métricas (MAE, RMSE, MAPE, R²) y visualización de resultados.

Al finalizar, podrás observar la tabla comparativa de todos los modelos y los gráficos de predicción vs. valores reales.

## Citaciones
* **Datos:** Ministerio de Agricultura, Ganadería y Pesca – Portal de Datos Abiertos de Argentina.
* **Metodología:** CRISP-DM (Cross-Industry Standard Process for Data Mining).
