# REBIUN revisión datos 2025

Proyecto para diagnosticar, comparar estructuralmente y documentar datos REBIUN 2025.

## Objetivo

Mantener un flujo reproducible para esta fase inicial de trabajo:

- conservar los datos brutos locales sin modificaciones;
- revisar estructura, encabezados, nulos, duplicados y formatos;
- comparar columnas e indicadores entre años;
- documentar criterios, incidencias y decisiones metodológicas;
- crear una maestra documental de universidades/bibliotecas.

Por ahora el proyecto está en fase de diagnóstico, comparación estructural y creación de la maestra de universidades. Todavía no está en fase de limpieza, generación de datos depurados ni exportación final.

## Estructura actual

```text
data/
  raw/        Datos brutos locales, no editados y excluidos de Git.
  interim/    Carpeta preparada para futuros datos intermedios.
  processed/  Carpeta preparada para futuros datos depurados.
  external/   Fuentes externas o tablas auxiliares.
docs/
  criterios_validacion.md
  diccionario_datos.md
  incidencias.md
  maestra_universidades_rebiun.csv
  maestra_universidades_rebiun.md
scripts/
  comparar_estructura_rebiun.py
  crear_maestra_universidades.py
  diagnostico_encabezados.py
  diagnostico_inicial.py
  diagnostico_nombres_2023.py
  diagnostico_universidades.py
outputs/
  informes/
  tablas/
```

## Datos brutos

`data/raw/` contiene los ficheros Excel originales de trabajo. Es una carpeta local excluida de Git mediante `.gitignore`, por lo que sus contenidos no se versionan.

Los datos brutos no deben modificarse directamente. Cualquier transformación futura deberá quedar reflejada en scripts, configuración o documentación de incidencias antes de generar datos en `data/interim/` o `data/processed/`.

## Flujo de trabajo actual

1. Copiar los ficheros originales en `data/raw/`.
2. Mantener `data/raw/` como fuente local no versionada.
3. Ejecutar scripts de diagnóstico para identificar estructura, encabezados, nulos, duplicados y formatos.
4. Comparar columnas, códigos de indicadores y nombres institucionales entre años.
5. Documentar criterios, incidencias y decisiones en `docs/`.
6. Generar informes agregados en `outputs/informes/` cuando corresponda.

## Publicación en GitHub Pages

La visualización interactiva principal está preparada en `docs/index.html`.

Para activarla en GitHub Pages:

1. Ir a `Settings` en el repositorio de GitHub.
2. Abrir `Pages`.
3. En `Build and deployment`, seleccionar `Deploy from a branch`.
4. Elegir rama `main` y carpeta `/docs`.
5. Guardar la configuración.

Archivos publicados:

- `docs/index.html`: visualización interactiva Altair/Vega-Lite.
- `docs/scatter_peso_biblioteca_ptgas_usuarios_2025.png`: versión estática en alta resolución.
- `docs/scatter_peso_biblioteca_ptgas_usuarios_2025.svg`: versión vectorial editable.

