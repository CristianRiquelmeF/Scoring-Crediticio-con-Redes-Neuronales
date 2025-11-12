[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1j_6VjKO0z8HyBtsvohtg0C8_HvARxTWN?authuser=2)

# Sistema Inteligente de Scoring Crediticio con Redes Neuronales

## Resumen  
Las entidades financieras se enfrentan constantemente al desafío de decidir si otorgan o no un crédito. Un error en esta decisión puede significar una pérdida económica para la institución o una exclusión injusta para un cliente. Este proyecto implementa un modelo de scoring crediticio utilizando el dataset German Credit Data. El objetivo es predecir si un cliente representa un buen o mal riesgo de crédito, aplicando técnicas avanzadas de Deep Learning (específicamente, Redes Neuronales Densas y arquitecturas ResNet) para mejorar la precisión y robustez.
Dado que los modelos de Deep Learning actúan como una "caja negra", un pilar de este proyecto es la Explicabilidad de IA (XAI). Se utilizan técnicas como LIME para asegurar que las decisiones del modelo sean transparentes, interpretables y auditables por un equipo de riesgo bancario.

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

- SMOTE permitió balancear el dataset, reduciendo sesgos hacia la clase mayoritaria.  
- Los experimentos demuestran que, para este conjunto de datos, el modelo DNN Simple (Accuracy: 76%) superó en rendimiento general al modelo ResNet (Accuracy: 69%).Más importante aún para el contexto del negocio (riesgo bancario), la DNN Simple mostró una capacidad significativamente mayor para identificar correctamente a los clientes de "Crédito Malo" (Clase 1), alcanzando un Recall de 0.78 (frente al 0.70 del ResNet).
- Dado que el costo de un "Falso Negativo" (aprobar un crédito malo) es muy alto, el modelo DNN Simple se perfila como la solución más robusta y efectiva para este problema. Este modelo sería el candidato ideal para ser auditado en detalle con LIME antes de un despliegue productivo.

### Ejemplo de gráficos incluidos en el notebook:

#### Distribución de la variable objetivo
<img width="500" height="300" alt="distribucion_target" src="https://github.com/user-attachments/assets/1ee33723-4c6d-4674-a3f3-1e7936d32f79" />


#### Comparación de modelos

<img width="1380" height="980" alt="image" src="https://github.com/user-attachments/assets/c135770a-3cef-4c18-b421-2dd4b87d2e4b" />


#### Explicación con LIME para un cliente
<img width="500" height="797" alt="lime_explicacion" src="https://github.com/user-attachments/assets/5120db78-8d65-45a5-a0dd-a1a3ad30becf" />


---

## Explicabilidad  
Se utilizó **LIME** para entender qué variables influyen en la predicción de cada cliente.  
Ejemplo: un cliente con **93% probabilidad de crédito bueno** se explica por factores como **historial de pagos** y **duración del crédito**.  

---

## Conclusión  
Los resultados muestran que el modelo DNN Simple alcanzó un desempeño general superior al modelo ResNet, pero en conjunto, los experimentos demuestran que las redes neuronales profundas pueden ser una alternativa viable para el scoring crediticio, combinando precisión aceptable y explicabilidad mediante herramientas XAI como LIME.

---
> Proyecto desarrollado como parte de portafolio de Machine Learning avanzado.
---
