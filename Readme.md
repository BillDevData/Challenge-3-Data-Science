# Proyecto Telecom X - Parte 2

## Objetivo del análisis
El objetivo principal de este proyecto es **predecir la cancelación de clientes (churn)** de la empresa Telecom. A partir de variables relevantes, buscamos identificar patrones de comportamiento que permitan anticipar qué clientes tienen mayor riesgo de abandonar el servicio y apoyar decisiones estratégicas para reducir la evasión.

## Estructura del proyecto
El proyecto se organiza de la siguiente manera:
+ Notebook del challenge 3
+ Base de datoa: datos_procesados.csv
+ Archivo Readme

## Preparación de los datos
1. **Clasificación de variables**:  
   - Categóricas: género, tipo de contrato, método de pago, servicios contratados, entre otras.  
   - Numéricas: tenure, cargos mensuales, booleanas transformadas a numéricas.

2. **Normalización y codificación**:  
   - Variables categóricas se codificaron con One-Hot Encoding.  
   - Variables numéricas fueron normalizadas para modelos sensibles a escala, como KNN.

3. **Separación de conjuntos**:  
   - Los datos se dividieron en conjuntos de entrenamiento (80%) y prueba (20%).  
   - Se realizó **oversampling** para balancear la variable objetivo `Churn` y mejorar la capacidad predictiva sobre clientes que cancelan.

## Modelización
Se probaron tres modelos de Machine Learning:  
- **Random Forest Classifier**  
- **Logistic Regression**  
- **K-Nearest Neighbors (KNN)**  

Se seleccionó Random Forest como modelo principal debido a su desempeño balanceado y capacidad para manejar variables categóricas codificadas y normalizadas sin necesidad de escalado adicional. La justificación se basó en métricas de precisión, recall y f1-score, además de la facilidad de interpretar la importancia de las variables.

## Análisis Exploratorio de Datos (EDA)
Durante el EDA se generaron gráficos como:  
- Boxplots de `Charges.Monthly` y `tenure` vs. `Churn`  
- Mapas de calor de correlación para identificar relaciones fuertes  
- Visualizaciones de la importancia de variables para cada modelo  

Estos análisis permitieron identificar insights como:  
- Clientes con contratos mensuales son más propensos al churn.  
- Métodos de pago electrónicos están asociados a mayor cancelación.  
- Clientes con poco tiempo como clientes y cargos altos presentan mayor riesgo.

## Ejecución del cuaderno
Instalar las bibliotecas necesarias:  
```bash
pip install pandas numpy matplotlib seaborn scikit-learn

## Bibliotecas utilizadas
- `pandas` – manipulación de datos  
- `numpy` – cálculos numéricos  
- `matplotlib` – visualización de gráficos  
- `seaborn` – visualización estadística  
- `scikit-learn` – modelado, normalización, evaluación (`LogisticRegression`, `RandomForestClassifier`, `KNeighborsClassifier`, `train_test_split`, `StandardScaler`, `classification_report`, `confusion_matrix`)  
- `imblearn` – balanceo de clases (`RandomOverSampler`) 
