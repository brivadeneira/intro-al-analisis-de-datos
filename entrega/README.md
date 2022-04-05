# Entrega parte 1 Análisis de datos

*Análisis de un dataset de interés y exposición de los resultados*

## Requerimientos

* Fecha entrega: **DO 10/04/2022**
* Fecha exposición: **LU 11/04/2022**

Se debe compartir una **URL pública a un repositorio personal en Github** que contenga:
* Un archivo llamado `README.md` con el informe según la [estructura recomendada](https://github.com/brivadeneira/intro-al-analisis-de-datos/tree/main/entrega/modelo_data_analysis_report.md).
* Los jupyter notebooks empleados para el análisis
  * Cuyo código debe estar ordenado, y respetar las buenas prácticas de código
* El dataset en cuestión en su formato original.

> Cada uno de los estudiantes será designado para hacer *code review* a otro estudiante.

## Proceso recomendado

### Elección de un dataset de interés

A fin de motivar el proceso propuesto para la entrega, se debe seleccionar un dataset de interés, ya sea relacionado con el trabajo, estudio, temática de preferencia, etc. Siempre que se tenga permitido usar dichos datos y teniendo en cuenta que deben estar estructurados en *alguno* de los siguientes formatos compatibles con `pandas`:

* csv *(o txt)*
* excel
* html
* json
* sql
* sql_query
* sql_table

#### Datasets a disposición

Se ponen a disposición una serie de datasets a elegir:

* [Tweets históricos Elon Musk](https://github.com/brivadeneira/intro-al-analisis-de-datos/tree/main/entrega/datasets/elon_tweets.zip)
* [Pizza menu](https://github.com/brivadeneira/intro-al-analisis-de-datos/tree/main/entrega/datasets/pizza_menu.zip)
* [Resultado votación LUC](https://github.com/brivadeneira/intro-al-analisis-de-datos/tree/main/entrega/datasets/ResumenGeneral_D_DPTOS.json)
* [Social media influencers](https://github.com/brivadeneira/intro-al-analisis-de-datos/tree/main/entrega/datasets/social_media_influencers.zip)
* [Tesla Deaths](https://github.com/brivadeneira/intro-al-analisis-de-datos/tree/main/entrega/datasets/tesla_deaths.zip)

### Hipótesis y preguntas disparadoras

Elaborar una serie de preguntas disparadoras de interés a responder al cabo del análisis del dataset. Así como una hipótesis a priori.

### Exploración inicial

Con ayuda de los métodos `head()`, `info()`, `describe()` *(y aquellos que se consideren pertinentes)*, elaorar una descripción de los datos en cuestión, clasificandolos según:
* a qué objeto de Python corresponden.
* a qué grupo de tipos de datos pertenece.

### Preparación y limpieza

* Se debe definir la extención de los datos persé, así como establecer el `index` y su tipo.
* Los nombres/labels de las columnas/Series deben respetar el estilo `snake_case` y ser descriptivos.
* Se deben identificar, para cada serie, aquellos valores que no corresponden a la naturaleza de dicha serie *(missing values)*.
  * Establecer y documentar un criterio para corregir dichos valores.
* Se deben revisar los tipos de datos en función de su significado, naturaleza y el contexto en el que se desarrolla el análisis.
* Identificar y eliminar aquellos valores duplicados que no contribuyen significativamente en la información, si los hubiere.
* Identificar valores sin sentido físico o fuera del concepo de la naturaleza de los datos y reemplazarlos con algún criterio (documentar dicho criterio).
* Identificar outliers, establecer un criterio sobre su corrección o eliminación (documentarlo).

### Transformación y análisis
* Transformar los datos de manera conveniente al análisis.
  * Transformar Series en categorías
  * Conformar nuevas Series resultantes de una operación o aplicación de otras Series.
  * Y otras transformaciones que se crean convenientes.
* Obtener los indicadores/relaciones/resultados de operaciones que respondan las preguntas disparadoras que motivan al análisis.

### Conclusión

Elaborar una conclusión que responda las preguntas disparadoras al inicio del proceso, que afirme o refute la hipótesis inicial según corresónda. Si se encontraron datos anecdóticos que se creen convenientes agregar, agregarlos en esta sección. Así como una proyección a continuar o mejorar al análisis.

