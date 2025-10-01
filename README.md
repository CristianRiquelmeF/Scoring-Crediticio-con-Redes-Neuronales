[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1j_6VjKO0z8HyBtsvohtg0C8_HvARxTWN?authuser=2)

# Sistema Inteligente de Scoring Crediticio con Redes Neuronales

## Resumen  
Las entidades financieras se enfrentan constantemente al desafío de decidir si otorgan o no un crédito. Un error en esta decisión puede significar una pérdida económica para la institución o una exclusión injusta para un cliente. Este proyecto implementa un modelo de **scoring crediticio** utilizando el dataset **German Credit Data**. El objetivo es predecir si un cliente representa un **buen** o **mal riesgo de crédito**, aplicando técnicas de **Machine Learning moderno** para mejorar precisión, robustez y explicabilidad. Además se aborda el desafío de la "caja negra", utilizando técnicas de Explicabilidad de IA (XAI) como LIME para que las decisiones del modelo sean transparentes y auditables por un equipo de riesgo bancario.

El notebook incluye:  
- **Análisis exploratorio de datos (EDA)**.  
- **Manejo de desbalance** de clases con **SMOTE**.  
- **Comparación de modelos**:  
  - Red neuronal profunda (DNN simple).  
  - Arquitectura ResNet para datos tabulares.  
- **Evaluación de desempeño** con métricas estándar.  
- **Explicabilidad** mediante LIME para interpretar decisiones individuales.

---

## Dataset  
Se utilizó el **German Credit Data**, compuesto por 1000 observaciones con variables categóricas y numéricas que describen información financiera, historial crediticio y características personales.

- Variable objetivo: **Good Credit (1)** / **Bad Credit (0)**.  
- Notoria presencia de **desbalanceo de clases**, resuelto con SMOTE.  

---

## Modelos y Técnicas  
1. **DNN simple**:  
   - Varias capas densas con activación ReLU.  
   - Regularización con Dropout.  

2. **ResNet para tabulares**:  
   - Conexiones residuales para mejorar la propagación de gradientes.  
   - Mejor desempeño en general.  

3. **Callbacks aplicados**:  
   - `EarlyStopping`.  
   - `ReduceLROnPlateau`.  

## Librerías Principales
    - TensorFlow / Keras
    - Scikit-learn
    - SHAP
    - LIME
    - Pandas
    - NumPy
    - Matplotlib / Seaborn
---

## Resultados  

- El **modelo ResNet** superó a la DNN simple en métricas de precisión y recall.  
- SMOTE permitió balancear el dataset, reduciendo sesgos hacia la clase mayoritaria.  
- Se logró una clasificación confiable de clientes de buen/mal crédito.  

### Ejemplo de gráficos incluidos en el notebook:

#### Distribución de la variable objetivo
<img width="500" height="300" alt="distribucion_target" src="https://github.com/user-attachments/assets/1ee33723-4c6d-4674-a3f3-1e7936d32f79" />


#### Curvas de entrenamiento (Loss y Accuracy)
<img width="500" height="300" alt="curva_loss" src="https://github.com/user-attachments/assets/6d488fd4-7a64-473b-90a1-18acebd9dae2" />

<img width="500" height="300" alt="curva_accuracy" src="https://github.com/user-attachments/assets/4abd94c7-ee1c-417f-9501-697ac8d7497d" />


#### Explicación con LIME para un cliente
<img width="500" height="797" alt="lime_explicacion" src="https://github.com/user-attachments/assets/5120db78-8d65-45a5-a0dd-a1a3ad30becf" />


---

## Explicabilidad  
Se utilizó **LIME** para entender qué variables influyen en la predicción de cada cliente.  
Ejemplo: un cliente con **93% probabilidad de crédito bueno** se explica por factores como **historial de pagos** y **duración del crédito**.  

---

## Conclusión  
El proyecto demuestra cómo aplicar **Deep Learning moderno (ResNet)** en problemas de **scoring crediticio**, mejorando rendimiento frente a modelos simples y ofreciendo explicaciones interpretables con LIME.  

---
> Proyecto desarrollado como parte de portafolio de Machine Learning avanzado.
---
