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
 

El mejor modelo es el XGBOOST, ya que tiene menos error en RMSE, MAE y MAPE, contando ademas con mayor r^2. La diferencia entre real y predicho es en promedio de 3,69%, o 22 puntos de score crediticio. El modelo explica un 82,5% de la variabilidad en los datos.
<img width="1340" height="692" alt="Captura de pantalla 2025-11-16 210854" src="https://github.com/user-attachments/assets/bf89c5c5-219d-4589-9df3-a89a19bff9c1" />
Los puntos representan las coordenadas de valor real vs valor predicho, lo ideal es que estos puntos se encuentren dentro de la recta ya que esto significaría que el modelo se acerca a lo real. La mayoría de puntos se encuentran dentro de la banda de error.

