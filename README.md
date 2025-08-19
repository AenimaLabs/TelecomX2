# 📊 Predicción de Cancelación de Clientes (Churn Prediction)

Este repositorio contiene un análisis completo para predecir la **cancelación de clientes (churn)** en una empresa de telecomunicaciones. El objetivo es **anticipar la cancelación** y permitir acciones proactivas de retención mediante modelos de machine learning.

---

## 🎯 Objetivo

Desarrollar modelos predictivos que identifiquen a los clientes con **mayor probabilidad de cancelar su servicio**, basado en características demográficas, de uso y contractuales.  
El enfoque está en **alta detección de abandono (recall)**, interpretabilidad y estrategias accionables de retención.

---

## 📁 Estructura del repositorio

TelecomX2/
│
├── Telecomx¿X2.ipynb # Notebook completo (Google Colab)
├── df_clean.csv
├── README.md



---

## 🧪 Modelos desarrollados

Se entrenaron y compararon dos modelos de machine learning:

| Modelo | Recall (clase 1) | F1-score (clase 1) | ROC-AUC | Escalamiento | Interpretable |
|-------|------------------|--------------------|---------|--------------|---------------|
| **Regresión Logística** | 0.79 | 0.62 | 0.8423 | ✅ Sí | ✅ Alta |
| **Random Forest** | 0.79 | 0.63 | 0.8424 | ❌ No | ⚠️ Media |

✅ **Ambos modelos alcanzan un recall del 79%**, lo que significa que **detectan casi 8 de cada 10 cancelaciones reales**.  
Ideal para sistemas de retención proactiva.

---

## 🔍 Variables más influyentes

Las principales variables que predicen la cancelación, identificadas por ambos modelos:

| Variable | Impacto | Interpretación |
|--------|--------|----------------|
| `Internet_Fibra Óptica` | ⬆️ Alto | Mayor riesgo: posibles problemas de servicio |
| `Contrato_Mes a mes` | ⬆️ Alto | Contrato flexible = fácil salida |
| `Meses_Contrato` | ⬇️ Bajo | Más tiempo = mayor estabilidad |
| `Streaming_TV` | ⬆️ Medio | Costo adicional sin uso frecuente |
| `Soporte_Tecnico` | ⬇️ Bajo | Reduce riesgo: valor agregado efectivo |
| `Seguridad_Online` | ⬇️ Bajo | Aumenta la percepción de valor |
| `Cargo_Mensual` | ⬇️ (contraintuitivo) | Planes caros pueden incluir más servicios y compromiso |

> 🔎 **Insight clave**: Los clientes con **fibra óptica** y **contrato mes a mes** son el segmento de **mayor riesgo**.

---

## 📈 Estrategias de retención propuestas

Basadas en el análisis de los modelos:

### 1. **Programa de retención para fibra óptica**
- Auditoría de calidad del servicio (velocidad, estabilidad)
- Soporte técnico proactivo
- Oferta de descuento por renovación a contrato anual

### 2. **Conversión de contratos mes a mes**
- Incentivos: 2-3 meses gratis al pasar a contrato de 1 o 2 años
- Alertas automáticas a clientes con >3 meses en plan flexible
- Campaña: “Estabilidad = Ahorro garantizado”

### 3. **Bienvenida proactiva para nuevos clientes**
- Seguimiento personalizado en los primeros 3 meses
- Guía de uso de servicios (especialmente streaming y seguridad)
- Soporte prioritario

### 4. **Optimización de servicios adicionales**
- Enviar encuesta de uso de streaming
- Si no lo usan, ofrecer downgrade sin penalización
- Promover paquetes combinados con descuento

### 5. **Sistema de alertas predictivas**
- Integrar modelo en CRM o sistema de atención
- Priorizar clientes con P(Abandono) > 70%
- Asignar a equipo de retención con script personalizado

---


