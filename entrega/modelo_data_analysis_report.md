# Modelo de informe de Data Analysis

## Recomendaciones generales:

* Redactar en presente simple y evitar hacerlo personal. 
* Mantener un enfoque *claro y conciso* sin perder el foco.
* No perder de vista el tipo de audiencia.
* Documentar los gráficos y visualizaciones, explicando los tipos de variables en cada eje, las unidades si fuera necesario y observaciones pertinentes.
* Suma puntos redactarlo en inglés.

## Título / Title

Elegir un título atractivo que de cuenta de la temática

### Ejemplo

"Optimizando ventas anuales"

*Tabla de Contenidos*
   
## Introducción y Resumen / Introduction & Summary

* Introducir *breve* pero fuertemente sobre las razones que conducen a realizar el análisis.
> Las primeras líneas deben atrapar a quien la lea e invitar a explorar el resto del informe.  
* Explicar de manera resumida qué se espera lograr con dicho análisis.
* Agregar algo de contexto si fuera necesario.
* Mostrar en un resumen los resultados encontrados en el análisis.

### Ejemplo

En base a los datos referentes a las ventas de todo un año, se realiza un análisis que busca responder preguntas clave hacia la optimización de las mismas: *¿Cuál es el mejor mes de ventas?, ¿Cuál es su recaudación?, ¿En qué ciudad se venden más productos?, ¿Cuáles se venden juntos?* Para así determinar y predecir indicadores clave hacia la optimización: *¿Cuál es el mejor día y horario para mostrar publicidad de productos? ¿A qué se debe el resultado del mayor y menor registro de ventas?*


## Contexto / Background - Context

* Exponer un marco teórico, histórico o aclaraciones pertinentes sobre el origen de los datos,
* así como la necesidad de su análisis con foco en las contribuciones y ayuda en toma de decisiones que implican.
* Si fuera el caso, enfatizar en el impacto de lo antes mencionado y su alcance.

### Ejemplo

La compañía comercializadora de productos electrónicos cuenta sucursales distribuidas en diferentes ciudades de Estados Unidos. Se espera que ante los resultados del análisis de sus ventas a lo largo de un año surjan respuestas a los principales interrogantes e indicadores varios para tomar decisiones como: en qué ciudades/sucursales y clientes enfatizar, cambiar estrategia de ventas u ofrecer servicios diferenciados, cómo optimizar la gestión de anuncios, evaluar la posibilidad de sugerir productos conjuntos, etc.

## Datos / Data

* Mencionar el origen de los datos.
* Exponer un resumen del dataset con los nombres de columnas, descripción del contenido de cada una
* así como algunos datos estadísticos.

### Ejemplo

Los datos protagonistas del análisis fueron exportados directamente del sistema de ventas de la compañía.

|  | Order ID | Product | Quantity Ordered | Price Each | Order Date | Purchase Address |  |
|---:|---:|---:|---:|---:|---:|---:|---|
| description | Número de identificación autogenerado por el sistema. Unívoco a cada órden. | Nombre del producto. | Cantidad de productos ordenados. | Precio unitario. | Fecha y hora en la que se realizó la orden en formato `DD/MM/AA HH:MM` | Dirección de envío con formato `XXX Name St, City, YZ XXXXX` |  |
| type | int | str | int | float | str | str |  |
| count | 18324 | 18324 | 18324 | 18324 | 18324 | 18324 |  |
| unique | 17538 | 20 | 8 | 19 | 13584 | 17120 |  |
|  | min 176558   max 194094 | most common Lightning Charging Cable   freq 12% | min 1   max 7 | min 109.99    max 999.99 | min 04/01/19 03:09   max 05/01/19 04:25 | top 821 Elm St, Austin, TX 73301   freq 4 |  |


## Metodología / Methodology

* Resumir las estrategias para el análisis.
* En particular si se realiza limpieza y adaptaciones en base a ciertos criterios.
* Aclarar dichos criterios.
* Mencionar preguntas a responder.
> Mantener una estructura de tipo: inicio, desarrollo, fin.

### Ejemplo

