# Predicción de Rendimiento de Cultivos de Maíz

Este proyecto desarrolla un pipeline de machine learning para predecir el rendimiento de cultivos de maíz basado en datos climáticos, uso de pesticidas y fertilizantes.

## Resumen del Proyecto

El objetivo es construir un modelo que pueda predecir el rendimiento de maíz (yield) utilizando variables como temperatura, precipitaciones, uso de pesticidas y fertilizantes por área geográfica y año.

## Dataset

Utilizamos el dataset de Kaggle "Crop Yield Prediction Dataset" que contiene:
- yield.csv: Rendimiento de maíz por área y año
- temp.csv: Datos de temperatura promedio
- rainfall.csv: Datos de precipitaciones
- pesticides_by_type.csv: Uso de pesticidas por tipo (este y el siguiente dataset fueron incluidos manualmente desde otra fuente, ver primeras líneas de la notebook EDA.ipynb)
- fertilizers_by_type.csv: Uso de fertilizantes por tipo

Los datos cubren diferentes países y años, permitiendo análisis temporal y geográfico.

## Metodología

### Preparación de Datos

**Descarga y almacenamiento:**
Los datos se descargan directamente desde Kaggle usando kagglehub y se mueven la carpeta local `data/`.

**Limpieza de variables:**
Se identifican y eliminan columnas que tienen un solo valor único, ya que no aportan información discriminante para el modelo.

**Estandarización de columnas:**
Se aplica una función para normalizar nombres de columnas:
- Convertir a minúsculas
- Eliminar espacios extra al inicio y final
- Reemplazar espacios internos por guiones bajos

**Homogeneización de identificadores:**
Se renombra la columna 'country' a 'area' en el dataset de temperatura para que coincida con los otros dataframes.

### Análisis Exploratorio

**Combinación de datasets:**
Se realiza merge secuencial usando left join en las columnas 'year' y 'area'.

El orden de merge es:
1. yield (base)
2. + temperature
3. + rainfall  
4. + pesticides
5. + fertilizers

**Análisis de completitud:**
Se examina la presencia de valores faltantes y la cardinalidad de las variables categóricas principales (area y year) para entender la cobertura temporal y geográfica de los datos.

## Estructura del Proyecto

```
crop-yield-predictor/
├── data/                    # Datasets descargados
├── notebooks/              # Análisis exploratorio
│   └── EDA.ipynb           # Notebook principal
├── requirements.txt        # Dependencias
└── README.md              # Este archivo
```

## Configuración del Entorno

1. Crear y activar entorno virtual:
```bash
python -m venv venv
venv\Scripts\activate
```

2. Instalar dependencias:
```bash
pip install -r requirements.txt
```

3. Configurar kernel de Jupyter:
```bash
python -m ipykernel install --user --name=venv --display-name="Python (venv)"
```

## Uso

El análisis principal se encuentra en `notebooks/EDA.ipynb`. El notebook está estructurado para ejecutarse secuencialmente:

1. Descarga y preparación de datos
2. Carga y estandarización de dataframes
3. Combinación de datasets
4. Limpieza y análisis exploratorio

## Próximos Pasos

- Feature engineering adicional
- Análisis de correlaciones
- Modelado y evaluación
- Deployment del pipeline

## Notas Técnicas

- Los datos se procesan en memoria usando pandas
- Se mantiene trazabilidad de todas las transformaciones
- El código está documentado para facilitar reproducibilidad
