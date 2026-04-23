# Urban Flow

Sprint 1.

Este trabajo arranca con un problema bastante típico: hay un dataset histórico de multas por exceso de velocidad que viene de un sistema viejo y los datos no están como para usarlos directo. La idea del sprint es ordenar primero la base del proyecto y después ir avanzando de a poco con la carga, la limpieza y el análisis.

Por ahora quedó armada la estructura de carpetas para separar raw, interim, processed y plots, y también el notebook base con la configuración inicial para trabajar sobre la rama `Sprint_1`. Además se agregó la lógica de `desactivar_git_push`, porque el notebook puede mostrar comandos de Git, pero no tiene sentido que al profesor le intente hacer un push cuando ejecute todo.

Todavía no entramos en la parte fuerte de pandas. La idea de este primer avance fue dejar el arranque prolijo y preparado, así en los siguientes commits se puede sumar la carga del CSV, revisar el estado del dataset y recién después empezar con la limpieza real de columnas.
