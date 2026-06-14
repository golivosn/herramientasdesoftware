

# Sprint 2

## Objetivo

Desarrollar un sistema que determine qué multas tienen evidencia visual válida, cruzando el dataset de multas depurado con el dataset de imágenes de los radares.

## Introducción y contexto

Los radares urbanos generan registros automáticos de multas y las cámaras asociadas registran evidencia visual de cada infracción. Sin embargo, no todas las multas tienen imagen asociada, no todas las imágenes corresponden a una infracción y pueden existir errores de detección. El objetivo de este sprint es cruzar ambas fuentes de datos para determinar qué multas cuentan con evidencia visual válida.

# Conclusión del Sprint 2

El cruce entre el dataset de multas depurado y el dataset de imágenes
mostró que no todas las multas cuentan con evidencia visual. El OCR
sobre las imágenes tipo plates funcionó mejor que sobre las completes
porque en estas últimas la patente ocupa una porción menor del frame
y genera más errores de detección.

El umbral del 80% de coincidencia permitió filtrar falsos positivos
sin descartar matches válidos con pequeñas diferencias de caracteres,
errores típicos del OCR como confundir O con 0, I con 1 o B con 8.
De todas formas, la calidad del resultado depende fuertemente de la
resolución y el ángulo de las fotos.

Para un sistema productivo se recomendaría combinar el OCR con un
modelo de detección de patentes entrenado específicamente, y almacenar
la imagen original junto con la multa en el momento de la infracción
para garantizar la trazabilidad completa.

# Conclusión del Sprint 3

Migramos las 1.713 multas del CSV depurado a una base relacional `transito`
gestionada con SQLAlchemy. La carga quedó en 66 vehículos, 3 radares, 1.713
multas y 613 evidencias, separando el modelo lógico (dataclasses, sin motor)
del modelo relacional (tablas con claves primarias y foráneas).

Sobre esa base resolvimos las consultas del negocio. La patente con más
infracciones es WEFLYN con 38 multas y el radar más activo es R02 en Av.
Libertador con 182. Solo el 35,79% de las multas tiene foto asociada (613
de 1.713), así que la mayoría no está confirmada visualmente.

Sumamos una base vectorial `patente_vectorial` (ChromaDB + OpenCLIP) que
guarda el vector de cada imagen junto al id del vehículo, de forma que a
partir de una foto se recupera por aproximación la patente y sus datos.

Por último, los binarios (imágenes) se versionaron por separado simulando
un remote de DVC para que el repo de git no cargue con archivos pesados.
