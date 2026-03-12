# 📡 TelecomX LATAM — Predicción de Churn (Parte 2)

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![Status](https://img.shields.io/badge/Status-Completado-green)

## 📋 Descripción del Proyecto

Este proyecto forma parte del Challenge de Data Science de **Alura LATAM**. El objetivo es predecir la **cancelación de clientes (churn)** de la empresa Telecom X, utilizando técnicas de machine learning para identificar los factores que más influyen en que un cliente abandone el servicio.

---

## 🗂️ Estructura del Repositorio

| Archivo | Descripción |
|---|---|
| `Challenge_TelecomX_LATAM_Parte2.ipynb` | Notebook principal con todo el análisis |
| `README.md` | Descripción del proyecto |
| `TelecomX_diccionario.md` | Diccionario de variables del dataset |
| `datos_tratados.csv` | Dataset procesado listo para modelado |

---

## 🎯 Objetivos

- Preparar y limpiar los datos para el modelado predictivo
- Analizar la correlación entre variables y el churn
- Entrenar y evaluar modelos de clasificación
- Identificar los factores principales de cancelación
- Proponer estrategias de retención basadas en los resultados

---

## 🔧 Tecnologías Utilizadas

| Librería | Uso |
|---|---|
| `pandas` | Manipulación de datos |
| `numpy` | Operaciones numéricas |
| `matplotlib` / `seaborn` | Visualización de datos |
| `scikit-learn` | Modelado de machine learning |
| `scipy` | Prueba estadística Chi-cuadrado |

---

## 📊 Pipeline del Proyecto

### 1. Preparación de Datos
- Carga del dataset `datos_tratados.csv`
- Eliminación de columna `customerID`
- Encoding de variables categóricas con `pd.get_dummies`
- Análisis de distribución del churn con `value_counts`
- Balanceo de clases con `class_weight='balanced'`
- Escalado de variables con `StandardScaler`

### 2. Análisis de Correlación
- Heatmap de correlación entre variables numéricas
- Crosstab + Chi-cuadrado para variables categóricas
- Selección de variables más relevantes para el modelo

### 3. Modelado Predictivo

| Modelo | Accuracy | Recall Churn | Seleccionado |
|---|---|---|---|
| Regresión Logística (balanceada) | 74% | 0.79 | ✅ Sí |
| Random Forest | — | — | — |

> La **Regresión Logística Balanceada** fue seleccionada como modelo final por su alto recall en churn (0.79), lo que significa que detecta correctamente al 79% de los clientes que cancelarán. En este problema de negocio, minimizar los falsos negativos es más importante que la precisión general.

### 4. Interpretación y Conclusiones
- Análisis de coeficientes de la Regresión Logística
- Importancia de variables del Random Forest
- Informe estratégico con recomendaciones de retención

---

## 🔍 Principales Hallazgos

Los factores con mayor impacto en la cancelación de clientes son:

1. **Tipo de contrato** → Clientes *Month-to-month* tienen ~43% de churn vs ~3% en contratos anuales
2. **Método de pago** → *Electronic check* registra la mayor tasa de cancelación (~45%)
3. **Antigüedad (tenure)** → Clientes nuevos de 0 a 12 meses son los más propensos a cancelar
4. **Senior Citizens** → Adultos mayores cancelan ~42% vs ~24% en no seniors
5. **Servicios adicionales** → Clientes sin *OnlineSecurity* ni *TechSupport* presentan mayor riesgo

---

## 💡 Estrategias de Retención Recomendadas

| Problema detectado | Acción recomendada |
|---|---|
| Contratos mensuales | Ofrecer descuento para migrar a plan anual |
| Pago por Electronic check | Incentivar pago automático con beneficios exclusivos |
| Clientes nuevos (0-12 meses) | Programa de onboarding y acompañamiento |
| Senior Citizens | Plan especial con soporte dedicado y simplificado |
| Sin servicios adicionales | Bundle de seguridad + soporte técnico con descuento |

---

## 👤 Autor
Renzo Luza — Challenge Data Science, Alura LATAM



             
