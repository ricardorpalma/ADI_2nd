
# Análisis Exploratorio

## Introducción

El objetivo de realizar un análisis exploratorio consiste en examinar los datos en base a su distribución, características antes de realizar alguna técnica estadística.

El objetivo principal es entender los datos y sus variables antes de acometer algún tipo de análisis más detallado.

Detectar fallas en el diseño de los datos o en la recolección y aplicado a datos univariantes o multivariantes.

![Procesos asociados](images/fig1_ED.png)


El proceso de obtención de información a partir de los datos involucra una serie de procesos asociados.

## Premisas Industriales

Siempre que se aprende algo se avanza desde lo que conozco hacia lo que
desconozco. Sea que estés en una actividad industrial, social o
académica, una de las premisas para aprender implica soltar lo que se
tiene y ha tenido por años como cierto o verdadero para pasar a trabajar
como lo hacen los jueces y los abogados. No daremos nada por cierto
hasta que veamos datos y pruebas que lo demuestren.

El análisis exploratorio de datos será la herramienta que utilizaremos
para comprobar nuestras conjeturas e hipótesis, pero esto requiere
pasión por aprender. Ese avalente gesto de no dar nada por cierto es lo
que algunos filósofos como Descartes nos proponen bajo la consigna de
"la duda metódica" como única vía para llegas a la verdad (yo agregaría
"sin morir en el intento").

En el terreno industrial existen muchos mitos o verdades reveladas. A
modo de ejemplo citaría la mala interpretación que los economistas
argentinos hicieron en la década del 80 del siglo XX respecto a las
técnicas de manágement japonés y el paradigma de la calidad. Para un
economista de entonces las ideas puestas en práctica sobre "inventario
cero" sonaban a una cosa muy plausible, sobre todo a la hora de pagar
impuestos sobre los activos. Créanme jamás vi tanta convulsión en las
cadenas de suministros locales ni tantos quebrantos de empresas como en
esa época.

Como primer actividad realizaremos un análisis exploratorio de datos en
R-Cran sin adentrarnos mucho en las estructuras y tipos de datos o sobre
como importar datos de fuentes como SAP, hojas de cálculo e incluso la
misma web con herramientas como **curl**.

Sin lugar a dudas el recurso más preciado para cualquier sistema de
manufactura o producción de servicios es su recurso humano. Algunos
autores en los últimos 10 años han cambiado esta palabra elevando la
importancia con el cambio de nombre de la gerencia que los administra
pasando de Gerentes de Recursos Humanos a Gerencia de Gestión del
Talento.

Comenzaremos nuestro introducción al tema entonces con este tipo de
información utilizadon un dataset que viene cargado en una de la
bibliotecas (o paquetes) de R.


## KDD

Knowledge Discovery in Databases es un proceso orientado a la identificación de patrones y al descubrimientos de patrones nuevos mas entendibles.

![Evaluación e Interpretación](images/fig2_ED.png)

Knowledge Discovery implica la evaluación e interpretación de patrones y modelos para tomar decisiones con respecto a lo que constituye conocimiento y lo que no lo es. Por lo tanto, el KDD requiere de un amplio y profundo conocimiento sobre tu área de estudio.(Gentileza de MESRK Containers Statistics)

KDD requiere un mayor conocimiento acerca del área de estudio que el **Data Mining**.

## Comprension del dominio de estudio

Como en cualquier tipo de investigación, es fundamental tener muy claros los límites y objetivos de lo que pretendemos. Es muy fácil perder el rumbo en el océano infinito de datos a nuestra disposición.

Desarrollo de un entendimiento sobre el dominio
Descubrimiento de conocimiento previo que sea relevante
Definición del objetivo del KDD
En este paso es cuando reconocemos las fuentes de información más importantes y quienes tienen control sobre ellas. También es relevante incluir toda la metadata relacionada, dimensionar la cantidad de datos, y formatos.

Se recomienda que toda la información más importante que se encuentre solamente en medios físicos sea digitalizada, previo a iniciar las actividades de KDD.

El KDD se refiere al proceso general de descubrir conocimientos útiles a partir de datos, y la minería de datos se refiere a un paso particular en este proceso. La minería de datos es la aplicación de algoritmos específicos para extraer patrones a partir de los datos. La distinción entre el proceso KDD y el paso de minería de datos (dentro del proceso) es un punto central de este artículo. Los pasos adicionales en el proceso KDD, tales como preparación de datos, selección de datos, limpieza de datos, incorporación de conocimiento previo apropiado e interpretación apropiada de los resultados de la minería, son esenciales para asegurar que el conocimiento útil se derive de los datos. La aplicación ciega de métodos de minería de datos (correctamente criticados como dragado de datos en la literatura estadística) puede ser una actividad peligrosa, que fácilmente conduce al descubrimiento de patrones sin sentido e inválidos.

KDD ha evolucionado y sigue evolucionando desde la intersección de campos de investigación como el aprendizaje de máquinas, reconocimiento de patrones, bases de datos, estadísticas, IA, adquisición de conocimientos para sistemas expertos, visualización de datos y computación de alto rendimiento. La meta unificadora es extraer conocimiento de alto nivel desde datos de bajo nivel en el contexto de grandes conjuntos de datos.

El proceso KDD puede ser visto como una actividad multidisciplinaria que abarca técnicas fuera del alcance de cualquier disciplina en particular, como el aprendizaje automático o machine learning. En este contexto, existen oportunidades claras para que otros campos de IA (aparte del aprendizaje automático) contribuyan al KDD. El KDD pone un énfasis especial en encontrar patrones comprensibles que se pueden interpretar como conocimiento útil o interesante. Así, por ejemplo, las redes neuronales, aunque son una potente herramienta de modelado, son relativamente difíciles de entender en comparación con los árboles de decisión. El KDD también hace hincapié en las propiedades de escalado y robustez de los algoritmos de modelado para grandes conjuntos de datos ruidosos.

## Limpieza y procesamiento de datos

Los datasets disponibles en la actualidad usualmente están incompletos (valores de atributos faltantes), tienen ruido (errores y datos aislados o outliers), o presentan inconsistencias (discrepancias en los datos recolectados).

Eliminación de ruido y datos aislados o outliers.
Uso del conocimiento previo para eliminar las inconsistencias y los duplicados.
Selección y uso de estrategias para manejar la información faltante en los datasets.
Estos “datos sucios” pueden confundir el proceso de minería y conducir a resultados inválidos o poco confiables.

El preprocesamiento y la limpieza tienen el objetivo de mejorar la calidad de los datos y los resultados de la minería. Recuerda que la implementación de análisis complejos y el minado de grandes cantidades de datos puede tomar mucho tiempo, así que lo que podamos hacer para acortar ese tiempo será siempre de provecho.

## Minería de datos

La minería es una exploración. Nos adentramos en la inmensidad de los datos y descubrimos poco a poco los patrones o modelos presentes en ellos; las relaciones.

![Algoritmos de exploración](images/fig3_ED.png)

 Y en esta exploración, una de nuestras herramientas más útiles son los algoritmos.

¿Qué es un algoritmo? Básicamente, un algoritmo es una serie de instrucciones o reglas establecidas en un programa informático que nos permiten llegar a un resultado o solución.

En el caso de la minería de datos, un algoritmo nos permite procesar un set de datos para obtener nueva información sobre ese mismo dataset.

En general, la minería de datos comprende tres pasos: la selección de la tarea, la selección del algoritmo (o algoritmos) y su uso.

El algoritmo busca patrones y modelos que nos interesen, siguiendo sus reglas preestablecidas, que pueden incluir árboles de clasificación, modelos de regresión, clusters, modelos mixtos, entre otros.

La mayoría de los métodos de minería de datos se basan en técnicas comprobadas de aprendizaje automático o machine learning, reconocimiento de patrones, y estadísticas: clasificación, agrupación, regresión, etc. La formación de diferentes algoritmos bajo cada uno de estos encabezados a menudo puede ser desconcertante para el analista de datos novato y también para el experto.

Debe hacerse hincapié en que, de los muchos métodos de minería de datos anunciados en la literatura, en realidad sólo hay unas pocas técnicas fundamentales.

## Interpretación de patrones minados

Es importante que comprendamos la diferencia entre dos términos clave: patrones y modelos.

Patrones: son estructuras locales que hacen declaraciones sólo sobre un espacio restringido por variables. Esto tiene aplicaciones importantes en detección de anomalías como la detección de faltas en procesos industriales o de fraudes en el sistema bancario.
Modelos: son estructuras globales que hacen declaraciones sobre cualquier punto en el espacio de medición. Por ejemplo, los modelos pueden predecir el valor de alguna otra variable.
En la etapa de interpretación, hallamos los patrones y modelos en los datos analizados.

Los resultados deben presentarse en un formato entendible. Por esta razón las técnicas de visualización son importantes para que los resultados sean útiles, dado que los modelos matemáticos o descripciones en formato de texto pueden ser difíciles de interpretar para los usuarios finales.

Desde este punto del proceso es posible regresar a cualquiera de los pasos anteriores.

## Imputación de datos

La falta de datos en el proceso de captura puede deberse a diversas situaciones que van desde:

* fatiga del informante
* rechazo a informar
* calidad de la muestra
* formación del encuestador

Los valores NA (not available) no pueden ser comparados ni se puede realizar operaciones sobre ellos.

## Detección en R

La elección de datos ausente se debe verificar previo a la realización de ciertas calculas para entender su resultado, que puede verse afectados por la aparición de datos nulos.


