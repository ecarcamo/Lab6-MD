# Lab 6 - Minería de Datos: Modelos KNN

Este proyecto consiste en la implementación, optimización y análisis de algoritmos de **K-Nearest Neighbors (KNN)** para tareas de regresión (predicción de precios) y clasificación (categorización de precios) utilizando un dataset de Airbnb.

## Contenido del Proyecto
- Preprocesamiento de datos y manejo de valores faltantes.
- Optimización de hiperparámetros mediante `GridSearchCV`.
- Evaluación de modelos de regresión y clasificación.
- Análisis comparativo con modelos previos (Árbol de Decisión, Random Forest, Naive Bayes).

## Requisitos
- Python 3.9+
- Bibliotecas: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `pyreadr`.

## Instalación de dependencias
```bash
pip install -r requirements.txt
```

## Resultados del Laboratorio 6 (KNN)

### Optimización de Hiperparámetros
Para ambos modelos (Regresión y Clasificación), los mejores parámetros encontrados fueron:
- **n_neighbors**: 15
- **weights**: 'distance'
- **p**: 1 (Distancia de Manhattan)

La distancia de Manhattan resultó superior a la Euclidiana debido a la alta dimensionalidad del dataset y la presencia de outliers en los precios.

### Desempeño del Modelo KNN

#### Regresión (Predicción de Precio)
| Métrica | Valor en Test |
| :--- | :--- |
| RMSE | 2807.71 |
| MAE | 483.17 |
| R² | 0.5661 |

#### Clasificación (Categoría de Precio)
| Métrica | Valor en Test |
| :--- | :--- |
| Accuracy | 0.6657 |
| F1-Score | 0.6629 |

### Análisis Comparativo
- **Eficacia**: El modelo **Random Forest** sigue siendo el más robusto para la predicción de precios (menor RMSE). KNN muestra un buen R², pero su RMSE es sensible a los outliers extremos del dataset.
- **Eficiencia**: KNN es significativamente más lento en la fase de predicción en comparación con Naive Bayes y Árboles de Decisión, ya que debe calcular distancias contra todo el conjunto de entrenamiento.

## Archivos Principales
- `main.ipynb`: Notebook con el desarrollo completo.
- `listings.RData`: Dataset original.
- `metricas_modelos.json`: Registro de métricas de modelos anteriores.
