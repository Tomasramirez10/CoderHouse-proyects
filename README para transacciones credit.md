# Detección de Fraude en Transacciones con Tarjetas de Crédito

Resumen del proyecto basado en [`credit_transactions_improved_v1.ipynb`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb).

## Objetivo
Desarrollar un pipeline reproducible y "production-ready" para detectar transacciones fraudulentas, priorizando recall y minimizando el costo económico de errores.

## Contenido
- Notebook principal: [Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb)
- Datos esperados: `fraudTest.csv` (colocar en la misma carpeta o usar `kagglehub` como se indica en el notebook)

## Requisitos
- Python 3.8+
- libs principales: pandas, numpy, scikit-learn, xgboost, lightgbm, category_encoders, geopy, shap, matplotlib, seaborn
- Instalar con: pip install -r requirements.txt (crear si es necesario)

## Flujo del Notebook
1. Cargar dataset (local o via kagglehub).
2. EDA y chequeos de calidad (nulos, tipos, balance de clases).
3. Feature engineering sin data leakage:
   - Temporal: `hour_trans`, `day_of_week`, `mes`.
   - Demográfico: `age`, `age_group`.
   - Geográfico: `dist_cliente_merch`.
   - Monto: `amt_log`, `monto_alto`, `monto_noche`.
   - Variables de grupo calculadas *después* del split: `amt_rel_cliente`, `transacciones_cliente`.
4. Preprocesamiento con `ColumnTransformer` (Target/Count encoding, KNNImputer, StandardScaler).
5. Búsqueda de hiperparámetros (GridSearchCV) sobre XGBoost / LightGBM.
6. Calibración de probabilidades (`CalibratedClassifierCV`) y optimización de threshold:
   - Métrica prioritaria: recall / F2-score.
   - Optimización por costo: minimizar (FP × $10) + (FN × $100).
7. Interpretabilidad con SHAP y simplificación a top N features.

## Variables y objetos clave
- Entrenamiento / split: [`X_train`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`y_train`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`X_test`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`y_test`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb)
- Pipeline / modelos: [`preprocessor`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`model// filepath: Ejemplos/Credit Card Transactions Fraud Detection Dataset/README.md
# Detección de Fraude en Transacciones con Tarjetas de Crédito

Resumen del proyecto basado en [`credit_transactions_improved_v1.ipynb`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb).

## Objetivo
Desarrollar un pipeline reproducible y "production-ready" para detectar transacciones fraudulentas, priorizando recall y minimizando el costo económico de errores.

## Contenido
- Notebook principal: [Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb)
- Datos esperados: `fraudTest.csv` (colocar en la misma carpeta o usar `kagglehub` como se indica en el notebook)

## Requisitos
- Python 3.8+
- libs principales: pandas, numpy, scikit-learn, xgboost, lightgbm, category_encoders, geopy, shap, matplotlib, seaborn
- Instalar con: pip install -r requirements.txt (crear si es necesario)

## Flujo del Notebook
1. Cargar dataset (local o via kagglehub).
2. EDA y chequeos de calidad (nulos, tipos, balance de clases).
3. Feature engineering sin data leakage:
   - Temporal: `hour_trans`, `day_of_week`, `mes`.
   - Demográfico: `age`, `age_group`.
   - Geográfico: `dist_cliente_merch`.
   - Monto: `amt_log`, `monto_alto`, `monto_noche`.
   - Variables de grupo calculadas *después* del split: `amt_rel_cliente`, `transacciones_cliente`.
4. Preprocesamiento con `ColumnTransformer` (Target/Count encoding, KNNImputer, StandardScaler).
5. Búsqueda de hiperparámetros (GridSearchCV) sobre XGBoost / LightGBM.
6. Calibración de probabilidades (`CalibratedClassifierCV`) y optimización de threshold:
   - Métrica prioritaria: recall / F2-score.
   - Optimización por costo: minimizar (FP × $10) + (FN × $100).
7. Interpretabilidad con SHAP y simplificación a top N features.

## Variables y objetos clave
- Entrenamiento / split: [`X_train`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`y_train`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`X_test`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`y_test`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb)
- Pipeline / modelos: [`preprocessor`](Ejemplos/Credit Card Transactions Fraud Detection Dataset/credit_transactions_improved_v1.ipynb), [`model
