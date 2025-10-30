# diabetes-ml-prediction

# 🩺 Predicción de Riesgo de Diabetes con Machine Learning

Este proyecto desarrolla un modelo predictivo para estimar el riesgo de desarrollar diabetes tipo 2 utilizando datos clínicos y de estilo de vida. Se implementan y comparan dos algoritmos de Machine Learning supervisado: **Random Forest Classifier** y **Gradient Boosting Classifier**.

---

## 🎯 Objetivo

- Identificar factores clave asociados al riesgo de diabetes  
- Entrenar modelos predictivos para clasificación binaria (diabetes sí/no)  
- Evaluar el desempeño de modelos y realizar predicciones sobre nuevos pacientes  
- Simular casos clínicos para validar comportamiento del modelo  

---

## 📊 Dataset y Variables

Variables principales utilizadas en el modelo:

| Variable | Descripción |
|---|---|
| `age` | Edad |
| `physical_activity_minutes_per_week` | Minutos semanales de actividad física |
| `bmi` | Índice de Masa Corporal |
| `glucose_fasting` | Glucosa en ayunas |
| `glucose_postprandial` | Glucosa postprandial |
| `hba1c` | Hemoglobina glicosilada |
| `diabetes_risk_score` | Score compuesto de riesgo |

Variable objetivo:
- `diagnosed_diabetes` (0 = no diabetes, 1 = diabetes)

---

## ⚙️ Modelos Entrenados

### Random Forest
- Captura relaciones no lineales y maneja variables con distintas escalas

### Gradient Boosting
- Basado en boosting secuencial, corrige errores del modelo previo

---

## ✅ Resultados

| Modelo | Accuracy | Precision | Recall | F1-Score |
|---|---|---|---|---|
| Random Forest | 0.92125 | 0.99896 | 0.87056 | 0.93035 |
| Gradient Boosting | 0.92175 | 1.0 | 0.87048 | 0.93076 |

Ambos modelos presentaron métricas robustas, con especial rendimiento en la identificación de casos positivos.

---

## 🧪 Predicción con Casos Simulados

Se evaluaron perfiles simulados para validar la coherencia clínica del modelo:

| Caso | Perfil | Predicción | Probabilidad Diabetes |
|---|---|---|---|
| 1 | Joven, activo, glucosa normal | No | 5% aprox |
| 2 | Adulto, actividad moderada, glucosa intermedia | No | 12% aprox |
| 3 | Mayor, sobrepeso, glucosa alta | **Sí** | **~99.99%** |

El modelo predijo correctamente los niveles de riesgo esperado en cada escenario.

---

## 💾 Exportación del Modelo

El modelo fue guardado utilizando `joblib`:

```python
joblib.dump(rf, "../../src/modelo_random_forest.pkl")
joblib.dump(gradient_b, "../../src/modelo_gradient_boosting.pkl")
