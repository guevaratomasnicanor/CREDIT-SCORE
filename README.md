# CREDIT-SCORE AND DEFAULT PREDICTION
https://www.kaggle.com/datasets/conorsully1/credit-score
El dataset contiene 1000 observaciones con 84 variables financieras de los individuos. Las variables objetivo son CREDI_SCORE y DEFAULT

Otras variables son: 
INCOME, SAVINGS, DEBT, R_SAVINGS_INCOME, R_DEBT_INCOME, R_DEBT_SAVINGS, CAT_GAMBLING, CAT_CREDIT_CARD, CAT_MORTGAGE, CAT_SAVINGS_ACCOUNT, CAT_DEPENDENTS

#INSIGHTS
Comportamientos de personas en default:
-	Los clientes en default destinan una proporción mucho mayor de sus ahorros a educación. 
- Quienes caen en default mantienen relación deuda/ingresos y deuda/ahorro mucho mayor, lo que refleja vulnerabilidad financiera y sobreendeudamiento.	
-	Incremento fuerte en multas en los últimos 6 meses. Posible indicador de comportamiento desorganizado o inestabilidad económica reciente.	
-	Alta proporción de multas respecto a ahorros. Puede reflejar poca capacidad de pago ante gastos imprevistos.
-	Gastan más en alimentos relativo a sus ahorros, indicando presión en gastos básicos y bajo margen de ahorro.	
- Mayor proporción de personas con tarjeta de crédito entre los morosos

Las variables con mas correlación con el credit score son:
- Ratio deuda/ingreso(85,8%), dueda/ahorro(45%), y deuda ,todas impactan negativamente en la puntuacion.
- ratio de consumo/deuda, utilidades/deuda e impuestos/deuda tienen 30% de correlacion positiva. Implica que pueden sostener consumo y pagar impuestos sin endeudarse, ademas de estar mejor controlados financieramente.

