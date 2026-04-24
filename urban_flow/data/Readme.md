
# Conclusión del Sprint 1

El análisis sobre el dataset `speeding_fines` mostró que los datos heredados
tenían problemas serios de calidad. De las 4.000 filas originales se terminaron
conservando 1.713 multas válidas: 1.982 fueron descartadas por falta de datos
mínimos (patente, velocidad registrada o velocidad máxima) y 305 por no
presentar infracción real una vez aplicada la tolerancia del 5%.

Además, un 26,44% del dataset final mantiene la fecha por defecto 1932-01-01
y un 19,79% mantiene la hora por defecto 00:00, porque las fechas y horas
originales venían mal formadas. Eso explica por qué el gráfico de meses
muestra enero con un pico muy por encima del resto: es principalmente el
efecto del default 1932-01-01, no un comportamiento real del tránsito.

En los gráficos de líneas, al excluir el default opuesto en cada filtro, se
observa que cuando se toman solo las multas con hora 00:00 la serie temporal
arranca recién en 2020, y que cuando se toman solo las multas con fecha
1932-01-01 los excesos se concentran en el rango horario de 08 a 20 hs. Esto
sugiere que los defaults no están distribuidos al azar sino asociados a
registros con problemas de captura entre 2020 y 2024 y en horarios diurnos.

Respecto de la distribución real de las multas válidas, los excesos
promedian 39,3 km/h (con tolerancia) y 42,3 km/h sin tolerancia. Las
avenidas Libertador y Siempre Viva concentran la mayor parte de las
infracciones, y el top de patentes reincidentes encabezado por WEFLYN, con
38 multas, muestra que existe un grupo pequeño de conductores con
comportamiento repetidamente infractor.

La principal recomendación para la migración al nuevo sistema es asegurar
la validación en origen de fecha, hora, patente y velocidades, dado que de
lo contrario un cuarto de los registros sigue perdiendo información
temporal aprovechable para el análisis.
