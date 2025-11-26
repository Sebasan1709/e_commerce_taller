# 🛍️ Predicción de Intención de Compra a partir de Clickstream (E-Commerce 2008)

Este proyecto desarrolla un proceso completo de **Machine Learning aplicado a datos de navegación (clickstream)** para predecir si una sesión de usuario visitará la página de **Ofertas (Sale)** en un e-commerce de ropa.

Incluye:

- Limpieza y transformación del log de clicks  
- Construcción de un dataset **a nivel sesión**  
- Feature engineering evitando *data leakage*  
- Entrenamiento de 4 modelos base  
- Comparación de métricas  
- Optimización con **Optuna**  
- Interpretabilidad del modelo  
- Recomendación de negocio basada en datos  

---

## 🚀 Objetivo del Proyecto

Predecir si un usuario visitará la página de ofertas (`page 1 = 4`), identificando comportamiento de "buscadores de descuentos". Esto permite:

- Activar personalización en tiempo real  
- Mejorar campañas de remarketing  
- Incrementar las conversiones hacia productos en descuento  
- Entender patrones de navegación útiles para el área de marketing  

---

## 📂 Estructura del Proyecto

```text
e-commerce-clickstream-ml
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
│   └── xgboost_vs_optuna.png
│
├── README.md
└── requirements.txt

