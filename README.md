 ## 📈 Predicción de Abandono de Clientes (Customer Churn)

Este proyecto aplica modelos de Machine Learning (Regresión Logística y Random Forest) para predecir si un cliente de telecomunicaciones se dará de baja, permitiendo tomar medidas de retención proactivas.

---

## 📥 1. Carga de Datos y Preprocesamiento
En esta etapa, importamos el dataset limpio y preparamos las variables.
- **Dataset utilizado:** `datos_tratados.csv`
- **Variable Objetivo (Target):** `Churn` (Yes/No)
- Se aplicó un análisis de asociación ($\chi^2$) para eliminar variables categóricas irrelevantes.

---

## 🪓 2. División de Datos (Train / Test Split)
Para evitar el sobreajuste (overfitting) y garantizar que el modelo se evalúe en escenarios del "mundo real", dividimos los datos **antes** de aplicar cualquier técnica de balanceo.

- **Conjunto de Entrenamiento (Train):** 70% de los datos. Se utiliza para enseñar al modelo.
- **Conjunto de Prueba (Test):** 30% de los datos. Se mantiene intacto y con su desbalance original para evaluar el rendimiento final.

> **Nota sobre el Balanceo (SMOTE):** Dado que la variable objetivo presentaba un fuerte desbalance (73.5% No / 26.5% Yes), se aplicó la técnica SMOTE *exclusivamente* al conjunto de entrenamiento para generar datos sintéticos de la clase minoritaria.

---

## 🧠 3. Entrenamiento de Modelos
Se probaron y entrenaron los siguientes algoritmos de clasificación utilizando el conjunto de datos balanceado (`X_train_smote`, `y_train_smote`):

1. **Regresión Logística:** Modelo base interpretable.
2. **Random Forest Classifier:** Modelo de ensamble basado en árboles de decisión para capturar relaciones no lineales.

---

## 📊 4. Evaluación y Resultados
El rendimiento de los modelos se midió sobre el conjunto de prueba (`X_test`, `y_test`). En el negocio de las telecomunicaciones, el costo de perder un cliente (Falso Negativo) es mayor que el costo de enviarle una promoción innecesaria (Falso Positivo). Por lo tanto, la métrica principal a optimizar es el **Recall de la clase "Yes"**.

### Matriz de Confusión y Métricas Clave
*(Aquí puedes insertar las imágenes de tus matrices de confusión)*

- **Regresión Logística:** Logró un Recall del **X%**, logrando detectar a **X** clientes en riesgo de fuga.
- **Random Forest:** Alcanzó un Recall del **X%**, detectando a **X** clientes.

**Conclusión:** El modelo seleccionado es **[Nombre del Modelo]**, ya que demostró la mayor capacidad para identificar correctamente a los clientes propensos al abandono, minimizando los casos que el sistema "dejó pasar".