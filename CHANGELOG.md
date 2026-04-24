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
