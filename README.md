🧮 Credit Score and Default Prediction

📊 Dataset: Credit Score

📁 Observaciones: 1,000
📈 Variables: 84 (financieras y demográficas)
🎯 Variables objetivo: CREDIT_SCORE y DEFAULT

🧠 Descripción general

El dataset contiene información financiera detallada de individuos, incluyendo ingresos, ahorros, deudas, relaciones entre variables financieras y categorías socioeconómicas.
El objetivo principal es predecir el puntaje crediticio (CREDIT_SCORE) y la probabilidad de default (DEFAULT).

📌 Variables destacadas
Tipo	Variable	Descripción
Numérica	INCOME	Ingreso mensual del individuo
Numérica	SAVINGS	Monto total de ahorros
Numérica	DEBT	Monto total de deudas
Relacional	R_SAVINGS_INCOME	Ahorros en relación a ingresos
Relacional	R_DEBT_INCOME	Deuda en relación a ingresos
Relacional	R_DEBT_SAVINGS	Deuda en relación a ahorros
Categórica	CAT_GAMBLING	Presencia de gastos en juego/apuestas
Categórica	CAT_CREDIT_CARD	Posee tarjeta de crédito
Categórica	CAT_MORTGAGE	Tiene hipoteca
Categórica	CAT_SAVINGS_ACCOUNT	Posee cuenta de ahorros
Categórica	CAT_DEPENDENTS	Tiene dependientes económicos

💡 Principales insights
🔻 Comportamientos asociados al default

-Los clientes en default destinan una proporción mucho mayor de sus ahorros a educación.

-Presentan ratios deuda/ingreso y deuda/ahorro considerablemente más altos → indican vulnerabilidad financiera y sobreendeudamiento.

-Se observa un incremento notable en multas durante los últimos 6 meses → posible reflejo de desorganización financiera o inestabilidad reciente.

-Muestran una alta proporción de multas respecto a ahorros, sugiriendo poca capacidad para enfrentar gastos imprevistos.

-Gastan más en alimentos en relación a sus ahorros, lo que indica presión en gastos básicos y bajo margen de ahorro.

-Mayor proporción de personas con tarjeta de crédito entre los morosos.

<div align="center"> <img width="700" src="https://github.com/user-attachments/assets/02ebca1a-df05-4b9f-83e6-7cac7c51f853" alt="Default Behaviors Visualization"> </div>
📈 Variables más correlacionadas con el Credit Score
Variable	Correlación	Interpretación
R_DEBT_INCOME	-0.86	Una mayor deuda relativa a los ingresos reduce significativamente el puntaje crediticio.
R_DEBT_SAVINGS	-0.45	Niveles altos de deuda respecto a ahorros también impactan negativamente.
DEBT	-0.33	El endeudamiento total está inversamente relacionado con el crédito.
R_EXPENDITURE_DEBT, R_UTILITIES_DEBT, R_TAX_DEBT	+0.30	Una mejor capacidad para sostener consumo y pagar impuestos sin endeudarse refleja mayor control financiero.
<div align="center"> <img width="700" src="https://github.com/user-attachments/assets/b85a23d0-7d91-4399-b008-b90e2f6b9ba5" alt="Credit Score Correlations Visualization"> </div>

