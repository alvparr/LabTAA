# Práctica 2 – Análisis y Clustering de Marcha Humana

Este proyecto tiene como objetivo analizar trayectorias de marcha humana y aplicar técnicas de aprendizaje no supervisado (clustering) para agrupar patrones de movimiento. Se trabaja con un conjunto de datos estructurado por persona (`sub_XX`), donde cada subcarpeta contiene archivos CSV que representan trayectorias registradas.

## Estructura del proyecto

### 1. Extracción y preparación de datos
- Se recorren las carpetas por persona y se cargan todas las trayectorias CSV.
- Se concatenan en un único DataFrame por persona.
- Se normalizan usando `RobustScaler` para reducir el efecto de outliers y diferencias físicas entre sujetos (como altura o proporciones corporales).

**¿Por qué `RobustScaler`?**  
A diferencia de `StandardScaler` o `Normalizer`, `RobustScaler` utiliza la mediana y el rango intercuartílico (IQR), lo que lo hace menos sensible a valores extremos, permitiendo que el clustering se base en el comportamiento corporal y no en el tamaño del cuerpo.

### 2. Reducción de dimensionalidad
- Se aplican técnicas como PCA (Análisis de Componentes Principales) para facilitar la visualización y mejorar la eficiencia del clustering.

### 3. Clustering
- Se implementa K-Means.
- Se exploran diferentes configuraciones de parámetros y métricas de evaluación.

### 4. Visualización
- Resultados del clustering y análisis de componentes se muestran gráficamente para facilitar la interpretación.
- Se generan gráficos en 2D y 3D con etiquetas por cluster.

## Requisitos

- Python 3.8+
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
