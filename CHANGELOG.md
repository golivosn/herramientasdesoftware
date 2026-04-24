# CHANGELOG

## Día 1
Estructura de carpetas, rama `Sprint_1`, imports, variables globales y `desactivar_git_push`.

## Día 2
Descarga del dataset a `data/raw/` e inspección inicial (`head`, `dtypes`, nulos).

## Día 3
Normalización de fechas, horas, ubicaciones y patentes sobre una copia del dataframe.

## Día 4
Eliminación de filas sin datos mínimos para ser una multa válida (`patente`, `velocidad_registrada`, `velocidad_maxima`) con la leyenda pedida.

## Día 5
Detección y eliminación de outliers por IQR sobre `velocidad_registrada` y `velocidad_maxima` con la leyenda pedida.

## Día 6
Columnas `exceso_velocidad_real` (sin tolerancia) y `exceso_velocidad` (con 5% de tolerancia sobre la velocidad máxima).

## Día 7
Filtrado de filas sin infracción usando `exceso_velocidad > 0`.

## Día 8
Exportación del dataset limpio a `urban_flow/data/interim/speeding_fines.csv`.

## Día 9
Clase `FineAnalyzer`: encapsula el dataframe limpio y expone rankings, promedios de exceso y conteo por ubicación.

## Día 10
Instanciación del analizador y llamada a cada método en celdas separadas.

## Día 11
Gráficos de top patentes (`fines.jpg`), porcentaje de infracciones por hora (`hours.jpg`) y cantidad por mes (`months.jpg`) en `data/interim/plots/`.

## Día 12
Gráficos de líneas para los excesos filtrados por hora `00:00` (`hour.jpg`) y por fecha `1932-01-01` (`date.jpg`), con la interpretación documentada en el notebook.

## Día 13
Arreglo de `hour.jpg` y `date.jpg`: se excluye el default opuesto en cada filtro y se agrupa `date.jpg` por hora del reloj (0–23) para que el eje X quede legible.

## Día 14
Reordenamiento del notebook: se reubica el Ejercicio 04 antes del Punto 05, se restaura la clase `FineAnalyzer` que se había perdido por colisión de IDs y se elimina un markdown duplicado de Punto 05.

## Día 15
Punto 06: porcentajes de infracciones con los valores por defecto (`1932-01-01` y `00:00`) usando la leyenda pedida.

## Día 16
Estilo: indentación de todas las celdas de código a 2 espacios y se cortan líneas que excedían 80 caracteres, siguiendo la consigna.

## Día 17
Ajustes de consigna: `months.jpg` queda ordenado descendente de mayor a menor (con el mayor visualmente arriba) y la columna del ranking de patentes pasa a llamarse `patentes` (plural) como pide el enunciado del Ejercicio 04.
