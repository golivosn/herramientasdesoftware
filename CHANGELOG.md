# CHANGELOG

## Día 1

Se dejó armado el arranque del proyecto. Primero quedó creada la rama `Sprint_1` y la estructura de carpetas que pide la consigna, separando los datos crudos, los intermedios, los finales y la carpeta de gráficos. También se preparó el notebook con los imports iniciales, las variables globales y la lógica para controlar el `git push` con `desactivar_git_push`. La idea en este punto fue dejar una base prolija para no mezclar después la parte de setup con la parte de análisis.

## Día 2

En este avance ya se agregó la carga del dataset original dentro de `urban_flow/data/raw/speeding_fines.csv`. A partir de eso quedaron listas las primeras celdas de inspección: vista inicial de filas, revisión de tipos de datos y conteo de valores nulos. No hay limpieza todavía; por ahora el objetivo fue entender mejor el estado real del archivo antes de empezar a transformar columnas.
