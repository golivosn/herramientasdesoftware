# Urban Flow

Sprint 3.

## Objetivo

Migrar la información procesada a una base de datos relacional con el ORM de
SQLAlchemy, versionar los archivos binarios con un remote de DVC simulado y
habilitar la búsqueda de patentes por imagen con una base vectorial
(ChromaDB + OpenCLIP).

## Introducción y contexto

El sistema creció en volumen y complejidad, así que ya no alcanza con los
archivos CSV. En este sprint sumamos persistencia en la base relacional
transito, control de versiones de los datos binarios y una base vectorial
que permite recuperar el vehículo a partir de una imagen de su patente.

## Estructura

- urban_flow/data/raw: dataset original e imágenes.
- urban_flow/data/interim: dataset intermedio.
- urban_flow/data/processed: csv final, base transito y chroma.

La variable desactivar_git_push controla si el notebook hace push al remoto.
