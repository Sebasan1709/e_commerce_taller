🛍️ Predicción de Intención de Compra a partir de Clickstream (E-Shop 2008)

Este proyecto desarrolla un proceso completo de Machine Learning aplicado a datos de navegación (clickstream) para predecir si una sesión de usuario visitará la página de Ofertas (Sale) en un e-commerce de ropa.

Incluye:

Limpieza y transformación del log de clicks

Construcción de un dataset a nivel sesión

Feature engineering evitando data leakage

Entrenamiento de 4 modelos base

Comparación de métricas

Optimización con Optuna

Interpretabilidad del modelo

Recomendación de negocio basada en datos

🚀 Objetivo del Proyecto

Predecir si un usuario visitará la página de ofertas (page 1 = 4), identificando comportamiento de "buscadores de descuentos". Este insight permite:

Activar personalización en tiempo real

Mejorar campañas de remarketing

Incrementar las conversiones hacia productos en descuento

Entender patrones de navegación útiles para el área de marketing

📂 Estructura del Proyecto
📦 e-commerce-clickstream-ml
│
├── data/
│   └── e-shop clothing 2008.csv
│
├── notebooks/
│   └── clickstream_analysis.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── modeling.py
│   ├── optuna_tuning.py
│   └── utils.py
│
├── plots/
│   ├── metrics_barplot.png
│   ├── xgboost_vs_optuna.png
│
├── README.md
└── requirements.txt

🧹 1. Preprocesamiento y Feature Engineering

El dataset original está a nivel click, por lo que se transforma a nivel sesión, generando features agregadas:

total_clicks

avg_price_seen

max_price_seen

distinct_products

countries

main_category_mode

Target
Visited_Sale_Page = 1 si la sesión visitó la categoría 4 (sale)

Prevención de Data Leakage

Antes de agregar features se excluyen los clicks donde page 1 = 4.

🤖 2. Modelos Entrenados

Modelos evaluados:

Logistic Regression

Decision Tree

Random Forest

XGBoost

Pipeline usado en todos:

ColumnTransformer

Escalado

Imputación

OneHotEncoding

📊 3. Comparación de Resultados
Modelo	Accuracy	F1	ROC-AUC	Precision	Recall
Logistic Regression	0.678	0.224	0.654	0.579	0.138
Decision Tree	0.654	0.358	0.542	0.471	0.289
Random Forest	0.621	0.406	0.575	0.427	0.388
XGBoost	0.613	0.497	0.643	0.439	0.572
XGBoost Optuna	0.622	0.533	0.669	0.454	0.646

📌 Modelo ganador: XGBoost optimizado con Optuna.

🔧 4. Optimización con Optuna

Hiperparámetros optimizados:

n_estimators

max_depth

learning_rate

subsample

colsample_bytree

min_child_weight

gamma

Validación cruzada con:

StratifiedKFold(n_splits=3)


Métrica de objetivo:

F1 Score

🧩 5. Importancia de Variables (XGBoost)

Top 3 factores:

distinct_products – Usuarios que comparan más productos tienden a visitar ofertas.

main_category_mode_3 – La categoría skirts tiene mayor probabilidad de generar visitas a Sale.

total_clicks – Sesiones muy activas muestran más intención de buscar descuentos.

💼 6. Recomendación de Negocio

Mostrar un banner dinámico de “Ofertas”
para usuarios que navegan muchos productos distintos.

Campañas específicas para usuarios interesados en “skirts”
ya que muestran mayor sensibilidad al precio.

Activar mensajes contextuales en sesiones muy activas
sugiriendo ofertas relevantes cuando detecten alto engagement.

Estas acciones permiten guiar a usuarios con intención alta hacia ofertas, mejorando conversión y experiencia.

🧪 7. Requisitos
pandas
numpy
scikit-learn
xgboost
optuna
matplotlib
seaborn


Instalación:

pip install -r requirements.txt

▶️ 8. Ejecución
python src/preprocessing.py
python src/modeling.py
python src/optuna_tuning.py


O desde el notebook:

notebooks/clickstream_analysis.ipynb

🌱 9. Próximos Pasos

Añadir interpretabilidad con SHAP

Probar LightGBM como baseline adicional

Crear API con FastAPI para scoring

Agregar monitoreo de modelo

Si quieres, puedo generarte ahora:

una versión en inglés,

una versión más minimalista,

o una versión estilo profesional corporativo.
