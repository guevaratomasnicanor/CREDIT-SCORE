# 🧮 Credit Score and Default Prediction

📊 **Dataset:** [Credit Score](https://www.kaggle.com/datasets/conorsully1/credit-score)  
📁 **Observaciones:** 1,000  
📈 **Variables:** 84 (financieras y demográficas)  
🎯 **Variables objetivo:** `CREDIT_SCORE` y `DEFAULT`

---

## 🧠 Descripción general

El dataset contiene información financiera detallada de individuos, incluyendo ingresos, ahorros, deudas, relaciones entre variables financieras y categorías socioeconómicas.  
El objetivo principal es **predecir el puntaje crediticio** (`CREDIT_SCORE`) y **la probabilidad de default** (`DEFAULT`).

---

## 📌 Variables destacadas

| Tipo | Variable | Descripción |
|------|-----------|-------------|
| Numérica | `INCOME` | Ingreso mensual del individuo |
| Numérica | `SAVINGS` | Monto total de ahorros |
| Numérica | `DEBT` | Monto total de deudas |
| Relacional | `R_SAVINGS_INCOME` | Ahorros en relación a ingresos |
| Relacional | `R_DEBT_INCOME` | Deuda en relación a ingresos |
| Relacional | `R_DEBT_SAVINGS` | Deuda en relación a ahorros |
| Categórica | `CAT_GAMBLING` | Presencia de gastos en juego/apuestas |
| Categórica | `CAT_CREDIT_CARD` | Posee tarjeta de crédito |
| Categórica | `CAT_MORTGAGE` | Tiene hipoteca |
| Categórica | `CAT_SAVINGS_ACCOUNT` | Posee cuenta de ahorros |
| Categórica | `CAT_DEPENDENTS` | Tiene dependientes económicos |

---

## 💡 Principales insights

### 🔻 Comportamientos asociados al *default*
- Los clientes en **default** destinan una proporción mucho mayor de sus ahorros a **educación**.  
- Presentan **ratios deuda/ingreso** y **deuda/ahorro** considerablemente más altos → *indican vulnerabilidad financiera y sobreendeudamiento.*  
- Se observa un **incremento notable en multas** durante los últimos 6 meses → posible reflejo de **desorganización financiera** o **inestabilidad reciente.**  
- Muestran una **alta proporción de multas respecto a ahorros**, sugiriendo poca capacidad para enfrentar gastos imprevistos.  
- Gastan **más en alimentos en relación a sus ahorros**, lo que indica **presión en gastos básicos** y bajo margen de ahorro.  
- Mayor proporción de personas con **tarjeta de crédito** entre los morosos.

<div align="center">
  <img width="700" src="https://github.com/user-attachments/assets/02ebca1a-df05-4b9f-83e6-7cac7c51f853" alt="Default Behaviors Visualization">
</div>

---

## 📈 Variables más correlacionadas con el *Credit Score*

| Variable | Correlación | Interpretación |
|-----------|--------------|----------------|
| `R_DEBT_INCOME` | -0.86 | Una mayor deuda relativa a los ingresos reduce significativamente el puntaje crediticio. |
| `R_DEBT_SAVINGS` | -0.45 | Niveles altos de deuda respecto a ahorros también impactan negativamente. |
| `DEBT` | -0.33 | El endeudamiento total está inversamente relacionado con el crédito. |
| `R_EXPENDITURE_DEBT`, `R_UTILITIES_DEBT`, `R_TAX_DEBT` | +0.30 | Una mejor capacidad para sostener consumo y pagar impuestos sin endeudarse refleja **mayor control financiero**. |

<div align="center">
  <img width="700" src="https://github.com/user-attachments/assets/b85a23d0-7d91-4399-b008-b90e2f6b9ba5" alt="Credit Score Correlations Visualization">
</div>

## 📊 Métricas de los Modelos

| Modelo   | RMSE     | MAE      | R²     | MAPE (%) |
|----------|----------|----------|--------|----------|
| Random Forest (RF) | 28.7810 | 22.1175 | 0.8110 | 4.02 |
| XGBoost  | 27.7407 | 21.1174 | 0.8249 | 3.69 |
| LightGBM (LGBM) | 28.4413 | 20.8972 | 0.8135 | 3.78 |
 
XGBoost se posiciona como el mejor modelo entre los evaluados, ya que presenta el menor error en RMSE, MAE y MAPE, junto con el mayor poder explicativo (R²).
En términos prácticos, la diferencia promedio entre el valor real y el predicho es de 3,69%, lo que equivale aproximadamente a 22 puntos de score crediticio.
Además, el modelo logra explicar cerca del 82,5% de la variabilidad observada en los datos, ofreciendo un equilibrio sólido entre precisión, estabilidad y capacidad predictiva, lo que lo convierte en la opción más confiable para su implementación en un entorno de negocio.


<img width="1340" height="692" alt="Captura de pantalla 2025-11-16 210854" src="https://github.com/user-attachments/assets/bf89c5c5-219d-4589-9df3-a89a19bff9c1" />

Los puntos representan las coordenadas de valor real vs valor predicho, lo ideal es que estos puntos se encuentren dentro de la recta ya que esto significaría que el modelo se acerca a lo real. La mayoría de puntos se encuentran dentro de la banda de error.


📈 Impacto de Negocio y Simulación Financiera a 3 Años
Para evaluar el impacto real del modelo y evitar el sesgo común de compararlo contra un escenario irreal (como prestarle a todos a tasa fija), enfrentamos a XGBoost contra las dos mejores alternativas del negocio: una Regla Heurística basada en el score tradicional de mercado (CapEx $0) y un Scorecard tradicional automatizado mediante Regresión Logística Lasso (CapEx $15M). La simulación se proyectó a 3 años bajo una tasa de crecimiento bancario real del 4.9% anual y una tasa de descuento corporativa del 15%, aplicando políticas actuariales homogéneas donde las tasas y montos se ajustaron estrictamente al riesgo de default de cada banda de clientes.

Los resultados financieros demostraron que XGBoost es la única estrategia óptima, consolidando un Valor Actual Neto (VAN) de $3.410 millones y triturando a sus competidores. El modelo tradicional Lasso destruyó valor debido a su ceguera lineal en las bandas medias de riesgo (VAN de $2.551M), quedando incluso por debajo de la regla heurística elemental (VAN de $2.987M). XGBoost aportó un valor incremental neto de +$423.091.224 frente al rival más fuerte, demostrando que su capacidad para cruzar de forma no lineal las 80 variables reduce drásticamente el error de clasificación y maximiza la captura de margen.

A pesar del fuerte impacto inicial de los $40 millones de inversión tecnológica (CapEx) en el Año 0 y los $8 millones anuales de mantenimiento (OpEx), el proyecto se paga solo. La precisión del algoritmo para colocar más monto a quienes realmente van a pagar permite recuperar la inversión incremental antes del sexto mes. Además, el modelo valida la escalabilidad del software a largo plazo: a medida que el volumen de solicitudes crece orgánicamente con el mercado bancario, los flujos netos de XGBoost se expanden exponencialmente mientras sus costos fijos de mantenimiento tecnológico permanecen congelados.
