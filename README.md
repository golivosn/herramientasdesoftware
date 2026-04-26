# Urban Flow

Sprint 1.

## Objetivo

Limpiar y analizar un dataset historico de multas por exceso de velocidad
proveniente de un sistema heredado, para poder migrarlo al sistema nuevo
sin inconsistencias.

## Contexto

La localidad de Vaalserberg (Belgica) registra infracciones con radares
urbanos. Los datos viejos vienen con errores de formato y valores faltantes,
asi que antes de cualquier analisis hay que normalizarlos y depurarlos.

## Estructura

```
urban_flow/
  data/
    raw/        # dataset original sin procesar
    interim/    # dataset procesado + plots/
    processed/  # dataset final para exportar
```

El trabajo se realiza sobre la rama `Sprint_1`. La variable
`desactivar_git_push` controla si el notebook intenta hacer push al remoto.