Uno de los aspectos más interesantes de R-Cran es la facilidad que tienen para generar datasets en forma sensilla, lo que lo hace especialmente atractivo para desarrollar y entrenar modelos de simulación

Veamos un ejemplo de generación de un dataset fincticio llamado *"valores* y comencemos ha hacer el análisis primero en forma manual.


```r
# Crear un set de datos de 50 datos ficticios con 5 valores con NA.
valores <- as.integer(runif(50,1,10))
indices <- as.integer(runif(5,1,50))
valores[indices] <- NA
valores
#>  [1]  7  9  5  4  1  8  9  8  7  5 NA  5  8  2  9  7  2  4
#> [19]  7  8 NA  5  5 NA  2  6  2  5  4  7  9  4  9  2  8  3
#> [37]  3  5  5  9  9 NA  4  9  8  8  8  3  2  9
```




Devuelve TRUE si el objeto contiene un valor Nulo o ausente. Se aplica a cada elemento del objeto.


```r
is.na(valores)
#>  [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
#> [10] FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
#> [19] FALSE FALSE  TRUE FALSE FALSE  TRUE FALSE FALSE FALSE
#> [28] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
#> [37] FALSE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE
#> [46] FALSE FALSE FALSE FALSE FALSE
```



      na.fail(objeto)

Se utiliza para detener la ejecución de u scrip o programa si el objeto contiene algún valor ausente.

    any(is.na(objeto))


```r
any(is.na(valores))
#> [1] TRUE
```



Devolverá TRUE si existe al menos un valor ausente dentro de objeto.



### Eliminar datos ausentes

La eliminación de datos ausentes es una medida que de be realizarse en forma previa a cualquier análisis posterior del conjunto de datos.


    na.omit(objeto)

Elimina del objeto cualquier dato ausente existente


```r
na.omit(valores)
#>  [1] 7 9 5 4 1 8 9 8 7 5 5 8 2 9 7 2 4 7 8 5 5 2 6 2 5 4 7 9
#> [29] 4 9 2 8 3 3 5 5 9 9 4 9 8 8 8 3 2 9
#> attr(,"na.action")
#> [1] 11 21 24 42
#> attr(,"class")
#> [1] "omit"
```



    complete.cases(objeto)

Se utiliza en dataframes y verifica que ninguna de las columnas de cada fila contenga valores NA. Devuelve un vector, con valor de TRUE en las filas sin valores ausente (completas) y FALSE en el resto. este vector puede utilizarse para seleccionar filas de interés.


```r
complete.cases(valores)
#>  [1]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
#> [10]  TRUE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
#> [19]  TRUE  TRUE FALSE  TRUE  TRUE FALSE  TRUE  TRUE  TRUE
#> [28]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
#> [37]  TRUE  TRUE  TRUE  TRUE  TRUE FALSE  TRUE  TRUE  TRUE
#> [46]  TRUE  TRUE  TRUE  TRUE  TRUE
```

Existen una cantidad considerable de dataset de prueba en R-Cran que puedes utilizar para dar tus primeros pasos (e incluso en experimentos no tan básicos). Todos ellos aparecen en la bibliografía de estadística o tienen papers que explicna las técnicas de recolección. Es recomendable espolrar las fuentes que aparecen en las ayuda para que en caso de utilizarlo en tus artículos científicos puedas citar correctamente.

Para poder verlos tipea en la consola

    data()
    
