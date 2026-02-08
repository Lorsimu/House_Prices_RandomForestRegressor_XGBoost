# House Prices: Advanced Regression Techniques

## Descripción
Este proyecto es una solución para la competición de Kaggle "House Prices: Advanced Regression Techniques". El objetivo es predecir el precio final de venta de viviendas residenciales en Ames, Iowa, utilizando 79 variables explicativas que describen casi todos los aspectos de las casas.

El enfoque principal se centra en un preprocesamiento de datos mediante **Pipelines** y la comparación de rendimiento entre dos modelos: **Random Forest** vs **XGBoost**.

## 🛠️ Tecnologías y Librerías
- **Python 3**
- **XGBoost:** Algoritmo principal seleccionado por su popularidad y eficacia.
- **Scikit-Learn:** - `Pipeline` y `ColumnTransformer` para un código limpio y reproducible.
  - `RandomForestRegressor` como modelo base para la comparación.
  - `OneHotEncoder` y `SimpleImputer` para el tratamiento de datos.
- **Pandas & NumPy:** Manipulación y análisis de datos.

## ⚙️ Metodología y Preprocesamiento

### 1. Tratamiento de Datos Faltantes
Se realizó un análisis detallado de los valores nulos:
- **Variables Numéricas:** Imputación utilizando la mediana.
- **Variables Categóricas:** Imputación constante ("Doesn't apply") para características donde la ausencia de dato simplica ausencia de la característica (ej: si no se tiene piscina, no hay dato de su calidad), seguido de codificación **One-Hot**.

### 2. Selección de Modelos
Se entrenaron y compararon dos enfoques distintos utilizando validación cruzada (k-fold para el modelo random forest) y métrica MAE (Mean Absolute Error):

* **Random Forest:** Se probó con 100 y 1000 estimadores.
* **XGBoost Regressor:** Se ajustó con `early_stopping` para evitar sobreajuste.

## 📊 Resultados
El modelo **XGBoost** superó significativamente al Random Forest, demostrando ser más efectivo para este dataset tabular complejo.

| Modelo | MAE (Error Medio Absoluto) |
| :--- | :--- |
| Random Forest (1000 trees) | ~17,912 |
| **XGBoost** | **~16,784** |

*El modelo final utilizado para la sumisión a Kaggle fue XGBoost.*

## 🚀 Instalación y Uso

1. Clonar el repositorio.
2. Instalar las dependencias necesarias:
   ```bash
   pip install -r requirements.txt

## ✒️ Autor
**Lorenzo Ji** - *Proyecto personal con recursos proporcionado por Kaggle*
* Perfil de GitHub: https://github.com/Lorsimu
* Correo académico: lorenzo.ji@estudiante.uam.es