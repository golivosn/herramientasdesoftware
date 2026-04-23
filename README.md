# Urban Flow

Sprint 1.

Este trabajo arranca con un problema bastante típico: hay un dataset histórico de multas por exceso de velocidad que viene de un sistema viejo y los datos no están como para usarlos directo. La idea del sprint es ordenar primero la base del proyecto y después ir avanzando de a poco con la carga, la limpieza y el análisis.

Por ahora quedó armada la estructura de carpetas para separar raw, interim, processed y plots, y también el notebook base con la configuración inicial para trabajar sobre la rama `Sprint_1`. Además se agregó la lógica de `desactivar_git_push`, porque el notebook puede mostrar comandos de Git, pero no tiene sentido que al profesor le intente hacer un push cuando ejecute todo.

En el avance actual también ya se sumó la descarga del CSV original a `urban_flow/data/raw/speeding_fines.csv` y una primera inspección con `head()`, tipos de datos y conteo de nulos. Eso sirve para ver rápido con qué problemas viene el dataset antes de meterse en la parte más pesada de normalización.

Lo que sigue en los próximos pasos es limpiar fechas, horas, ubicaciones y patentes, decidir qué registros conviene descartar, calcular los excesos de velocidad y recién después pasar a la parte de análisis y gráficos.
