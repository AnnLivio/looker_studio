# Don't Stop Me Now / (Pandas + Looker Studio)
## Introducción
La actividad física es fundamental para nuestra profesión, despeja la mente, haces cable a tierra, regresas con más energía y muchas veces con la solución que estabas buscando o con una perspectiva más interesante. Después de 15 años y acusando 40 tacos decidí volver a correr para tener una alternativa a salir en bicicleta (mi otra pasión). En este proyecto haré el análisis de los datos recolectados en mi primer año con la app Runkeeper.

## Extracción de datos y exploración
Runkeeper provee diferentes archivos en formato: `csv`, `json` y `gpx`. El primer paso es cargar los archivos: `steps.csv` y `cardioActivities.csv`, utilizando Pandas.
* **Steps:** contiene 12.259 entradas y 3 columnas, incluyendo información como 'Activity Id', ' Timestamp', ' Steps'.
* **cardioActivities:** contiene 287 registros y 14 columnas tales como 'Activity Id', 'Date', 'Type', 'Route Name', 'Distance (km)', 'Duration', 'Average Pace', 'Average Speed (km/h)', etc.
En los primeros pasos de la inspección empleo métodos como head() e info().

## Transformación y Limpieza de Datos
+ Extraemos el total de pasos por `Activity Id` del dataframe de Steps para fusionarlo a nuestro dataset general de Activities.
+ Eliminamos las columnas ("Route Name", "Average Heart Rate (bpm)", "Friend's Tagged", "Notes", "GPX File") de Activities.
+ Convertimos `Average Pace`, `Duration` y `Date` a timedelta y datetime. Finalmente convertimos `Average Pace` a float. 
+ Extracción del total de steps por actividad.
+ Unión de ambos dataframes.
  
## Análisis Exploratorio de los Datos
(Fichero/File: `analisis_exploratorio.ipynb`)

Datos correspondientes sólo al primer año desde el comienzo de la actividad.

Respondiendo algunas preguntas:
+ Top 3 carreras más largas
+ Top 3 carreras más rápidas
+ Top 5 carreras con mayor desnivel positivo
+ Total kms corridos en el primer año
+ Desnivel positivo acumulado en todo el año

Extracción de datos y cálculos para evaluar la evolución
Observaciones finales.

## Predicciones
(Fichero/File: `running_forecast.ipynb`)

Datos completos desde finales de Junio de 2023 hasta principios de Noviembre de 2024 

Tras finalizar la limpieza y transformación de los datos, excluimos los datos correspondientes a `Cycling` y `Walking`.
Agrupamos los datos semanalmente para poder crear el modelo predictivo.
Imputamos valores faltantes en Junio para que no afecten las predicciones.
Creación y entrenamiento del modelo.
Realizamos nuestras predicciones y obtenemos métricas.
Extraigo los datos semanales para comparar con las predicciones realizadas en Google Sheets.

