# Telecom X - Parte 2: Predicción de Churn

[![Status](https://img.shields.io/badge/status-en%20progreso-blue.svg)](https://img.shields.io/badge/status-en%20progreso-blue.svg)

## 🎯 Propósito

Predecir qué clientes de **Telecom X** tienen mayor probabilidad de
cancelar sus servicios (churn) usando Machine Learning, para que la
empresa pueda anticiparse y tomar acciones de retención.

## 📁 Estructura del proyecto

📁 main/
├── 📓 Challenge_TelecomX_LATAM_Part2.ipynb  
├── 📊 datos_tratados.csv                    
├── 📄 README.md                            

## 🛠️ Preparación de datos

1. **Eliminé** `CustomerID` (no aporta valor predictivo)
2. **Simplifiqué** servicios de internet: `'No internet service'` → `'No'`
3. **Codificación**: OneHotEncoder con `drop='first'` en variables categóricas
4. **Escalado**: StandardScaler en variables numéricas
5. **Split**: 80% entrenamiento / 20% prueba (estratificado por churn)

## 🤖 Modelos entrenados

- **Logistic Regression** → modelo baseline interpretable
- **Random Forest** → modelo principal por mejor desempeño

## 📊 Insights EDA (en progreso)

Principales factores asociados al churn identificados:

- Contratos `Month-to-month`
- Clientes sin servicios adicionales (OnlineSecurity, TechSupport)
- Método de pago `Electronic check`
- Clientes con poco tiempo de permanencia (tenure bajo)

## 🚀 Cómo ejecutar

Instalar dependencias:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

Cargar los datos en el notebook:

import pandas as pd
df = pd.read_csv('datos_tratados.csv')

Ejecutar el notebook telecomx_churn.ipynb de forma secuencial
desde la primera celda.

## 📝 Conclusión
Proyecto desarrollado como parte del Challenge de Data Science de Alura
LATAM. El modelo final permite identificar clientes en riesgo de
cancelación para orientar estrategias de retención en Telecom X.

Autor: Renzo Luza
Challenge: Telecom X - Parte 2 | Alura Data Science LATAM                   
