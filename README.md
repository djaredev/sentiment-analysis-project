🐬 Delfin project
# Implementación y análisis de desempeño de técnicas de aprendizaje automático para el análisis de sentimientos

## 📝 Requisitos:
- Dataset [sentiment140](https://www.kaggle.com/datasets/kazanova/sentiment140)
- Vector de representacion de palabras [glove](https://nlp.stanford.edu/projects/glove/)

## 🤖 Tecnicas analisadas:
- Large Language Model (LLM)
- Support Vertor Machine (SVM)
- Long Short-Term Memory (LSTM)

## 📄 Resumen:

Los datos usados para realizar las pruebas fue el dataset sentiment140 una base de datos  muy utilizada en análisis de sentimientos, el dataset contiene 1,600,000 tweets extraídos directo de la API de Twitter que están etiquetados con dos clases diferentes (0 = negativo, 4 = positivo). 
A los  datos se les aplicó técnicas de preprocesamiento de datos para limpiarlos, estandarizarlos y adecuarlos para el uso en los modelos a excepción de el LLM ya que este cuenta con su propia capa que hace este proceso.

Algo a destacar del preprocesamiento realizado es que se usó incrustación de palabras (Word embeddings) para representar las palabras en forma de vectores, una técnica muy efectiva a la hora de vectorizar las palabras ya que los embeddings capturan relaciones semánticas y sintácticas además tiene una representación densa y de baja dimensión.

## 📊 Resultados:
Para evaluar los modelos se usaron las métricas que se basan en la matriz de confusión que se genera a partir de los datos que predijo el modelo y los datos reales, tanto BERT como el modelo LSTM fueron entrenados durante 8 epochs.

**Accuracy (Exactitud):** Esta métrica mide que también es la predicción en comparación con los datos reales.
En esta métrica el mejor modelo fue BERT con una accuracy de 84% durante el entrenamiento y 83% con los datos de prueba, seguido por la red LSTM con una accuracy 84% durante el entrenamiento y 82% con los datos de prueba, por último la SVM con una accuracy con los datos de prueba de 75%.

**Precisión:** Esta métrica mide de todas las instancias que el modelo predice para una clase especifica, cuántas  son realmente de esa clase.
En esta métrica el mejor modelo fue BERT con una precisión de 83% en la clase negativa y 84% en la clase positiva, seguido por el modelo LSTM con una precisión de 82% en la clase negativa y 83% en la clase positiva, por último la SVM con una precisión de 75% y 76% respectivamente.

**Recall (Sensitivity):** Esta métrica mide la capacidad del modelo para predecir una clase específica correctamente.
En esta métrica tanto BERT como LSTM tuvieron un recall de 84% en la clase negativa pero un 82% y 81% en la clase positiva respectivamente, por último la SVM con una precisión de 76% en la clase negativa y 75% en la positiva.

**F1-Score:** Es una métrica que combina la precisión y el recall en un solo valor proporcionando una medida equilibrada del rendimiento del modelo.
En esta métrica tanto BERT como LSTM tuvieron un f1-score de 83% en la clase negativa pero un 83% y 82% en la clase positiva respectivamente, por último la SVM con una precisión de 76% en la clase negativa y 75% en la positiva.

### ✅ Conclusiones:

En general los modelos BERT y LSTM tiene un rendimiento muy similar en todas las métricas en las que se les evaluó, pero con grandes diferencias en cuanto al consumo computacional y al tamaño siendo el modelo LSTM el de mayor tamaño con un total de 40,686,000 parámetros con un consumo en memoria de 155.20 MB mientras que el modelo BERT tuvo un tamaño total de 4,386,178 parámetros con un consumo en memoria de 16.73 MB teniendo en cuenta que BERT cuenta con diferentes tamaños de parámetros, siendo al que se le realizó fine tuning en esta investigación el más pequeño de todos, por lo que con un modelo similar de tamaño al modelo LSTM usado se podría tener un mejor rendimiento. 
Por otro lado, SVM rinde peor, está por debajo en todas las métricas en comparación con los otros 2 modelos, también, es el que menos tiempo de ejecución necesito, además de que tiene menos consumo computacional en comparación con los otros modelos.


En conclusión hacer fine tuning a un LLMs resultó mejor y más fácil que que crear una red LSTM customizada, preprocesar los datos y manejar incrustaciones de palabras, etc, por otro lado técnicas como SVM son más simples y más rápidas pero con un rendimiento inferior.


Los LLMs son una gran alternativa a las técnicas más conocidas, para afrontar problemas de análisis de sentimientos, ya que estos modelos han sido entrenados con grandes cantidades de texto y estos pueden ser ajustados a muchas tareas relacionadas con el NLP.




