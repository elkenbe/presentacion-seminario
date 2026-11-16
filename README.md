# presentacion_seminario.tex

Presentación en Beamer (16:9) para el **Seminario de investigación** de la PUCP. Expone un artículo y luego explica qué aporta a la investigación propia: *¿Cuál es la relación entre la informalidad y el crecimiento económico en los departamentos del Perú?*

**Autor:** Luis Martinez.

**Artículo presentado:** Rdhaounia, N. y Elweriemmi, M. (2026). *The complex trilogy of shadow economy, inflation, and economic growth: Evidence from MENA countries.* European Journal of Government and Economics, 15(1), 55-75. https://doi.org/10.17979/ejge.2026.15.1.12398

## Contenido de las láminas

| Bloque | Láminas |
|---|---|
| Portada | Título, subtítulo, institución, fecha (`\today`) y logo PUCP |
| Tabla de contenidos | Generada con `\tableofcontents` |
| **Sección 1: el artículo** | Objetivo y pregunta de investigación; tres láminas de resultados (informalidad-crecimiento, informalidad-inflación, crecimiento-inflación), cada una con sus ecuaciones, una tabla 3SLS vs. GMM y una lectura; limitaciones del artículo |
| **Sección 2: aportes para mi investigación** | Comparación de unidades de análisis, de variables, de bases de datos y del modelo econométrico; siguientes pasos |
| Cierre | Lámina de agradecimiento |

## Archivos que necesita

Para compilar, deben estar disponibles:

- `HKUSTstyle.sty`: tema de Beamer cargado con `\usepackage{HKUSTstyle}`. No viene con las distribuciones estándar de LaTeX; hay que tenerlo en la misma carpeta del `.tex`. Probablemente defina también los colores `deepblue`, `deepred`, `deepgreen` y `halfgray`, que `\lstset` usa pero este archivo no declara.
- `pic/LOGO-DE-PUCP.jpg`: logo de la portada, en una subcarpeta `pic/`.
- Paquetes de LaTeX: `fourier`, `calligra`, `pstricks`, `stackengine`, `booktabs`, `multicol`, `listings`, `babel` (español), entre otros. Una distribución completa (TeX Live o MiKTeX) los incluye.

Estructura sugerida:

```
carpeta/
├── presentacion_v2.tex
├── HKUSTstyle.sty
└── pic/
    └── LOGO-DE-PUCP.jpg
```

## Compilación

El archivo no indica el motor. Por `\usepackage[T1]{fontenc}` y `fourier`, lo esperable es **pdfLaTeX**; si `pstricks` da problemas con ese motor, prueba con XeLaTeX o LuaLaTeX. Corre dos veces para que la tabla de contenidos se actualice.

## Atajos definidos en el preámbulo

- `\paperframe`: pone el título y los autores del artículo en el encabezado de cada lámina de la sección 1. Si cambias de artículo, edítalo ahí.
- Columnas `L{ancho}` y `C{ancho}`: texto alineado a la izquierda y centrado, con ancho fijo, para las tablas de comparación.
- `\cmd` y `\env`: macros de formato heredadas de la plantilla; no se usan en las láminas.

## Cómo editar

- **Cifras del artículo:** están dentro de los `tabular` de las láminas 02, 03 y 04 (coeficientes, errores estándar, R², pruebas de Hansen).
- **Base de datos propia:** la tabla "Yo" de la lámina de bases de datos tiene `\ldots` como marcadores; se llenan cuando la base esté construida. La tabla de la izquierda es un fragmento reconstruido, según indica la propia lámina, porque el artículo no publica su base.
- **Pasos pendientes:** la última lámina de contenido lista los cuatro siguientes pasos (construir variables con la ENAHO, empalmar el VAB, verificar la condición de rango, estimar 2SLS/3SLS con efectos fijos).

## Notas

- El título de la primera sección es la referencia completa del artículo, así que aparece largo en la tabla de contenidos.
- Hay código sobrante de la plantilla (la línea comentada del formato 4:3 y `\lipsum`), sin efecto en la presentación.
