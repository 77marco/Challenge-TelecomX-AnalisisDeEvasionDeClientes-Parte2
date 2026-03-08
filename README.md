# Challenge Telecom X: Análisis de Evasión de Clientes (Churn) - Parte 2

Desarrollo de modelos de Machine Learning para predecir la evasión de clientes (Churn), como parte del Challenge Telecom X de la formación Oracle Next Education y Alura LATAM.

## 🎯 1. Propósito del Análisis
El objetivo principal de este proyecto es **predecir el churn (cancelación de servicio)** de los clientes de la empresa de telecomunicaciones ficticia "Telecom X". A través de la aplicación de algoritmos de Machine Learning, buscamos identificar patrones en el comportamiento y características de los usuarios para anticipar su salida, permitiendo a la gerencia tomar decisiones estratégicas de retención basadas en datos reales.

## 📁 2. Estructura del Proyecto
El repositorio está organizado de la siguiente manera para facilitar su revisión y reproducción:
* `TelecomX_Parte2.ipynb`: Cuaderno principal de Jupyter (Colab) que contiene todo el código ejecutable, desde la exploración hasta la evaluación de modelos.
* `README.md`: Documentación principal del proyecto.
* *(Nota: Los datos tratados y visualizaciones se generan dinámicamente durante la ejecución del cuaderno).*

## ⚙️ 3. Proceso de Preparación de los Datos
Para garantizar que los modelos matemáticos funcionaran correctamente, los datos originales pasaron por un riguroso preprocesamiento:
1. **Clasificación y Codificación (Encoding):** Las variables categóricas fueron transformadas a valores numéricos (0 y 1) para que los algoritmos pudieran interpretarlas.
2. **Balanceo de Clases (SMOTE):** Se detectó un desbalance donde solo el ~26% de la base representaba cancelaciones. Se aplicó la técnica *Oversampling* (SMOTE) para crear datos sintéticos y equilibrar las clases al 50/50, evitando así que el modelo generara sesgos predictivos.
3. **Estandarización (StandardScaler):** Se normalizaron las variables numéricas continuas (como `Cargos_Totales` y `Meses_Contrato`) para que tuvieran la misma escala. Esto fue crucial para que el modelo de Regresión Logística (basado en distancias) no le diera falsa prioridad a las columnas con números más grandes.
4. **Separación de Datos (Train/Test):** El conjunto de datos se dividió en **80% para entrenamiento y 20% para prueba**, asegurando que los modelos tuvieran un "examen final" con datos nunca antes vistos para comprobar su verdadero aprendizaje.

## 📊 4. Insights y Modelado Predictivo
Se entrenaron dos algoritmos (Regresión Logística y Random Forest) y se extrajo la importancia de las variables para el negocio.

**Resultados del Modelado:**
* **Regresión Logística:** Fue el modelo elegido como ganador por su alta estabilidad. Logró una exactitud general superior al 82% tanto en entrenamiento como en prueba, demostrando una excelente capacidad de generalización sin sufrir de subajuste ni sobreajuste.
* **Random Forest:** Aunque obtuvo métricas ligeramente superiores en prueba, presentó un fuerte problema de *Overfitting* (sobreajuste), memorizando el 99.8% de los datos de entrenamiento pero bajando su rendimiento al 84% en la prueba.

**Principales Descubrimientos de Negocio:**
* **Riesgo en Fibra Óptica:** Es el servicio que más empuja a los clientes a la cancelación, sugiriendo problemas de precio o calidad técnica.
* **Ciclo de Vida:** El mayor riesgo de fuga se concentra en los primeros meses. Contratos a uno o dos años reducen la evasión casi a cero.
* **Sensibilidad al Costo:** Cargos mensuales altos sin servicios de protección adicionales fomentan la salida del cliente.

## 🚀 5. Instrucciones de Ejecución
Para ejecutar este proyecto en tu entorno local o en Google Colab, necesitarás las siguientes bibliotecas:
* `pandas` / `numpy`: Manipulación y análisis de estructuras de datos.
* `matplotlib` / `seaborn`: Generación de gráficos (Heatmaps, Boxplots, Barplots).
* `scikit-learn`: Estandarización, métricas y entrenamiento de los modelos predictivos.
* `imbalanced-learn`: Aplicación de la técnica SMOTE para el balanceo de clases.

**Pasos para ejecutar:**
1. Clona este repositorio o abre el archivo `TelecomX_Parte2.ipynb` en Google Colab.
2. Asegúrate de tener las librerías instaladas (en Colab puedes ejecutar `!pip install imbalanced-learn` si es necesario).
3. Ejecuta las celdas en orden secuencial desde arriba hacia abajo. El código se encarga de importar las librerías necesarias automáticamente.
