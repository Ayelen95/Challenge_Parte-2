 # 📊 Análisis de Deserción de Clientes en Telecom (Parte 2)

![Python](https://img.shields.io/badge/Python-3.9+-blue)
![Pandas](https://img.shields.io/badge/Data-Pandas-150458)
![Scikit-Learn](https://img.shields.io/badge/MachineLearning-ScikitLearn-orange)
![Seaborn](https://img.shields.io/badge/Visualization-Seaborn-green)
![Status](https://img.shields.io/badge/Project-Churn%20Analysis-success)

 ## 📌 Descripción del Proyecto

Este proyecto aplica modelos de Machine Learning (Logistic Regression, Random Forest, Gradient Boosting, Extra Trees y Support Vector Machine) para predecir si un cliente se dará de baja.



## 📂 Estructura del Proyecto

```text
📁 Challenge_Parte-2/
│
├── images                           # Imágenes de graficos en formato .png
├── datos_tratados.csv               # Dataset en formato .csv
├── TelecomX_parte2_dao.ipynb        # Notebook principal con análisis y gráficos
└── README.md                        # Documentación del proyecto
```


## ▶️ Cómo Ejecutar el Proyecto

🔹Abrir Google Colab

🔹Subir el archivo .ipynb

🔹Ejecutar todas las celdas (Runtime > Run all).



## 🤖 Modelos implementados para Predicción de Churn

En este proyecto se utilizo **5 algoritmos de Machine Learning** utilizando **3 enfoques para manejar el desbalanceo de clases**.


## 🧠 Modelos utilizados

* Logistic Regression
* Random Forest
* Gradient Boosting
* Extra Trees
* SVM

## ⚖️ Enfoques evaluados

1. Modelo **normal**
2. Modelo con **class_weight="balanced"**
3. Modelo entrenados con **SMOTE**

Estos enfoques permiten analizar cómo afectan distintas técnicas de balanceo al rendimiento de los modelos.


## 🔬 Metodología

## 📥 1. Carga de Datos y Preprocesamiento
En esta etapa, importamos el dataset limpio y preparamos las variables.

- **Dataset utilizado:** `datos_tratados.csv`
- **Variable Objetivo (Target):** `Churn` (Yes/No)

- Se aplicó un análisis de asociación ($\chi^2$) para eliminar variables categóricas irrelevantes.
- Se realizó limpieza de datos y codificación de variables categóricas mediante **One-Hot Encoding**
- Se analizaron relaciones entre variables mediante **matriz de correlación** y análisis exploratorio.


## ✂️ 2. División de Datos (Train / Test Split)

- **Conjunto de Entrenamiento (Train):** 80% de los datos. Se utiliza para enseñar al modelo.
- **Conjunto de Prueba (Test):** 20% de los datos. Se mantiene intacto y con su desbalance original para evaluar el rendimiento final.


## ⚙️ 3. Entrenamiento de Modelos

Se entrenaron los modelos utilizando tres enfoques:

- Dataset original
- Modelos con **class_weight**
- Dataset balanceado mediante **SMOTE**

Esto permitió comparar cómo afectan las técnicas de balanceo al rendimiento de cada algoritmo.


## 📊 4. Evaluación y Resultados
Los modelos se evaluaron utilizando las siguientes métricas:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

En problemas de **churn**, es especialmente importante el **Recall**, ya que permite identificar la mayor cantidad posible de clientes que podrían cancelar el servicio.

También se analizaron las **matrices de confusión** para entender el comportamiento de los modelos.



## 📈 Mejores Modelos

Los modelos con mejor rendimiento fueron:

| Modelo | Enfoque | Característica |
|------|------|------|
| Gradient Boosting | Normal | Mejor ROC-AUC |
| Logistic Regression | Class Weight | Mejor Recall |
| Gradient Boosting | SMOTE | Buen equilibrio |



## 🔍 Interpretación de Resultados

El análisis mostró que algunos factores influyen en la cancelación de clientes:

- **Menor tiempo de permanencia (Tenure)** aumenta la probabilidad de churn.
- **Contratos mensuales** presentan mayor tasa de cancelación.
- **Cargos mensuales más altos** pueden asociarse con mayor churn.
- Clientes con **más servicios adicionales** tienden a permanecer más tiempo.



## 🏆 Modelo Recomendados:

- **Gradient Boosting → mejor rendimiento general**
- **Logistic Regression → mejor detección de clientes en riesgo**



## 📌 Conclusión

Los modelos de Machine Learning permiten identificar patrones asociados al churn y ayudan a anticipar la cancelación de clientes.  

Esta información puede utilizarse para implementar estrategias de retención más efectivas y mejorar la relación con los clientes.

---
## 👩‍💻 Autora
Ayelén (Angie) Desarrolladora en formación — Programa Alura Latam 2026

## ⭐ Contribuciones
Las contribuciones son bienvenidas. Si deseas mejorar gráficos, optimizar código o agregar nuevos análisis, puedes abrir un issue o un pull request.

## 🎓 Agradecimientos y Créditos
Este análisis es el resultado del tercer desafío técnico del programa Oracle Next Education. Agradezco a Alura Latam por la formación brindada en "Estadísticas y Machine Learning G9-ONE".