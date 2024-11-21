# Don't Stop Me Now / (Pandas + Looker Studio)
## Introducción
La actividad física es fundamental para nuestra profesión, despeja la mente, haces cable a tierra, regresas con más energía y muchas veces con la solución que estabas buscando o con una perspectiva más interesante. Después de 15 años y acusando 40 tacos decidí volver a correr para tener una alternativa a salir en bicicleta (mi otra pasión). En este proyecto haré el análisis de los datos recolectados en mi primer año con la app Runkeeper.

## Extracción de datos y exploración
Runkeeper provee diferentes archivos en formato: `csv`, `json` y `gpx`. El primer paso es cargar los archivos: `steps.csv` y `cardioActivities.csv`, utilizando Pandas. `Steps` contiene 12.259 entradas y 3 columnas, incluyendo información como 'Activity Id', ' Timestamp', ' Steps'. `cardioActivities` contiene 287 registros y 14 columnas tales como 'Activity Id', 'Date', 'Type', 'Route Name', 'Distance (km)', 'Duration', 'Average Pace', 'Average Speed (km/h)', etc. Los primeros pasos de la inspección empleo métodos como head() e info().

## Transformación y Limpieza de Datos
* Primero extraeremos el total de pasos por `Activity Id` del dataframe de Steps para fusionarlo a nuestro dataset general de Activities.
* Eliminamos las columnas ("Route Name", "Average Heart Rate (bpm)", "Friend's Tagged", "Notes", "GPX File") de Activities.
* Convertimos `Average Pace`, `Duration` y `Date` a timedelta y datetime. Finalmente convertimos `Average Pace` a float. 
* Extracción del total de steps por actividad.
* Unión de ambos dataframes.
  

### *Under construction*
