# CHANGELOG

Trabajo Practico Integrador — Urban Flow.

Integrantes: Gabriel Olivo, Tobias Tofalo, Luciano Cabral.

---

## Configuracion inicial

- Variables globales del notebook: `desactivar_git_push`, `nombre_rama`,
  `url_repositorio_https` y rutas del proyecto.
- Imports en una sola celda antes del Ejercicio 01: `pandas`, `matplotlib`,
  `pathlib`, `re`, `subprocess`, `unicodedata`, `urlretrieve`, `datetime`.
- Funcion `ejecutar_git` para correr los comandos de git desde el notebook
  y `push_si_corresponde` que respeta el flag `desactivar_git_push`.

---

## Dia 1 — Ejercicio 01

- Clonado del repositorio en Colab cuando corresponde y `cd` al
  directorio del proyecto para que las rutas resuelvan desde la raiz.
- Creacion de la rama `Sprint_1` (o checkout si ya existia).
- Estructura de carpetas pedida: `urban_flow/data/raw`,
  `urban_flow/data/interim`, `urban_flow/data/interim/plots` y
  `urban_flow/data/processed`.
- Verificacion del estado del repo con `git status`.

---

## Dia 2 — Ejercicio 02

- Descarga del dataset original desde el repositorio de la catedra a
  `urban_flow/data/raw/speeding_fines.csv` con `urlretrieve`.
- Inspeccion inicial: `head` de las 5 primeras filas, `dtypes` por
  columna y conteo de nulos con `isna().sum()`.

---

## Dia 3 — Ejercicio 03

- Normalizacion de `fecha` al formato `YYYY-MM-DD`; las invalidas se
  reemplazan por `1932-01-01`.
- Normalizacion de `hora` a 24 hs; las invalidas quedan en `00:00`.
- Normalizacion de `ubicacion`: mayusculas, sin tildes y sin caracteres
  especiales.
- Normalizacion de `patente`: mayusculas, sin separadores y `pd.NA` si
  no queda nada util.
- Eliminacion de filas sin `patente`, `velocidad_registrada` o
  `velocidad_maxima` con la leyenda pedida.
- Deteccion y eliminacion de outliers por IQR sobre `velocidad_registrada`
  y `velocidad_maxima`.
- Calculo de `exceso_velocidad_real` (sin tolerancia) y `exceso_velocidad`
  (con un 5% de tolerancia sobre la velocidad maxima).
- Filtrado de filas sin infraccion (`exceso_velocidad <= 0`).
- Exportacion del datset depurado a
  `urban_flow/data/interim/speeding_fines.csv`.

---

## Dia 4 — Ejercicio 04

- Clase `FineAnalyzer` que recibe el dataframe limpio y lo encapsula.
- Metodo interno `_ranking` reutilizado por los rankings.
- Metodos publicos:
  - `top_patentes_multadas` — top 5 patentes.
  - `top_horarios_multas` — top 5 horarios.
  - `exceso_velocidad_promedio` — promedio con tolerancia.
  - `exceso_velocidad_real_promedio` — promedio sin tolerancia.
  - `multas_por_ubicacion` — conteo agrupado por ubicacion.
- Instanciacion del objeto y llamada a cada metodo en celdas separadas.

---

## Dia 5 — Punto 05

Cinco graficos exportados como `.jpg` en `urban_flow/data/interim/plots/`:

- `fines.jpg` — barras con el top 10 de patentes mas reincidentes.
- `hours.jpg` — torta con el porcentaje de infracciones por hora.
- `months.jpg` — barras horizontales con la cantidad de infracciones por
  mes, ordenadas de mayor a menor.
- `hour.jpg` — linea del exceso promedio para multas con `hora == 00:00`,
  excluyendo las que ademas tienen la fecha por defecto.
- `date.jpg` — linea del exceso promedio para multas con
  `fecha == 1932-01-01`, agregadas por hora del reloj.

---

## Dia 6 — Punto 06

- Porcentaje de infracciones que quedaron con la fecha por defecto
  `1932-01-01`.
- Porcentaje de infracciones que quedaron con la hora por defecto
  `00:00`.

---

## Dia 7 — Punto 07

- Conclusion del Sprint 1 escrita en `urban_flow/data/Readme.md` con
  `%%writefile -a`: calidad de los datos, impacto de los defaluts de
  fecha y hora, distibucion de las multas validas y recomendacion para
  la migracion al sistema nuevo.

## Sprint 2 - Ejercicio 01 (2026-05-21)

- Creación de la rama `Sprint_2` a partir de `Sprint_1`.
- Descarga y extracción del dataset de imágenes en `urban_flow/data/raw/imgs`.
- Actualización del README con el contexto del Sprint 2.

## Sprint 2 - Ejercicio 02 (2026-05-21)

- Listado de imágenes con nombre y tamaño en KB.
- Agrupación en plates y completes con resolución promedio.
- Guardado de group_images.json en interim.
- Función mostrar_imagenes para visualización aleatoria.

## Sprint 2 - Ejercicio 02 (2026-05-21)

- Listado de imágenes con nombre y tamaño en KB.
- Agrupación en plates y completes con resolución promedio.
- Guardado de group_images.json en interim.
- Función mostrar_imagenes para visualización aleatoria.

## Sprint 2 - Ejercicio 02 (2026-05-21)

- Listado de imágenes con nombre y tamaño en KB.
- Agrupación en plates y completes con resolución promedio.
- Guardado de group_images.json en interim.
- Función mostrar_imagenes para visualización aleatoria.

## Sprint 3 - ejercicio 1 - rama sprint_3 y verificacion de datasets (2026-06-14)

- Rama Sprint_3 a partir de Sprint_2, chequeo de datasets.
