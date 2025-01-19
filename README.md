# Predicción de riesgo de incendio forestal en España: Proyecto GAIA

Este repositorio guarda el primer test que se ha hecho en el proyecto GAIA para predecir el riesgo de incendio forestal a nivel Español. El objetivo final de esta sección del proyecto GAIA es obtener un predictor de riesgo de incendio forestal diario en toda España. Este trabajo es un primer test para comprobar que la metodología seguida y los datos usados son los correctos.

El trabajo se ha hecho en un archivo `.ipynb` y se ha transformado a PDF. El informe completo está disponible aquí: [main.pdf](/src/main.pdf).

## Conclusiones del trabajo
En este trabajo se ha hecho una primera prueba de predicción del riesgo de incendio forestal siguiendo la metodología que se pretende aplicar en el Trabajo final de Fin de Máster. Se han obtenido muy buenos modelos que han sido capaces de predecir correctamente el 87% de todos los incendios y con un ROC-AUC del 0.9, solamente utilizando datos que cambian muy poco en el tiempo. Sin embargo, cabe recalcar que los modelos se han testado en conjuntos de datos muy balanceados comparando con la distribución real de los datos, cosa que favorece el rendimiento de los modelos. En un escenario real, donde los datos están desbalanceados debido a que los incendios forestales son eventos raros en comparación con la ausencia de incendios, el rendimiento de los modelos se vería muy mermado. Sin embargo, al ser esta una primera prueba que no incluye los factores que más afectan a los incendios (precipitaciones, temperatura y viento) ni pretende ser un buen predictor diario de riesgo de incendio forestal, no hay que preocuparse por testar en un conjunto de datos desbalanceado.

Este ejercicio ha servido para ver que vamos por el buen camino con la metodología seguida y testar qué tanto y cómo afectan en el riesgo de incendio forestal las variables atemporales que se han introducido. Esto se ha hecho mediante los "SHAP values" y "permutation feature importance". Además, el análisis profundo de los datos que se ha seguido en este trabajo ha servido para encontrar nuevas variables muy importantes como la variable `forest_percent`, y encontrar patrones interesantes en los datos al hacer "outlier detection". Se ha descubierto que las Islas Canarias se consideran como "outliers" por lo que en el trabajo final puede ser interesante hacer un predictor para la península y otro para las Islas Canarias.

En resumen, aunque los resultados preliminares son alentadores, queda un camino significativo por recorrer para adaptar y optimizar la metodología a los objetivos que tenemos. Los pasos futuros incluirán la incorporación de variables con temporalidad diaria como la `temperatura`, las `precipitaciones`, índices de vegetación como el `NDVI` y índices de riesgo de incendio forestal como el `FWI`. También se entrenaran modelos más sofisticados de `Deep Learning` introduciendo contexto temporal y espacial mediante los cuales se esperan obtener buenos resultados en conjuntos de test con distribuciones desbalanceadas reales.

## Ejemplo de predicciones del modelo

![Alt text](/data/figures/prediccion_agosto.png)

![Alt text](/data/figures/prediccion_noviembre.png)