* Se realiza una limpieza inicial de datos:
    * Removiendo `NaN` en todas las columnas exceptuando `Quantity Order` y `Price each`.
    * Para valores nulos o perdidos de `Quantity Order` y `Price each` se reemplazan por el valor de la mediana y del promedio correspondientemente.
* `Quantity Ordered` y `Price Each` se formatean a `int` y `float` respectivamente.
* Se crea una nueva columna denominada `Sales`, resultante de calcular el total para cada registro.
* Se crea una nueva columna con el `mes`, extraído de Order Date para obtener así el mes de mayor venta.
* Se genera además una nueva columna resultante de extraer el campo con el nombre d ela ciudad de la columna `Purchase Address` para obtener aquella en la que se registran la mayor cantidad de ventas.
* Se formatean los valores de la columna `Order Date` a objetos de tipo datetime.
* Para poder extraer así el valor de cada hora y formar una nueva columna.
* Y calcular entonces el rango de horas con mayor ventas.
* Se agrupan los registros que comparten `Order ID` para posteriormente filtrar aquellos que contienen sólo dos productos.
* Determinando el par de productos que más se vende en conjunto.
* Se determinan los productos que reportaron mayor cantidad de ventas y menor.
* Se observan los mismos en conjunto con otras columnas en busca de una correlación.


## Resultados / Results

* Exponer los resultados del análisis de manera intuitiva y amigable.
* Responder las preguntas planteadas durante la hipótesis y metodología.
* Hacer foco en gráficos y visualizaciones en general.
* Efatizar aquellos que respalden fuertemente la conclusión y la toma de decisiones.
> Mantener una estructura de tipo: inicio, desarrollo, fin.  

El mes de mayor venta es Diciembre:

![](https://i.imgur.com/ZdPeEAN.png)

Austin TX reporta el mayor ingreso en ventas:

![](https://i.imgur.com/c7ZSB9G.png)

Durante 12hs y 19hs se realizan  la mayor cantidad de compras:

![](https://i.imgur.com/m5Tlwvr.png)

Algunos de los productos vendidos en conjunto se pueden observar a continuación:

![](https://i.imgur.com/h5FLdlJ.png)


El TOP 3 de productos que se venden en conjunto es:

* Google Phone + USB-C Charging Cable + Wired Headphones
* iPhone + Lighting Charging Cable + Wired Headphones
* iPhone + Lighting Charging Cable + Apple Airpods Headphones

Se reporta una correlación entre el precio unitario de los productos más vendidos y menos vendidos, más específicamente, una relación inversamente proporcional:

![](https://i.imgur.com/STdk9kS.png)

## Conclusión / Conclusion

* Resumir en un párrafo o dos la conclusión del análisis.
* Haciendo hincaipié en los resultados obtenidos que refuerzan o refutan la hipótesis inicial.
* Y resaltando aquello que sirva a la toma de decisiones.
* Realizar recomendaciones de cara a la toma de decisiones.

### Ejemplo

El mes que reporta el mayor ingreso en ventas es Diciembre, por lo que se recomienda abastecer de stock en este período del año.

Los clientes de la ciudad de Austin TX reportan la mayor cantidad de pedidos, es propicio generar beneficios, promociones y ofrecer anuncios en dicha ciudad. Si se decide invertir recursos en anuncios, los dos mejores horarios para su publicación son las 12hs y las 19hs.

Algunas estrategias de venta que pueden resultar efectivas en relación a la venta de productos en conjunto tienen que ver con ofrecer combos de teléfonos móbiles, cable para cargarlos y auriculares compatibles entre si y/o sugerir los dos productos complementarios al que el cliente esté mirando.

Los productos con precios más elevados reportaron la mayor cantidad de ventas y viceversa. Se sugiere enfocar las nuevas estrategias de ventas a los primeros.

## Anécdotas / Anecdotes

* Agregar datos anecdóticos o cursiosos encontrados como "efecto colateral" durante el análisis.
* Proponer o proyectar futuros análisis al respecto.

### Ejemplo

Se propone realizar un nuevo análisis enfocado a los clientes de la ciudad de Austin TX: recrear este mismo análisis en ese segmento espefício, agregar indicadores como edad, género, contexto cultural y socio económico, etc.

