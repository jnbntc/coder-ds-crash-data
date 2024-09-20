<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue"/> <img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white"/> <img src="https://img.shields.io/badge/conda-342B029.svg?&style=for-the-badge&logo=anaconda&logoColor=white"/> <img src="https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white"/> <img src="https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white"/><img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>

## Descripción del Dataset de Accidentes de Tráfico

**Archivo:** dataset_description.ipynb

Este dataset contiene información detallada sobre accidentes de tráfico, incluyendo características del accidente, condiciones ambientales, información del vehículo y del conductor. 

**Columnas:**

| Nombre de la Columna         | Descripción                                           | Tipo de Dato  |
|------------------------------|----------------------------------------------------|--------------|
| Report Number              | Número único de reporte del accidente              | Categórico   |
| Local Case Number          | Número de caso local                                | Categórico   |
| Agency Name                | Nombre de la agencia que reporta el accidente       | Categórico   |
| ACRS Report Type           | Tipo de reporte de acuerdo al sistema ACRS        | Categórico   |
| Crash Date/Time            | Fecha y hora del accidente                          | Fecha/Hora   |
| Route Type                 | Tipo de vía donde ocurrió el accidente              | Categórico   |
| Road Name                  | Nombre de la vía                                    | Categórico   |
| Cross-Street Type          | Tipo de vía que cruza                              | Categórico   |
| Cross-Street Name           | Nombre de la vía que cruza                          | Categórico   |
| Off-Road Description       | Descripción de la ubicación si no es una vía     | Categórico   |
| Municipality               | Municipio donde ocurrió el accidente                | Categórico   |
| Related Non-Motorist       | Información sobre no-motoristas involucrados       | Categórico   |
| Collision Type             | Tipo de colisión                                    | Categórico   |
| Weather                    | Condiciones climáticas al momento del accidente      | Categórico   |
| Surface Condition          | Condición de la superficie de la vía                | Categórico   |
| Light                      | Condiciones de iluminación al momento del accidente  | Categórico   |
| Traffic Control            | Tipo de control de tráfico presente               | Categórico   |
| Driver Substance Abuse     | Detección de sustancias en el conductor           | Categórico   |
| Non-Motorist Substance Abuse | Detección de sustancias en no-motoristas          | Categórico   |
| Person ID                  | ID único de la persona involucrada en el accidente | Categórico   |
| Driver At Fault            | Indicador si el conductor tuvo la culpa            | Booleano     |
| Injury Severity            | Severidad de las lesiones del accidente            | Categórico   |
| Circumstance               | Circunstancias del accidente                       | Categórico   |
| Driver Distracted By       | Distracción del conductor al momento del accidente | Categórico   |
| Drivers License State      | Estado de la licencia de conducir del conductor   | Categórico   |
| Vehicle ID                 | ID único del vehículo involucrado                  | Categórico   |
| Vehicle Damage Extent      | Extensión de los daños del vehículo                 | Categórico   |
| Vehicle First Impact Location | Ubicación del primer impacto del vehículo      | Categórico   |
| Vehicle Second Impact Location | Ubicación del segundo impacto del vehículo     | Categórico   |
| Vehicle Body Type          | Tipo de carrocería del vehículo                    | Categórico   |
| Vehicle Movement           | Movimiento del vehículo al momento del accidente    | Categórico   |
| Vehicle Continuing Dir     | Dirección continua del vehículo                    | Categórico   |
| Vehicle Going Dir          | Dirección del vehículo                             | Categórico   |
| Speed Limit                | Límite de velocidad en el lugar del accidente      | Numérico    |
| Driverless Vehicle         | Indicador si el vehículo era autónomo              | Booleano     |
| Parked Vehicle             | Indicador si el vehículo estaba estacionado         | Booleano     |
| Vehicle Year               | Año de fabricación del vehículo                   | Numérico    |
| Vehicle Make               | Marca del vehículo                                | Categórico   |
| Vehicle Model              | Modelo del vehículo                               | Categórico   |
| Equipment Problems         | Problemas con el equipo del vehículo               | Categórico   |
| Latitude                   | Latitud del lugar del accidente                   | Numérico    |
| Longitude                  | Longitud del lugar del accidente                  | Numérico    |
| Location                   | Ubicación geográfica (latitud, longitud)        | Geográfica  |

## Propuestas de análisis

**Predecir la gravedad de un accidente:**

* **Objetivo:** Saber si un accidente será grave o no.
* **Columnas posibles de utilizar:** `Collision Type`, `Speed Limit`, `Traffic Control`, `Vehicle Damage Extent`, `Weather`, `Surface Condition`, `Light`, `Driver Substance Abuse`, `Driver Distracted By`, `Drivers License State`, `Crash Date/Time`.

## Análisis Exploratorio de Datos y Modelado Predictivo de Severidad de Accidentes

**Archivo:** accident_severity_analysis.ipynb

**Descripción:** Este notebook contiene un análisis exploratorio de datos y el desarrollo de modelos de aprendizaje automático para predecir la severidad de las lesiones en accidentes de tráfico. El conjunto de datos utilizado se describe en el archivo "dataset_description.ipynb". 

**1. Preprocesamiento de Datos:**

- Se eliminaron columnas consideradas irrelevantes para el análisis, como información de identificación, ubicación geográfica detallada y problemas del vehículo. 
- Se imputaron los valores faltantes en las columnas utilizando la moda.
- Se codificaron las variables categóricas utilizando LabelEncoder.

**2. Análisis de la Distribución de Clases:**

- Se encontró un desequilibrio significativo en la variable objetivo "Injury Severity", con la clase "NO APPARENT INJURY" siendo la más frecuente.

**3. Entrenamiento y Evaluación de Modelos:**

- Se entrenaron y evaluaron los siguientes modelos de clasificación:
    - XGBoost
    - Extra Trees Classifier
    - Decision Tree
    - Random Forest
    - Support Vector Machine (SVM)
    - LightGBM
    - CatBoost
    - HistGradientBoostingClassifier

**4. Métricas de Evaluación:**

- Se utilizaron las siguientes métricas para evaluar el rendimiento de los modelos:
    - Matriz de confusión
    - Accuracy
    - Precision (promedio ponderado)
    - Recall (promedio ponderado)
    - F1 Score (promedio ponderado)
    - Reporte de Clasificación 

**5. Resultados:**

- Todos los modelos presentaron un accuracy superior al 80%. 
- Sin embargo, las métricas de precision, recall y F1-score fueron significativamente más bajas para las clases minoritarias, especialmente "FATAL INJURY" y "SUSPECTED SERIOUS INJURY", debido al desequilibrio de clases.

**6. Conclusiones:**

- El desequilibrio de clases afecta negativamente la capacidad de los modelos para predecir correctamente las clases minoritarias, que son las de mayor importancia en este contexto.