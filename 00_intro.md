# Introducción
# Un Marco de Interpretabilidad Multidimensional para la Detección de Anomalías en Series Temporales

El despliegue de modelos de aprendizaje automático en dominios críticos para la seguridad, como la aeronáutica y el sector aeroespacial, requiere un alto grado de transparencia para garantizar la confianza y la responsabilidad. Este *notebook* presenta una metodología exhaustiva para interpretar la detección de anomalías en datos de series temporales multivariantes orientada al mantenimiento predictivo.

## Objetivos

El propósito principal de este documento es proponer e ilustrar un marco de interpretabilidad multidimensional. Para ello, se aborda el problema de la naturaleza opaca o de caja negra de las redes neuronales profundas mediante la integración de tres técnicas de Inteligencia Artificial Explicable (XAI):

* **SHAP (SHapley Additive exPlanations):** Para comprender la contribución global y local de cada variable en las predicciones del modelo.
* **LIME (Local Interpretable Model-agnostic Explanations):** Para aproximar el comportamiento del modelo de forma local mediante modelos subyacentes más sencillos e interpretables.
* **Integrated Gradients (Gradientes Integrados):** Para obtener explicaciones con resolución temporal, identificando qué segmentos específicos de tiempo y características impulsan la predicción de una anomalía.

## Caso de Estudio y Metodología

Para validar y demostrar este enfoque, el *notebook* se estructura en torno al siguiente entorno experimental:

1.  **Conjunto de Datos:** Se utiliza el *dataset* **CMAPSS** de la NASA, un estándar en la industria que simula la degradación de motores turbofán operando bajo diversas condiciones, proporcionando datos de sensores multivariantes a lo largo de trayectorias completas hasta el fallo (*run-to-failure*).
2.  **Modelo de Detección:** El sistema de decisión subyacente es un modelo **LSTM (Long Short-Term Memory)**, ampliamente utilizado para capturar dependencias temporales complejas en la monitorización de la salud de los motores. El modelo identifica anomalías midiendo el Error Cuadrático Medio (MSE) de reconstrucción.
3.  **Análisis XAI:** A través del uso combinado de SHAP, LIME e Integrated Gradients, se desglosan las decisiones del modelo LSTM, demostrando cómo extraer explicaciones a nivel local, global y temporal.