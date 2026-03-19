# 🏠 Predictor de Alquileres - Buenos Aires

Modelo de Machine Learning para estimar precios de alquiler en CABA usando datos de Properati.

## Stack
- **Data**: Pandas, NumPy
- **ML**: scikit-learn, XGBoost
- **Visualización**: Matplotlib, Seaborn, Folium
- **Deploy**: Streamlit

## Setup

```bash
# Clonar y entrar al repo
git clone https://github.com/tu-usuario/alquileres-bsas.git
cd alquileres-bsas

# Crear entorno virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows

# Instalar dependencias
pip install -r requirements.txt
```

## Datos

Descargá el dataset de Properati desde Kaggle:
- [Properati Data - Buenos Aires](https://www.kaggle.com/datasets/properati/properati-data)
- Guardá el CSV como `data/properati_raw.csv`

## Uso

### 1. Exploración (notebook)
```bash
jupyter notebook notebooks/01_eda.ipynb
```

### 2. Entrenar modelos
```bash
cd src
python train.py
```
Esto entrena Linear Regression, Random Forest y XGBoost, compara métricas, y guarda el mejor modelo en `data/`.

### 3. Correr la app
```bash
streamlit run app.py
```

## Estructura

```
alquileres-bsas/
├── data/
│   ├── properati_raw.csv      # Dataset crudo
│   ├── best_model.joblib      # Modelo entrenado
│   ├── scaler.joblib           # Scaler
│   ├── model_meta.json         # Metadata del modelo
│   └── experiments.json        # Log de experimentos
├── notebooks/
│   └── 01_eda.ipynb
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   └── predict.py
├── app.py
├── requirements.txt
├── .env
└── README.md
```

## Métricas

Los resultados se loguean automáticamente en `data/experiments.json` después de cada corrida de entrenamiento.