Recuerda que habitualmente cada biblioteca que cargas con *install.packages()* agrega otros datasets a esta colección
Si quieres ver todos los datasets tipea:

      data(package = .packages(all.available = TRUE)

Usaremos el dataset de Calidad de Aire de la Ciudad de New York

para visualizar el dataset tipea


```r
airquality
#>     Ozone Solar.R Wind Temp Month Day
#> 1      41     190  7.4   67     5   1
#> 2      36     118  8.0   72     5   2
#> 3      12     149 12.6   74     5   3
#> 4      18     313 11.5   62     5   4
#> 5      NA      NA 14.3   56     5   5
#> 6      28      NA 14.9   66     5   6
#> 7      23     299  8.6   65     5   7
#> 8      19      99 13.8   59     5   8
#> 9       8      19 20.1   61     5   9
#> 10     NA     194  8.6   69     5  10
#> 11      7      NA  6.9   74     5  11
#> 12     16     256  9.7   69     5  12
#> 13     11     290  9.2   66     5  13
#> 14     14     274 10.9   68     5  14
#> 15     18      65 13.2   58     5  15
#> 16     14     334 11.5   64     5  16
#> 17     34     307 12.0   66     5  17
#> 18      6      78 18.4   57     5  18
#> 19     30     322 11.5   68     5  19
#> 20     11      44  9.7   62     5  20
#> 21      1       8  9.7   59     5  21
#> 22     11     320 16.6   73     5  22
#> 23      4      25  9.7   61     5  23
#> 24     32      92 12.0   61     5  24
#> 25     NA      66 16.6   57     5  25
#> 26     NA     266 14.9   58     5  26
#> 27     NA      NA  8.0   57     5  27
#> 28     23      13 12.0   67     5  28
#> 29     45     252 14.9   81     5  29
#> 30    115     223  5.7   79     5  30
#> 31     37     279  7.4   76     5  31
#> 32     NA     286  8.6   78     6   1
#> 33     NA     287  9.7   74     6   2
#> 34     NA     242 16.1   67     6   3
#> 35     NA     186  9.2   84     6   4
#> 36     NA     220  8.6   85     6   5
#> 37     NA     264 14.3   79     6   6
#> 38     29     127  9.7   82     6   7
#> 39     NA     273  6.9   87     6   8
#> 40     71     291 13.8   90     6   9
#> 41     39     323 11.5   87     6  10
#> 42     NA     259 10.9   93     6  11
#> 43     NA     250  9.2   92     6  12
#> 44     23     148  8.0   82     6  13
#> 45     NA     332 13.8   80     6  14
#> 46     NA     322 11.5   79     6  15
#> 47     21     191 14.9   77     6  16
#> 48     37     284 20.7   72     6  17
#> 49     20      37  9.2   65     6  18
#> 50     12     120 11.5   73     6  19
#> 51     13     137 10.3   76     6  20
#> 52     NA     150  6.3   77     6  21
#> 53     NA      59  1.7   76     6  22
#> 54     NA      91  4.6   76     6  23
#> 55     NA     250  6.3   76     6  24
#> 56     NA     135  8.0   75     6  25
#> 57     NA     127  8.0   78     6  26
#> 58     NA      47 10.3   73     6  27
#> 59     NA      98 11.5   80     6  28
#> 60     NA      31 14.9   77     6  29
#> 61     NA     138  8.0   83     6  30
#> 62    135     269  4.1   84     7   1
#> 63     49     248  9.2   85     7   2
#> 64     32     236  9.2   81     7   3
#> 65     NA     101 10.9   84     7   4
#> 66     64     175  4.6   83     7   5
#> 67     40     314 10.9   83     7   6
#> 68     77     276  5.1   88     7   7
#> 69     97     267  6.3   92     7   8
#> 70     97     272  5.7   92     7   9
#> 71     85     175  7.4   89     7  10
#> 72     NA     139  8.6   82     7  11
#> 73     10     264 14.3   73     7  12
#> 74     27     175 14.9   81     7  13
#> 75     NA     291 14.9   91     7  14
#> 76      7      48 14.3   80     7  15
#> 77     48     260  6.9   81     7  16
#> 78     35     274 10.3   82     7  17
#> 79     61     285  6.3   84     7  18
#> 80     79     187  5.1   87     7  19
#> 81     63     220 11.5   85     7  20
#> 82     16       7  6.9   74     7  21
#> 83     NA     258  9.7   81     7  22
#> 84     NA     295 11.5   82     7  23
#> 85     80     294  8.6   86     7  24
#> 86    108     223  8.0   85     7  25
#> 87     20      81  8.6   82     7  26
#> 88     52      82 12.0   86     7  27
#> 89     82     213  7.4   88     7  28
#> 90     50     275  7.4   86     7  29
#> 91     64     253  7.4   83     7  30
#> 92     59     254  9.2   81     7  31
#> 93     39      83  6.9   81     8   1
#> 94      9      24 13.8   81     8   2
#> 95     16      77  7.4   82     8   3
#> 96     78      NA  6.9   86     8   4
#> 97     35      NA  7.4   85     8   5
#> 98     66      NA  4.6   87     8   6
#> 99    122     255  4.0   89     8   7
#> 100    89     229 10.3   90     8   8
#> 101   110     207  8.0   90     8   9
#> 102    NA     222  8.6   92     8  10
#> 103    NA     137 11.5   86     8  11
#> 104    44     192 11.5   86     8  12
#> 105    28     273 11.5   82     8  13
#> 106    65     157  9.7   80     8  14
#> 107    NA      64 11.5   79     8  15
#> 108    22      71 10.3   77     8  16
#> 109    59      51  6.3   79     8  17
#> 110    23     115  7.4   76     8  18
#> 111    31     244 10.9   78     8  19
#> 112    44     190 10.3   78     8  20
#> 113    21     259 15.5   77     8  21
#> 114     9      36 14.3   72     8  22
#> 115    NA     255 12.6   75     8  23
#> 116    45     212  9.7   79     8  24
#> 117   168     238  3.4   81     8  25
#> 118    73     215  8.0   86     8  26
#> 119    NA     153  5.7   88     8  27
#> 120    76     203  9.7   97     8  28
#> 121   118     225  2.3   94     8  29
#> 122    84     237  6.3   96     8  30
#> 123    85     188  6.3   94     8  31
#> 124    96     167  6.9   91     9   1
#> 125    78     197  5.1   92     9   2
#> 126    73     183  2.8   93     9   3
#> 127    91     189  4.6   93     9   4
#> 128    47      95  7.4   87     9   5
#> 129    32      92 15.5   84     9   6
#> 130    20     252 10.9   80     9   7
#> 131    23     220 10.3   78     9   8
#> 132    21     230 10.9   75     9   9
#> 133    24     259  9.7   73     9  10
#> 134    44     236 14.9   81     9  11
#> 135    21     259 15.5   76     9  12
#> 136    28     238  6.3   77     9  13
#> 137     9      24 10.9   71     9  14
#> 138    13     112 11.5   71     9  15
#> 139    46     237  6.9   78     9  16
#> 140    18     224 13.8   67     9  17
#> 141    13      27 10.3   76     9  18
#> 142    24     238 10.3   68     9  19
#> 143    16     201  8.0   82     9  20
#> 144    13     238 12.6   64     9  21
#> 145    23      14  9.2   71     9  22
#> 146    36     139 10.3   81     9  23
#> 147     7      49 10.3   69     9  24
#> 148    14      20 16.6   63     9  25
#> 149    30     193  6.9   70     9  26
#> 150    NA     145 13.2   77     9  27
#> 151    14     191 14.3   75     9  28
#> 152    18     131  8.0   76     9  29
#> 153    20     223 11.5   68     9  30
```



También es posible ver esto más claramente con **str**


```r
str(airquality)
#> 'data.frame':	153 obs. of  6 variables:
#>  $ Ozone  : int  41 36 12 18 NA 28 23 19 8 NA ...
#>  $ Solar.R: int  190 118 149 313 NA NA 299 99 19 194 ...
#>  $ Wind   : num  7.4 8 12.6 11.5 14.3 14.9 8.6 13.8 20.1 8.6 ...
#>  $ Temp   : int  67 72 74 62 56 66 65 59 61 69 ...
#>  $ Month  : int  5 5 5 5 5 5 5 5 5 5 ...
#>  $ Day    : int  1 2 3 4 5 6 7 8 9 10 ...
```




      total de filas completas, sin valores nulos o ausentes


```r
nrow(na.omit(airquality))
#> [1] 111
```





      total de filas completas, sin valores nulos o ausentes


```r
nrow(airquality[complete.cases(airquality),])
#> [1] 111
```




Algunas funciones de R pueden funcionar con valores NA, ingresando un parámetro adicional de tipo na.rm o action


```r
promedio <- mean(valores, na.rm=TRUE)
promedio
#> [1] 5.826087
```



### Uso de na.action com parametro de function modelo lineal


```r
lm(Solar.R ~ Temp, airquality, na.action=na.omit)
#> 
#> Call:
#> lm(formula = Solar.R ~ Temp, data = airquality, na.action = na.omit)
#> 
#> Coefficients:
#> (Intercept)         Temp  
#>     -24.431        2.693
```





## Limpieza de datos

Los valores ausentes son relativamente comunes en los set de datos y se deben a muchas causas: fallas en la captura de datos o en la transcripción de datos.

## Missing Completely at Random (MCAR)

Los valores perdidos no se relacionan con las variables en el set de datos. Esta función elimina las filas que tengan 100% de datos perdidos.

Como dice, los valores faltan aleatoriamente de su conjunto de datos. Los valores de los datos que faltan no se relacionan con ningún otro dato del conjunto de datos y no existe un patrón para los valores reales de los datos que faltan.

Por ejemplo, cuando el estatus de fumador no se registra en un subconjunto aleatorio de pacientes. Esto es fácil de manejar, pero desafortunadamente, los datos casi nunca faltan completamente al azar.

## Missing at Random (MAR)

Esto es confuso y sería mejor decir que falta condicionalmente al azar. Aquí, los datos que faltan tienen una relación con otras variables en el set de datos. Sin embargo, los valores reales que faltan son aleatorios.

Por ejemplo, el estatus de fumador no está documentado en pacientes mujeres porque el médico era demasiado tímido para preguntar.

## Not Missing at Random (NMAR)

El patrón de falta de datos está relacionado con otras variables del conjunto de datos, pero además, los valores de los datos que faltan no son aleatorios.

Por ejemplo, cuando no se registra el estado de tabaquismo en los pacientes ingresados como una emergencia, que también son más propensos a tener peores resultados de la cirugía.

La falta de datos no aleatorios es importante, puede alterar sus conclusiones y es la más difícil de diagnosticar y manejar. Sólo pueden detectarse recogiendo y examinando algunos de los datos que faltan. Esto es a menudo difícil o imposible de hacer.

La forma de tratar los datos que faltan depende del tipo de falta.



## Análisis Univariado

### Qué es un análisis exploratorio

Un análisis exploratorio de datos, o **AED** (en inglés, **EDA** -
Exploratory Data Analysis), es una **fase inicial y fundamental** en
cualquier proceso de analítica de datos o proyecto de ciencia de datos.
Su propósito no es generar conclusiones definitivas, sino **comprender
la estructura, las relaciones y las anomalías de los datos** antes de
aplicar modelos estadísticos o de aprendizaje automático más complejos.

Piense en el AED como la fase de ***"investigación detectivesca"*** de
sus datos. Es el momento de hacerse preguntas como:

-   ¿Cómo se distribuyen mis variables?
-   ¿Hay valores atípicos (outliers) que podrían sesgar mis resultados?
-   ¿Hay valores faltantes y, de ser así, cómo los manejo?
-   ¿Existen correlaciones o patrones interesantes entre las variables?

### ¿Por qué es crucial?

El AED es vital porque le permite **identificar problemas y
oportunidades** que, de otra forma, podrían pasar desapercibidos. Por
ejemplo, si un valor atípico representa un error de entrada de datos, no
corregirlo podría llevar a que su modelo predictivo sea completamente
inútil.

En un contexto de posgrado, no solo esperamos que se sepa cómo realizar
un AED, sino que entienda el **razonamiento detrás de cada paso**. Un
AED bien ejecutado puede guiar la selección de la metodología analítica
más apropiada y, en última instancia, **mejorar la calidad y la
fiabilidad de sus resultados**.

## Técnicas comunes en el AED

Para llevar a cabo un AED, se utilizan diversas técnicas, que se pueden
clasificar en dos grandes grupos:

-   **Paciencia y relfexión**: AED no es preparen, fuego, apunten; sino
    todo lo contrario. Es importante que se sepa que este análisis
    probablemente no te de respuestas. En su lugar te conforntará con
    nuevas preguntas que te llevarán a la causa raíz del problema.

-   **Técnicas Visuales:** Se utilizan gráficos para inspeccionar los
    datos. Algunos ejemplos incluyen:

-   **Histogramas:** Para ver la distribución de una variable numérica.

-   **Diagramas de caja (Box plots):** Para identificar la dispersión,
    la mediana y los posibles valores atípicos.

-   **Diagramas de dispersión (Scatter plots):** Para visualizar la
    relación entre dos variables.

-   **Mapas de calor (Heatmaps):** Para visualizar correlaciones entre
    múltiples variables.

-   **Técnicas Numéricas/Estadísticas:** Se utilizan resúmenes numéricos
    para describir los datos. Esto incluye:

-   **Estadísticas descriptivas:** Calcular la media, mediana, moda,
    desviación estándar y rango.

-   **Matrices de correlación:** Para cuantificar la fuerza de la
    relación entre variables.

-   **Tablas de frecuencia:** Para contar la ocurrencia de cada
    categoría en una variable cualitativa.

En resumen, el AED es la **primera conversación** que tiene con sus
datos. Es una etapa iterativa y flexible que le permite entender a fondo
lo que tiene entre manos, **formular hipótesis** y **preparar el
camino** para el análisis formal que vendrá después. Es la base de un
trabajo de investigación o de un proyecto de ciencia de datos serio y
robusto.

## Insatalar Paquetes y Datasets

Es lo rpimero que se tiene que hacer, contar con un dataset cargado en
el memoria o área de trabajo de R. Lo más importante es conocer y
revalidar los datos.

Uno de lo paquetes que podemos utilizar es AER , que tienen cientos de
datasets muy conocidos en conometría, algunos de ellos preferidos como
consutores en economía industrial tales como [@kosakoff2008america].

Recuerda que antes de poder utilizar un paquete en R, debes descargarlo
utilizando:

```         
-> Tools -> install.packeges y elegir en el cuadro de diálogo.
```


```r
library(AER)
#> Loading required package: car
#> Loading required package: carData
#> Loading required package: lmtest
#> Loading required package: zoo
#> 
#> Attaching package: 'zoo'
#> The following objects are masked from 'package:base':
#> 
#>     as.Date, as.Date.numeric
#> Loading required package: sandwich
#> Loading required package: survival
```

Biblioteca AER [@AER-2008]

### Listado de Datasets

Para visualizar los datasets que tiene incluidos **AER** usamos el
siguiente código.


```r
data(package="AER")
```

```         
nota las comillas dobles en el nombre del paquete. verás la salida en la consola de RStudio
```

No verás el detalle en RMarkdown

Vamos a uilizar **CPS1985** son parte de AER y haremos algunos pasos
para explorarlos.

Observa que hay una tabla igual pero con los datos de 1988

### Visualización de las estructura del dataset

Para poder utilizarlo debemos invocar al datset y podrás ver parte de su
mínima expresión de datos en la ventana superior derecha de R-Studio.
Utilizar


```r
data(CPS1985)
```

Esto crea una variable que se llama igual que el datset que tiene 534
instancias o casos observados en una estructura de 11 columnas.

Para explorar la cabecera de datos utilizar


```r
head(CPS1985)
#>       wage education experience age ethnicity region gender
#> 1     5.10         8         21  35  hispanic  other female
#> 1100  4.95         9         42  57      cauc  other female
#> 2     6.67        12          1  19      cauc  other   male
#> 3     4.00        12          4  22      cauc  other   male
#> 4     7.50        12         17  35      cauc  other   male
#> 5    13.07        13          9  28      cauc  other   male
#>      occupation        sector union married
#> 1        worker manufacturing    no     yes
#> 1100     worker manufacturing    no     yes
#> 2        worker manufacturing    no      no
#> 3        worker         other    no      no
#> 4        worker         other    no     yes
#> 5        worker         other   yes      no
```

Para ver los datos finales de la tabla utilizar:


```r
tail(CPS1985)
#>      wage education experience age ethnicity region gender
#> 528 11.79        16          6  28      cauc  other female
#> 529 11.36        18          5  29      cauc  other   male
#> 530  6.10        12         33  51     other  other female
#> 531 23.25        17         25  48     other  other female
#> 532 19.88        12         13  31      cauc  south   male
#> 533 15.38        16         33  55      cauc  other   male
#>     occupation        sector union married
#> 528  technical         other   yes      no
#> 529  technical         other    no      no
#> 530  technical         other    no     yes
#> 531  technical         other   yes     yes
#> 532  technical         other   yes     yes
#> 533  technical manufacturing    no     yes
```

### Exploración de la clase

Como R es un lenguaje orientado a objetos, opera con el concepto de
clases. Si no conoces que es esto, simplemene observa la información que
obtienes del comando **str**.


```r
str(CPS1985)
#> 'data.frame':	534 obs. of  11 variables:
#>  $ wage      : num  5.1 4.95 6.67 4 7.5 ...
#>  $ education : num  8 9 12 12 12 13 10 12 16 12 ...
#>  $ experience: num  21 42 1 4 17 9 27 9 11 9 ...
#>  $ age       : num  35 57 19 22 35 28 43 27 33 27 ...
#>  $ ethnicity : Factor w/ 3 levels "cauc","hispanic",..: 2 1 1 1 1 1 1 1 1 1 ...
#>  $ region    : Factor w/ 2 levels "south","other": 2 2 2 2 2 2 1 2 2 2 ...
#>  $ gender    : Factor w/ 2 levels "male","female": 2 2 1 1 1 1 1 1 1 1 ...
#>  $ occupation: Factor w/ 6 levels "worker","technical",..: 1 1 1 1 1 1 1 1 1 1 ...
#>  $ sector    : Factor w/ 3 levels "manufacturing",..: 1 1 1 3 3 3 3 3 1 3 ...
#>  $ union     : Factor w/ 2 levels "no","yes": 1 1 1 1 1 2 1 1 1 1 ...
#>  $ married   : Factor w/ 2 levels "no","yes": 2 2 1 1 2 1 1 1 2 1 ...
```

Ahora nos queda más claro que los datos que nos ofrecía *data()* habla
sobre:

```         
CPS1985  Determinants of Wages Data (CPS 1985)
```

Sobre una columna llamada Salarios (WAGES) y como podemos explicarla en
función de los datos vinculados en otras columna.

A la columna Wages se la llama columnas de etiquetas del dataset y es
vital para hacer más tarde aprendizaje supervisado de máquina **machine
learning**.

Vemos también que el dataset tiene columnas que son de tipo **numérico**
y **alfabético**, pero existen además otras que se denominan de tipo
**categórico** con instancias bien explicadas.

Existen además otros tipos tales como **binarias** y otras que veremos
más adelante.

## Acceso a datos individuales, filas y columnas

Veamos la columna de educación

Examinemos la clase


```r
class(CPS1985$education)
#> [1] "numeric"
```

Las sintaxis **nombre de tabla** \$ **nombre de columna** nos muestra
los valores


```r
CPS1985$education
#>   [1]  8  9 12 12 12 13 10 12 16 12 12 12  8  9  9 12  7 12
#>  [19] 11 12 12  7 12 11 12  6 12 10 12 12 14 12  8 17 12 12
#>  [37] 12 12 12 14 12 14 12  9 13  7 16 10  8 12 12 16 12 12
#>  [55] 13 12 13 10 12 12 11 12  3 12 12 10 12 12 12 10 11 14
#>  [73] 10  8  8  6 11 12 12 12 14 12 10 16 13 12 11 12 12 11
#>  [91] 12 12 12 12 12 12 15 12 12 13 11 10 12 12 14 12 14  5
#> [109] 12  8 13 12 12 12 11 16 11 12  8 12 12 12 12 12 12 12
#> [127]  9 13 12 12 12 12 12 14  9 10 12  7  9 12 12 12 11 11
#> [145] 10 12 12 12 12 13  6 14 12 14 12 12 16 14 14 12 12 13
#> [163] 17 12 14 16 16 15 17 12 14 12 16 12 14 16 18 15 12 12
#> [181] 18 16 18 16 16 16 17 12 14 18 12 12 12 18 10 16 16 16
#> [199] 13 12 14 16 17 12 16 12 15 13 14 16 18 13 12 18 14 14
#> [217] 12 12 12 16 12 11 12 14 12 16 16 11 13 12 14 14 12 12
#> [235] 13 14 14 12 14 12 12 12 14 12 12 15 12 13 17 14 13 16
#> [253] 12 12 16 16 13 14 18 14 12 12 12 12 12 11 16 12 12 12
#> [271] 12 18 11 12 16 13 16 13 12 12 12 12 12 13 14 14 12 12
#> [289] 17 16 12 12 13 12 13 12 12 14 12 12 12 12 12 13 12  9
#> [307] 13 12 13 12 13 12 13 16 12 12 12 12 12 12 12 17 14 12
#> [325] 14 15 12 12 11 12 12 16 13 12 12 12 12 12 12 12 12 12
#> [343] 12 17 14 12  4 14  8 15  2  8 11 10  8  9 12  8 14 12
#> [361] 12 16 13 16 14 12 11 13 12 10  8 12 12 12 12 12 12 12
#> [379] 12 13 14 12 12 11 11 12 12 12 10 12 12 12 14 14 12 13
#> [397] 12 13 12 12 10 12 14 11 11  8 16 10 16 14 14 11 12  9
#> [415] 11 13 14 12 14 12 12 12 12 11 12  8  9  7 11 13 18 17
#> [433] 16 14 12 18 18 17 13 16 14 15 18 16 16 18 16 17 16 17
#> [451] 15 18 17 16 18 18 14 16 18 18 16 12 16 16 16 12 12 12
#> [469] 18 12 16 15 18 16 18 16 12 18 12 16 14 18 16 18 17 18
#> [487] 14 14 16 16 14 17 16 16 16 15 18 17 16 18 17 12 17 12
#> [505] 17 16 16 18 16 16 17 16 18 12 16 14 16 12 14 16 17 16
#> [523] 16 17  9 15 15 12 16 18 12 17 12 16
```

### Datos ordenados


```r
sort(CPS1985$education)
#>   [1]  2  3  4  5  6  6  6  7  7  7  7  7  8  8  8  8  8  8
#>  [19]  8  8  8  8  8  8  8  8  8  9  9  9  9  9  9  9  9  9
#>  [37]  9  9  9 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10
#>  [55] 10 10 11 11 11 11 11 11 11 11 11 11 11 11 11 11 11 11
#>  [73] 11 11 11 11 11 11 11 11 11 11 11 12 12 12 12 12 12 12
#>  [91] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [109] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [127] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [145] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [163] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [181] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [199] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [217] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [235] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [253] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [271] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
#> [289] 12 12 12 12 12 12 12 12 12 12 12 12 12 12 13 13 13 13
#> [307] 13 13 13 13 13 13 13 13 13 13 13 13 13 13 13 13 13 13
#> [325] 13 13 13 13 13 13 13 13 13 13 13 13 13 13 13 14 14 14
#> [343] 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14
#> [361] 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14
#> [379] 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 14 15
#> [397] 15 15 15 15 15 15 15 15 15 15 15 15 16 16 16 16 16 16
#> [415] 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16
#> [433] 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16
#> [451] 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16 16
#> [469] 16 16 16 16 16 16 16 16 16 16 16 17 17 17 17 17 17 17
#> [487] 17 17 17 17 17 17 17 17 17 17 17 17 17 17 17 17 17 18
#> [505] 18 18 18 18 18 18 18 18 18 18 18 18 18 18 18 18 18 18
#> [523] 18 18 18 18 18 18 18 18 18 18 18 18
```

# Identificación de valores mínimos y máximos, conteos (QUERY)

**Mínimos**


```r
which.min(CPS1985$education)
#> [1] 351
```

Debes entender que esto nos dice que el valor que está en la fila
indicada tiene el primer valor mínimo

Para ver qué valor es el mínimo ejecutamos


```r
CPS1985$education[351]
#> [1] 2
```

**Máximos**


```r
which.max(CPS1985$education)
#> [1] 177
```

Debes entender que esto nos dice que el valor que está en la fila
indicada tiene el primer valor mínimo

Para ver qué valor es el mínimo ejecutamos


```r
CPS1985$education[177]
#> [1] 18
```

## Conteos


```r
length(CPS1985$education)
#> [1] 534
```

Tenemos una muestra de 534 casos.

### ¿Cuántos valores hay mayores que 16 en educación?


```r
mayores_16 <- which(CPS1985$education > 16)

mayores_16
#>  [1]  34 163 169 177 181 183 187 190 194 203 211 214 249 259
#> [15] 272 289 322 344 431 432 436 437 438 443 446 448 450 452
#> [29] 453 455 456 459 460 469 473 475 478 482 484 485 486 492
#> [43] 497 498 500 501 503 505 508 511 513 521 524 530 532
```

El vector mayores_16 nos muestra el índice que contiene los casos de
educación \> que 16

Para ver los valores ejecutamos


```r
CPS1985$education[mayores_16]
#>  [1] 17 17 17 18 18 18 17 18 18 17 18 18 17 18 18 17 17 17
#> [19] 18 17 18 18 17 18 18 17 17 18 17 18 18 18 18 18 18 18
#> [37] 18 18 18 17 18 17 18 17 18 17 17 17 18 17 18 17 17 18
#> [55] 17
```

¿Cuántos casos hay en la muestra que tengan educación mayor que 16.


```r
length(mayores_16)
#> [1] 55
```

# Ploteos y Gráficas

La función clásica del paquete base par plotear es **plot()**. Ella se
adapta automáticamente a la geometría del objeto (en este caso dataset)
a graficar.


```r
plot(CPS1985$education)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-29-1.png" width="672" />

Podemos ordenar los datos para tener mayor claridad y etiquetar los ejes
cartecianos, así como agrevar color y tipo de línea

```         
consulta desde la consola ?plot()
```


```r
plot(sort(CPS1985$education), main= "Cuatrimestres de educación del personal", ylab="Cuatrimestre", xlab="Individuo (caso muestral)",col= "red")
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-30-1.png" width="672" />

## Gráficos de caja y bigote


```r
boxplot(CPS1985$education, col="blue", main="Gráficas para 1,2y3 Sigma con outilers - Nivel de educación")
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-31-1.png" width="672" />

Si quieres ignorar (no contemplar) los outilers usa el parámetro
"outline = FALSE"


```r
boxplot(CPS1985$education, outline = FALSE  ,col="green", main="Gráficas para 1,2y3 Sigma sin outilers - Nivel de educación")
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-32-1.png" width="672" />

En este caso los valores que difieren en más de 3 sigma no son tenidos
en cuenta para la media y el desvío estandard.

## Histogramas

Histogramas dicotómicos


```r
hist(CPS1985$education,breaks = 2, main="clasificador en dos submuestras de igual rango", ylab="Frecuencai relativa o conteo" )
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-33-1.png" width="672" />

Clasificador en rangos


```r
hist(CPS1985$education, col="orange")
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-34-1.png" width="672" />

Histograma de 50 cajas


```r
hist(CPS1985$education,breaks = 50, main="clasificador de 50 cajas", col="pink" )
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-35-1.png" width="672" />

## Funciones de densidad

La función **density()** en R calcula la estimación de la densidad
kernel de una variable numérica univariada, lo que permite visualizar la
distribución de los datos a través de una curva continua en lugar de
barras. Esta función genera un conjunto de pares de puntos (x, y) que
representan la curva de densidad, la cual muestra la probabilidad de que
los datos se encuentren en un determinado rango, y es útil para entender
la forma y dispersión de una distribución.

```         
En otras palabras ella estima la distribución de probabilidad:
```

Para una muestra de datos numéricos, density() estima cómo se
distribuyen los datos.

-   Genera una curva suave: A diferencia de un histograma, que usa
    barras, density() crea una curva suave y continua, facilitando la
    interpretación visual de los patrones. Produce puntos (x, y):

La salida de la función es un objeto que contiene las coordenadas x e y
de la curva de densidad estimada, permitiendo su graficación o análisis
posterior.

-   Utiliza estimación kernel:

La función se basa en la técnica de estimación de densidad kernel, que
calcula la densidad de probabilidad de la variable.

**¿Para qué sirve?**

-   Visualización de datos:

Es una herramienta fundamental para crear gráficos de densidad, que
ofrecen una representación fluida y continua de la distribución de una
variable.

-   Análisis de la forma de los datos:

Permite observar la forma general de la distribución, como la presencia
de picos (modas) o el sesgo.

-   Comparación de distribuciones:

Facilita la comparación visual de la distribución de diferentes grupos
de datos cuando se grafican varias curvas de densidad en el mismo
gráfico.


```r
densidad <- density(CPS1985$education)
print(densidad)
#> 
#> Call:
#> 	density.default(x = CPS1985$education)
#> 
#> Data: CPS1985$education (534 obs.);	Bandwidth 'bw' = 0.5738
#> 
#>        x                 y            
#>  Min.   : 0.2786   Min.   :1.476e-05  
#>  1st Qu.: 5.1393   1st Qu.:2.171e-03  
#>  Median :10.0000   Median :2.513e-02  
#>  Mean   :10.0000   Mean   :5.138e-02  
#>  3rd Qu.:14.8607   3rd Qu.:7.301e-02  
#>  Max.   :19.7214   Max.   :3.036e-01
```


```r
plot(density(CPS1985$education), col="violet")
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-37-1.png" width="672" />

## comparación de dos kernels


```r
library(AER)
data(CPS1988)
```

Generación de Vectores a comparar

utilizaremos la función **lines** para agregar líneas a una gáfico ya
existente y la función **legend** para etiquetar las gráficas


```r
# Genero vectores
Vector_85 <- CPS1985$education
Vector_88 <- CPS1988$education

# Cantidad de casos en las muestras

length(Vector_85)
#> [1] 534
length(Vector_88)
#> [1] 28155
```


```r
# Gráfica primera función
plot(density(Vector_88),col="blue", main="Graficas de Densidad Comparativa", ylab="Densidad")

#Gráfica segunda función
lines(density(Vector_85), col = "violet")

# Caja de leyendas
legend("topright", legend = c("Vector 1988", "Vector 1985"), col = c("blue", "violet"), lty = 1)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-40-1.png" width="672" />

## Alternativas

Como siempre en R, existen alternativas que perteneces a bibliotecas
(libraries) que hacen trabajo más vistoso con menos código


```r

# install.packages("remotes")
# remotes::install_github("R-CoderDotCom/ridgeline@main")

library(ridgeline)

ridgeline(chickwts$weight, chickwts$feed,
          mode = TRUE)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-41-1.png" width="864" />

# Estadísticos univariados normales

## Cálculo de la media

La media significa el promedio o la suma de todos los elementos
divididos entre el total de la muestra, o lo que es lo mismo es un
promedio de todos los elementos.

La media proporciona una medida de localización central de los datos. Si
los datos son datos de una muestra, la media se denota x¯ ; si los datos
son datos de una población, la media se denota con la letra griega μ .
[@anderson_2008_estadistica].

### Fórmula de la media

En las fórmulas estadísticas se usa identificar el valor de la primera
observación de la variable $x$ con $x_1$ , el valor de la segunda
observación de la variable $x$ con $x_2$ y así con lo siguiente.

En general, el valor de la i-ésima observación de la variable $x$ se
denota $x_i$ hasta la posición final del conjunto de datos $x_n$ .

La media se representa como $\bar{x}$ para la muestra o $\hat{x}$ para
la población.

Aquí la fórmula para le media.

$$\bar{x}=  \sum_{i=1}^{n}{\frac{x_i}{n}}  = \frac{x_1+x_2+x_3+ \ldots  x_n}{n}  $$

Se podría calcular a mano


```r
suma_de_x <- sum(Vector_85)
n <- length(Vector_85)
promedio_aritmetico <- suma_de_x/n
promedio_aritmetico
#> [1] 13.01873
```

Pero lo habitual es calcularlo con la función integrada


```r
mean(Vector_85)
#> [1] 13.01873
```

## Cálculo de la Mediana

La mediana refleja el valor central de los datos. Como lo dice Lind
(2015) es el punto medio de los valores una vez que se han sido
ordenados de menor a mayor o de mayor a menor. [@lind_2015_estadistica].

Algunas veces, posiblemente cuando se detectan valores atípicos o
outliers de la muestra, es necesario pensar en utilizar un concepto
llamado media recortada la cual se calcula nuevamente pero habiendo
quitando cierto porcentaje de los valores mayores y menores del
conjunto.

La función subset() filtra bajo una expresión o condición un conjunto de
datos que pueden ser vectores o data.frames. En este caso el resultado
es un vector en R llamado datos.reducido.

El propósito de la mediana es reflejar la tendencia central de la
muestra, de manera que no esté influida por los valores extremos. Dado
que las observaciones en una muestra son $x1,x2,...,xn$ , acomodados en
orden de magnitud creciente, es decir, ordenados ascendentemente, la
mediana de los datos estará dada por alguna de las maneras dependiendo
si el número de elementos es par o es impar:


```r
median(Vector_85)
#> [1] 12
```

### Cálculo del desvío estandard


```r
sd(Vector_85)
#> [1] 2.615373
```

# Datos Categóricos

Entendemos por datos categóricos a aquellos que definen la pertenencia
de un objeto estadístico a una categoría o clase de acuerdo a alguno de
sus atributos. De acuerdo con el nivel de medición los datos categóricos
corresponden a las variables medidas en escalas nominales u ordinales,
aunque aquí nos centraremos en las nominales. Una variable nominal
asigna pertenencia a una categoría excluyente, es decir, señala una
igualdad o diferencia. En términos lógicos la única operación que
podemos realizar es $a=b$ o $a \ne  b$. En el caso de las ordinales
existe una magnitud, algunas categorías tienen más y otras tienen menos
de algún atributo, por lo que es posible hacer operaciones como
$a\gt  b$ o $a \lt b$. Sin embargo esa magnitud expresa una distancia
desconocida.

## Tipos de Análisis Categóricos

| Escala de Medición | Propiedad Sistema Numérico | Operación Matemática | Ejemplos |
|-----------------|----------------------|-----------------|-----------------|
| Nominal | Identidad | Contar Frecuencias | Sexo |
| Ordinal | Magnitud | Ordenar | NSE |
| Intervalo | Distancia | Suma, Resta | Calificaciones del Mora |
| Razón | Cero indica ausencia de valor | Multiplicación, División | Ingreso, Edad |

Veamos algunos ejemplos de tratamiento de estos datos. En nuestra tabla
columnas como "gendre" , "ethnicity" u "ocupatión" son variables
Factoriales o Categóricas.

Para trabajarlas debemos construir clases que se adapten a este tipo de
datos.


```r
genero <- table (CPS1985$gender)
class(genero)
#> [1] "table"
genero
#> 
#>   male female 
#>    289    245
```

Ploteandolas tenemos


```r
plot(genero)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-47-1.png" width="672" />

Podemos usar la biblioteca kable para analizarlas como tabla


```r
library(kableExtra)
 genero %>%   kable(., caption="Tabla de conteos de la variable Género")
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```



Table: (\#tab:unnamed-chunk-48)Tabla de conteos de la variable Género

|Var1   | Freq|
|:------|----:|
|male   |  289|
|female |  245|



Variable Ocupación


```r
ocupacion <- table (CPS1985$occupation)
prop.table(ocupacion)
#> 
#>     worker  technical   services     office      sales 
#> 0.29213483 0.19662921 0.15543071 0.18164794 0.07116105 
#> management 
#> 0.10299625
kable( ocupacion , caption="Tabla de conteos de la variable Género")
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```



Table: (\#tab:unnamed-chunk-49)Tabla de conteos de la variable Género

|Var1       | Freq|
|:----------|----:|
|worker     |  156|
|technical  |  105|
|services   |   83|
|office     |   97|
|sales      |   38|
|management |   55|



Gráfica de pastel


```r
pie(ocupacion)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-50-1.png" width="672" />

## Tablas de Contingencia Bidimensionales

Las tablas de una sola variable son útiles para conocer la distribución
univariada de una variable categórica, expresada en cantidades o
proporciones. Sin embargo el análisis de datos categóricos generalmente
implica trabajar con más de una variable. Con más de una variable
también podemos trabajar con tablas, a las que llamaremos tablas de
contingencia. En función de la cantidad de variables que contemos en una
tabla de contingencia definiremos el número de dimensiones de la tabla.
Así, la anterior es una tabla de una dimensión. Una tabla de
contingencia tiene 2 o más dimensiones. Es importante no confundir el
número de categorías de las variables con el número de dimensiones de la
tabla.

Para tablas de contingencia bidimensionales visualmente las dimensiones
se nos presentan como filas y columnas. En la intersección de cada fila
y columna hay una celda que registra el conteo de las observaciones que
pertenecen a ambas categorías. En términos de conjuntos, el conteo de
objetos en la intersección de A y B. Nótese que la tabla debe incluir
todas las intersecciones posibles, dadas por las categorías de la
variable, aun cuando no haya observación en ese conjunto de datos en
particular. Se les asigna el conteo correspondiente: 0.


```r
equidada <- cbind(genero,ocupacion)
equidada
#>            genero ocupacion
#> worker        289       156
#> technical     245       105
#> services      289        83
#> office        245        97
#> sales         289        38
#> management    245        55
```


```r
library(vcd)
#> Loading required package: grid
mosaicplot(equidada)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-52-1.png" width="672" />

```r
# mosaic(equidada)
```


```r
library(vcd)

mosaic(prop.table(equidada),panel = )
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-53-1.png" width="672" />

```r

mosaic(prop.table(equidada), 
       shade=T, #Fortifico con el modelo de independencia. 
       main="Equidad en ingresos", #Pongo títulos con main=""
       sub = "Mosaico", las=3)  
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-53-2.png" width="672" />

## El modelo de independencia.

### Historia mitológica

Acompáñeme a un situación hipotética. Rexthor, the dog-bearer [@prasad2023correlation]
<https://xkcd.com/1725/>, una criatura mitológica y malvada que acecha a
los analistas cualitativos nos ha robado una tabla de contingencia, pero
ha olvidado llevarse las sumas marginales. Empecemos por agradecer que
fue Rexthor y no \\\\\\\\\\…

Preguntémonos cómo podríamos reconstruir la tabla original con esos
datos. La respuesta es: ninguna manera. Sin embargo podríamos crear una
tabla completa en la que se respeten las sumas marginales y se aproxime
**-más o menos, nunca lo sabremos–** a la tabla original.

### Proporciones y sumas marginales para una tabla de contingencia.

Cuando analizamos tablas de contingencia las proporciones marginales
<mark>totales, de fila o columna</mark> facilitan la visualización de las diferencias. La función prop.table() se encarga de calcularlos. Esta función recibe como input una tabla y regresa otra, con las proporciones en lugar de los conteos.

La sintaxis de **prop.table()** es prop.table(x, márgen), donde:  

* $x$ es un objeto de la clase table y 

* $margen$ es un número del 0 al 2 que indica el margen sobre el que se computará la proporción: 

    * 0 para el total de la tabla, 
    * 1 para las filas y 
    * 2 para la columnas. 
    
    * Para tablas de más de dos dimensiones podemos usar números mayores.

Si queremos obtener los perfiles de fila o columna podemos usar
**margin.table()**, que regresa un vector con los perfiles marginales. La sintaxis de margin.table() es 
$$margin.table(x, márgen)$$, donde

* $x$ es un objeto de la clase table y 

* $margen$ un número del 1 al 2: 

    * 1 para las sumas marginales de las filas y 
    * 2 para las columnas. Nos regresa un vector.

Si queremos agregar a la tabla las sumas marginales usamos la función

**addmargins()**, con la sintaxis 

$$addmargins(x, c(margen, margen))$$. 

El vector de márgenes creado con c() observa las mismas reglas ya expuestas. Nos regresa un objeto de la clase table con las mismas dimensiones del original al que ha agregado una fila y/o una columna para las sumas marginales.


```r
#Dos vectores de: variables categóricas.\
ISO_9000 <- c("Sí", "No", "Sí", "No", "No", "Sí", "No", "No", "No", "No")
ISO_14000 <- c("No", "No", "Sí", "Sí", "Sí", "No", "Sí", "Sí", "Sí", "Sí")

#Tablas univariadas (conteos).
ISO_9000
#>  [1] "Sí" "No" "Sí" "No" "No" "Sí" "No" "No" "No" "No"
table(ISO_9000)
#> ISO_9000
#> No Sí 
#>  7  3
```
En tanto que el conteo para normas ambieltales será


```r
ISO_14000
#>  [1] "No" "No" "Sí" "Sí" "Sí" "No" "Sí" "Sí" "Sí" "Sí"
table(ISO_14000)
#> ISO_14000
#> No Sí 
#>  3  7
```

### Tabla de contigencia por filas


```r
x <- table(ISO_9000, ISO_14000)
prop.table(x)
#>         ISO_14000
#> ISO_9000  No  Sí
#>       No 0.1 0.6
#>       Sí 0.2 0.1
```
Proporciones de filas


```r
prop.table(x,1)
#>         ISO_14000
#> ISO_9000        No        Sí
#>       No 0.1428571 0.8571429
#>       Sí 0.6666667 0.3333333
```

Proporciones porcentuales de columnas. 


```r
prop.table(x, 2)*100
#>         ISO_14000
#> ISO_9000       No       Sí
#>       No 33.33333 85.71429
#>       Sí 66.66667 14.28571
```

## Sumas marginales


```r
margin.table(x, 1)      #Filas
#> ISO_9000
#> No Sí 
#>  7  3
```


```r
margin.table(x, 2)      #Columnas
#> ISO_14000
#> No Sí 
#>  3  7
```
### Tablas adosadas


```r
#Tabla con marginales adosados. 

addmargins(x, c(1, 2))
#>         ISO_14000
#> ISO_9000 No Sí Sum
#>      No   1  6   7
#>      Sí   2  1   3
#>      Sum  3  7  10
```


## Prueba de hipótesis de independencia estadística para tablas de contingencia.

Como vimos en las tablas del ejemplo anterior los certificados de ISO9000 e ISO14000 parecen no ser las mismas personas: quién acreditan **Calidad** tiene una probabilidad baja de acreditar **Ambiental** y viceversa. Si ISO_9000 y ISI_14000 fueran variables medidas en la escala razón podríamos estimar el coeficiente de correlación, pero como son variables categóricas no es posible. Lo que sí podemos es verificar si hay alguna tipo de relación entre esas variables comparando los datos observados con una tabla ideal que presenta la distribución que recíproca que tendrían esas variables si estuvieran distribuidas al azar. Es decir, si certificar Ambiental no afectara la probabilidad de certifical Calidad y viceversa. Esa tabla ideal no existe, pero podemos crearla y **llamarla modelo de independencia:** nos indica la forma que tendrían los conteos si las variables fueran independientes. 
Si la tabla observada tiene una gran divergencia con respecto al modelo de independencia podríamos afirmar que no hay independencia entre filas y columnas: hay algo que no es el azar que está incidiendo en su distribución.



<hr>

## Conteos esperados.

Los conteos esperados se obtienen multiplicando las suma marginales
correspondientes a una celda y dividiéndola por la n.

$$ E= \frac {\sum(fila) \sum(columna)}{n} $$


```r

#Función para estimar valores esperados. 
esperados <- function (x) {
  res = matrix(rep(0, length(x)), ncol=ncol(x)) 
for(i in 1:nrow(x)) {
  for(j in 1:ncol(x)) {
    res[i,j] = (margin.table(x, 1)[i] * margin.table(x, 2)[j])/sum(x) }}
  return(res)}

#Código para ejemplo: Ya no lo voy usar.
#addmargins(x, c(1,2)) -> rexthor
#rexthor[1:2, 1:2] <- 0

#ftable(rexthor, main="La tabla robada")
```

¿Cómo lo hacemos? La forma más simple es multiplicar los conteos marginales para cada celda y luego dividirlos por la n, el total de observaciones. Las proporciones marginales indican la probabilidad de que un objeto **en el sentido estadístico** pertenezca a cierta categoría. En cada celda ubicamos el conteo según la probabilidad conjunta de la categoría de las filas y de la de las columnas. Por las proporciones marginales de la tabla robada sabemos sabemos que una observación tiene una probabilidad de $P=0.6$ de no certificar ISO9000 y $ P = 0.3$
  de no certificar ISO14000. Es decir, una probabilidad conjunta de $0.18$ obtenida al multiplica $0.6 y 0.3.$ Podemos describir a ese valor como  
  
$$ P( ISO9000_{no} | ISO14000_{no})$$ 

 : la probabilidad de no certificar ISO9000 ni ISO14000.

En esta tabla las probabilidades marginales son conocidas, pero las centrales no. Estamos usando un criterio para construirla: que las probabilidades marginales tienen información suficiente para crear la tabla y que cualquier otra variación es producto del azar. Según nuestro supuesto las únicas variables que afectan la probabilidad de cada celda son ellas mismas, el resto es azar. Este modelo reconstruye los conteos asumiendo que esas variables son independientes en su distribución, es decir, dependen solamente de ellas mismas. Por eso lo llamamos modelo de independencia: son la reconstrucción ideal de una distribución de probabilidades conjuntas en el que ambas variables son independientes.

Veamos, pues, que conteos produce el modelo de independencia para la tabla robada.


```r
espe <- esperados(x)
ftable(espe, main="Frecuencias esperadas bajo el supuesto de independencia estadística")
#>      A   B
#>           
#> A  2.1 4.9
#> B  0.9 2.1
```

Agradezcamos la amabilidad de **Rexthor, the dog-bearer**, que nos ha regresado la tabla original. Ahora podemos comparar cuan buena era la predicción de nuestro modelo. Directamente computaremos la diferencia entre los valores centrales de la tabla –los marginales ya sabemos que son iguales.


```r
residuos_crudos <- x-esperados(x)
kable(residuos_crudos, caption="Residuales crudos")
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```



Table: (\#tab:unnamed-chunk-64)Residuales crudos

|   |   No|   Sí|
|:--|----:|----:|
|No | -1.1|  1.1|
|Sí |  1.1| -1.1|




```r
library(vcd)
mosaicplot(x)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-65-1.png" width="672" />


```r
mosaic(x, 
       shade=T, #Fortifico con el modelo de independencia. 
       main="Asociación entre certificación Calidad vs Ambiental", 
       sub = "Mosaico")  
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-66-1.png" width="672" />


```r
assoc(x)    #Análisis de los residuales de Pearson. 
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-67-1.png" width="672" />

```r
assoc(x, 
      shade=T, 
      main="Asociación entre Certificación Calidad vs Ambiental", 
      sub="Residuales de Pearson")
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-68-1.png" width="672" />


# Análisis Multivariado

## La Magia de R-cran

Realizar un análisis multivariado con R-CRAN ofrece numerosas ventajas, que lo convierten en una herramienta muy popular en el ámbito de la estadística, la ciencia de datos y la investigación. A continuación, se detallan las principales:

1. **Potencia y Flexibilidad:**

Gran variedad de paquetes: R-CRAN cuenta con una enorme colección de paquetes (librerías) que extienden su funcionalidad. Para el análisis multivariado, existen paquetes especializados para técnicas como:

Análisis de Componentes Principales (PCA)

Análisis Factorial Exploratorio (EFA) y Confirmatorio (CFA)

Análisis de Clúster (K-means, jerárquico)

Modelos de Ecuaciones Estructurales (SEM)

Análisis de Correspondencias Múltiples (MCA)

Análisis Discriminante

Y muchos más...

**Capacidad de personalización:** A diferencia de muchos programas de "apuntar y hacer clic", R permite a los usuarios escribir su propio código, lo que brinda un control total sobre el análisis. Esto es ideal para resolver problemas específicos, crear funciones personalizadas y automatizar tareas repetitivas.

2. **Naturaleza Gratuita y de Código Abierto:**

Sin costo de licencia: R es un software de código abierto, lo que significa que es completamente gratuito. Esto lo hace accesible para estudiantes, investigadores, pequeñas empresas y cualquier persona que no pueda permitirse software comercial costoso.

Comunidad activa y soporte: La gran comunidad de usuarios de R contribuye a la creación de nuevos paquetes, la documentación y la resolución de problemas. Puedes encontrar una gran cantidad de foros, blogs, tutoriales y recursos en línea para ayudarte en tu camino.

3. **Reproducibilidad y Transparencia:**

Scripting: Al trabajar con R, se escribe un script o código que documenta cada paso del análisis. Esto hace que el proceso sea reproducible, lo que es fundamental en la investigación científica. Cualquiera puede ejecutar el mismo código y obtener los mismos resultados, lo que aumenta la transparencia y la confianza en los hallazgos.

Flujo de trabajo documentado: El código actúa como una bitácora del análisis. Esto facilita la colaboración con otros investigadores, la revisión de un proyecto y la identificación de posibles errores.

4. **Visualización de Datos de Alta Calidad:**

Gráficos avanzados: R es reconocido por su capacidad para crear visualizaciones de datos de gran calidad. Paquetes como ggplot2 permiten generar gráficos muy personalizables, informativos y estéticamente atractivos.

Visualización de resultados multivariados: Para el análisis multivariado, la visualización es crucial. R facilita la creación de gráficos de dispersión, biplots, dendrogramas y otras representaciones visuales que ayudan a interpretar los resultados complejos.

5. **Integración con otros lenguajes y herramientas:**

Interoperabilidad: R puede conectarse y trabajar con otros lenguajes de programación como Python, así como con bases de datos y diversas fuentes de datos (archivos de texto, CSV, Excel, etc.).

Reportes automáticos: Se puede integrar R con herramientas como R Markdown para generar informes automáticos y dinámicos que combinan el código, los resultados del análisis y el texto explicativo.


## Matrices de correlación

Una matriz de correlación multivariada es una tabla cuadrada y simétrica que muestra los coeficientes de correlación de Pearson (o de otro tipo) para cada par de variables en un conjunto de datos. En otras palabras, es una herramienta clave en el análisis multivariado que resume la fuerza y la dirección de la relación lineal entre múltiples variables simultáneamente.

### Interpretación

* Estructura: La matriz tiene el mismo número de filas y columnas que el número de variables que se están analizando.

* Diagonal principal: La diagonal principal de la matriz siempre contiene valores de 1. Esto se debe a que cada variable está perfectamente correlacionada consigo misma.

* Simetría: La matriz es simétrica. El valor de la correlación entre la variable A y la variable B es el mismo que entre la variable B y la variable A. Por lo tanto, la información en la parte superior e inferior de la diagonal es un espejo.

* Coeficientes de correlación: Los valores que no están en la diagonal son los coeficientes de correlación entre los pares de variables. Estos valores oscilan entre -1 y 1.

    * Valores cercanos a 1: Indican una correlación positiva fuerte. Cuando una variable aumenta, la otra también tiende a aumentar.

    * Valores cercanos a -1: Indican una correlación negativa fuerte. Cuando una variable aumenta, la otra tiende a disminuir.

    * Valores cercanos a 0: Indican que no existe una relación lineal fuerte entre las variables. Es importante recordar que esto no significa que no haya ninguna relación, sino que no hay una relación lineal.



```r
plot(CPS1985)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-69-1.png" width="672" />

Notemos como el paradigma de objetos nos permite utilizar el comano plot que se adapta al objeto "matriz multivariada".


```r

#install.packages("corrplot")
library(corrplot)
#> corrplot 0.95 loaded
matrizCPS1985 <- cor(CPS1985[ ,1:4])
corrplot(matrizCPS1985)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-70-1.png" width="672" />



```r
palette = colorRampPalette(c("green", "white", "red")) (20)
heatmap(x = matrizCPS1985, col = palette, symm = TRUE)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-71-1.png" width="672" />


## Fumar y productividad


```r
data("CigarettesSW")
datos_cigarros <- as.data.frame(CigarettesSW[ , - c(1,2)])
str(datos_cigarros)
#> 'data.frame':	96 obs. of  7 variables:
#>  $ cpi       : num  1.08 1.08 1.08 1.08 1.08 ...
#>  $ population: num  3973000 2327000 3184000 26444000 3209000 ...
#>  $ packs     : num  116 129 105 100 113 ...
#>  $ income    : num  4.60e+07 2.62e+07 4.40e+07 4.47e+08 4.95e+07 ...
#>  $ tax       : num  32.5 37 31 26 31 ...
#>  $ price     : num  102.2 101.5 108.6 107.8 94.3 ...
#>  $ taxs      : num  33.3 37 36.2 32.1 31 ...
```

matriz de correlación


```r
corelacion_cigarros <- cor(datos_cigarros)
corelacion_cigarros
#>                    cpi  population      packs     income
#> cpi         1.00000000  0.04758017 -0.4994643  0.2317893
#> population  0.04758017  1.00000000 -0.2112834  0.9573113
#> packs      -0.49946432 -0.21128337  1.0000000 -0.3317847
#> income      0.23178932  0.95731126 -0.3317847  1.0000000
#> tax         0.68571446  0.16598557 -0.6421176  0.3372751
#> price       0.91165558  0.14586043 -0.6524732  0.3375339
#> taxs        0.70412144  0.18891721 -0.6574167  0.3582307
#>                   tax      price       taxs
#> cpi         0.6857145  0.9116556  0.7041214
#> population  0.1659856  0.1458604  0.1889172
#> packs      -0.6421176 -0.6524732 -0.6574167
#> income      0.3372751  0.3375339  0.3582307
#> tax         1.0000000  0.8993727  0.9853330
#> price       0.8993727  1.0000000  0.9203278
#> taxs        0.9853330  0.9203278  1.0000000
```


```r
library(psych)
#> 
#> Attaching package: 'psych'
#> The following object is masked from 'package:car':
#> 
#>     logit
corPlot(corelacion_cigarros)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-74-1.png" width="672" />



```r
pairs.panels(corelacion_cigarros,
             smooth = TRUE,      # Si TRUE, dibuja ajuste suavizados de tipo loess
             scale = FALSE,      # Si TRUE, escala la fuente al grado de correlación
             density = TRUE,     # Si TRUE, añade histogramas y curvas de densidad
             ellipses = TRUE,    # Si TRUE, dibuja elipses
             method = "pearson", # Método de correlación (también "spearman" o "kendall")
             pch = 21,           # Símbolo pch
             lm = FALSE,         # Si TRUE, dibuja un ajuste lineal en lugar de un ajuste LOESS
             cor = TRUE,         # Si TRUE, agrega correlaciones
             jiggle = FALSE,     # Si TRUE, se añade ruido a los datos
             factor = 2,         # Nivel de ruido añadido a los datos
             hist.col = 4,       # Color de los histogramas
             stars = TRUE,       # Si TRUE, agrega el nivel de significación con estrellas
             ci = TRUE)          # Si TRUE, añade intervalos de confianza a los ajustes
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-75-1.png" width="672" />





## Herramientas exploratorias semi automáticas

Dataset *esoph* tiene datos referidos a correlación entre consumo de alcohol y tabaco en forma conjunta con test por contraste (casos de control) y entre casos independientes y muestra selectiva en blanco.

Utilizaremos la biblioteka **skimr**



```r
library(skimr)
skim(esoph)
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```


Table: (\#tab:unnamed-chunk-76)Data summary

|                         |      |
|:------------------------|:-----|
|Name                     |esoph |
|Number of rows           |88    |
|Number of columns        |5     |
|_______________________  |      |
|Column type frequency:   |      |
|factor                   |3     |
|numeric                  |2     |
|________________________ |      |
|Group variables          |None  |


**Variable type: factor**

|skim_variable | n_missing| complete_rate|ordered | n_unique|top_counts                         |
|:-------------|---------:|-------------:|:-------|--------:|:----------------------------------|
|agegp         |         0|             1|TRUE    |        6|45-: 16, 55-: 16, 25-: 15, 35-: 15 |
|alcgp         |         0|             1|TRUE    |        4|0-3: 23, 40-: 23, 80-: 21, 120: 21 |
|tobgp         |         0|             1|TRUE    |        4|0-9: 24, 10-: 24, 20-: 20, 30+: 20 |


**Variable type: numeric**

|skim_variable | n_missing| complete_rate| mean|    sd| p0| p25| p50| p75| p100|hist  |
|:-------------|---------:|-------------:|----:|-----:|--:|---:|---:|---:|----:|:-----|
|ncases        |         0|             1| 2.27|  2.75|  0|   0|   1|   4|   17|▇▂▁▁▁ |
|ncontrols     |         0|             1| 8.81| 12.14|  0|   1|   4|  10|   60|▇▁▁▁▁ |




## Gráficos Especiales

Algunas funciones para dibujar algunos diagramas especiales: la función 'bagplot' traza un diagrama de bolsa, 'faces' traza caras de Chernoff, 'iconplot' traza una representación de una tabla de frecuencia o una matriz de datos, 'plothulls' traza cascos de un conjunto de datos bivariados, 'plotsummary' traza un resumen gráfico de un conjunto de datos, 'puticon' agrega iconos a un gráfico, 'skyline.hist' combina varios histogramas de un conjunto de datos unidimensional en un gráfico, las funciones 'slider' admiten algunos gráficos interactivos, 'spin3R ' ayuda a inspeccionar una nube de puntos de 3 dim, 'stem.leaf' traza un gráfico de tallo y hoja, 'stem.leaf.backback' traza versiones consecutivas del gráfico de tallo y hoja.

La biblioteca **aplpack** generará rostros según la familia de flores del dataset iris.
Dada la enorme capacidad que nuestro cerebro tiene para percibir aún variaciones pequeñas entre rostros, esta técnica permite de un sólo vistazo indagar sobre un dataset completo.



```r
library("aplpack")
iris_sample<-iris[sample(1:dim(iris)[1],size=16,replace=F),]

iris_sample
#>     Sepal.Length Sepal.Width Petal.Length Petal.Width
#> 39           4.4         3.0          1.3         0.2
#> 90           5.5         2.5          4.0         1.3
#> 136          7.7         3.0          6.1         2.3
#> 54           5.5         2.3          4.0         1.3
#> 62           5.9         3.0          4.2         1.5
#> 31           4.8         3.1          1.6         0.2
#> 106          7.6         3.0          6.6         2.1
#> 150          5.9         3.0          5.1         1.8
#> 45           5.1         3.8          1.9         0.4
#> 134          6.3         2.8          5.1         1.5
#> 79           6.0         2.9          4.5         1.5
#> 78           6.7         3.0          5.0         1.7
#> 96           5.7         3.0          4.2         1.2
#> 3            4.7         3.2          1.3         0.2
#> 61           5.0         2.0          3.5         1.0
#> 65           5.6         2.9          3.6         1.3
#>        Species
#> 39      setosa
#> 90  versicolor
#> 136  virginica
#> 54  versicolor
#> 62  versicolor
#> 31      setosa
#> 106  virginica
#> 150  virginica
#> 45      setosa
#> 134  virginica
#> 79  versicolor
#> 78  versicolor
#> 96  versicolor
#> 3       setosa
#> 61  versicolor
#> 65  versicolor

faces(iris_sample[1:4],face.type=1,labels=iris_sample$Species)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-77-1.png" width="672" />

```
#> effect of variables:
#>  modified item       Var           
#>  "height of face   " "Sepal.Length"
#>  "width of face    " "Sepal.Width" 
#>  "structure of face" "Petal.Length"
#>  "height of mouth  " "Petal.Width" 
#>  "width of mouth   " "Sepal.Length"
#>  "smiling          " "Sepal.Width" 
#>  "height of eyes   " "Petal.Length"
#>  "width of eyes    " "Petal.Width" 
#>  "height of hair   " "Sepal.Length"
#>  "width of hair   "  "Sepal.Width" 
#>  "style of hair   "  "Petal.Length"
#>  "height of nose  "  "Petal.Width" 
#>  "width of nose   "  "Sepal.Length"
#>  "width of ear    "  "Sepal.Width" 
#>  "height of ear   "  "Petal.Length"
```

## Análisis Exploratŕio Automático


### DataExplorer

El paquete ***DataExplorer()*** es capaz de tomar un dataframe y generarnos un informe completo en formato html mediante el comando **create_report**. Lamentablemente el informe es interactivo y no podemos incrustarlo en este artículo. Por ello te pedimos que ejecutes desde la consola.

    library(DataExplorer)
    create_report(mtcars)
    
Este generará un exahustivo análisis de la planilla oficial de sobrevivientes del Titanic, indicando sesgos varianzas, promedios, Existencias de NA, co-varianzas, etc.


### GGally

Otra herramienta muy utilizada es GGally, tiene una enorme cantidad de gráficos que se adaptan a data.frames categoricos , lógicos, numericos, etc.


```r
library(GGally)
#> Loading required package: ggplot2
#> 
#> Attaching package: 'ggplot2'
#> The following objects are masked from 'package:psych':
#> 
#>     %+%, alpha
ggpairs(mtcars)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-78-1.png" width="672" />



```r
df <- mtcars[, c(1,3,4,5,6,7)]

ggcorr(df, palette = "RdBu", label = TRUE)
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-79-1.png" width="672" />



```r
require("survival")
# Fit survival functions
surv <- survfit(Surv(time, status) ~ sex, data = lung)
# Plot survival curves
surv.p <- ggsurv(surv)
surv.p
```

<img src="01-Ana_Exploratorio_files/figure-html/unnamed-chunk-80-1.png" width="672" />

