# Redes Neuronales artificiales

Las redes neuronales artificiales son modelos computacionales inspirados en el funcionamiento del cerebro humano. Están compuestas por una serie de unidades llamadas neuronas artificiales, que están conectadas entre sí a través de conexiones ponderadas. Estas conexiones permiten a las redes neuronales procesar información y realizar tareas de aprendizaje y predicción.

![Neurona Humana](images/Neuron3.png)

En ingeniería industrial, las redes neuronales artificiales se utilizan en una amplia variedad de aplicaciones, como:

1. Pronóstico de demanda: Las redes neuronales pueden utilizarse para predecir la demanda futura de productos o servicios en función de datos históricos, ayudando así a la planificación de la producción y la gestión de inventarios.

2. Control de procesos: Las redes neuronales pueden utilizarse para controlar y optimizar procesos industriales. Pueden aprender de los datos recopilados en tiempo real y ajustar los parámetros del sistema para maximizar la eficiencia y minimizar los errores.

3. Mantenimiento predictivo: Las redes neuronales pueden utilizarse para predecir fallos y realizar mantenimiento predictivo en maquinaria y equipos industriales. Al analizar datos de sensores y patrones de fallas anteriores, las redes neuronales pueden identificar señales de advertencia temprana y ayudar a evitar costosas interrupciones en la producción.

4. Control de calidad: Las redes neuronales pueden utilizarse para realizar inspección y control de calidad en productos manufacturados. Pueden identificar defectos o anomalías en imágenes, señales o datos sensoriales, ayudando a mejorar la calidad del producto final.

5. Optimización de la cadena de suministro: Las redes neuronales pueden utilizarse para optimizar la gestión de la cadena de suministro, analizando grandes volúmenes de datos y tomando decisiones óptimas en tiempo real sobre inventario, distribución y logística.

La ventaja de las redes neuronales artificiales en ingeniería industrial radica en su capacidad para modelar relaciones complejas y no lineales entre variables, así como en su capacidad de aprendizaje a partir de datos. Sin embargo, es importante tener en cuenta que el uso de redes neuronales artificiales requiere una adecuada preparación y procesamiento de los datos, así como una validación y ajuste adecuados de los modelos para garantizar resultados confiables y precisos.[@zermane_development_2022]


![Ejemplo de una red neuronal artificial de una capa occulta](images/ann.png)

* Si la ANN (Artificial Neural Net) tiene sólo una neurona de salida actua como clasificador dicotómico de la entrada.

* Si tiene varios niveles o categorías del tipo binario puede actuar como clasificador categórico

* Si tiene una salida de doble precisión puede actuar como predictor (clustering)

## Bibliografía recomendada

![Análisis de datos categóricos](images/book_12.png)


## Redes Neuronales en R-Cran

En R-Cran, puedes implementar redes neuronales artificiales utilizando la biblioteca "neuralnet". Esta biblioteca proporciona funciones para construir y entrenar redes neuronales de una o varias capas en R.

Aquí hay un ejemplo básico de cómo construir y entrenar una red neuronal artificial utilizando la biblioteca "neuralnet" en R-Cran:

1. Instalación del paquete "neuralnet":


    install.packages("neuralnet")


2. Carga del paquete "neuralnet":


    library(neuralnet)


3. Preparación de los datos de entrenamiento y prueba:

Supongamos que tienes un conjunto de datos con variables de entrada (predictoras) llamadas "x1" y "x2" y una variable de salida (objetivo) llamada "y". Debes dividir tus datos en conjuntos de entrenamiento y prueba. Aquí hay un ejemplo de cómo puedes hacerlo:


    set.seed(123)  # Establecer una semilla aleatoria para reproducibilidad

      # Dividir datos en conjuntos de entrenamiento y prueba

    train_indices <- sample(1:nrow(tus_datos), nrow(tus_datos)*0.8)  # 80% de los datos para entrenamiento
    train_data <- tus_datos[train_indices, ]
    test_data <- tus_datos[-train_indices, ]


4. Construcción de la red neuronal:

Aquí puedes definir la arquitectura de tu red neuronal especificando el número de nodos en cada capa oculta. Por ejemplo, una red con una capa oculta de 5 nodos se puede definir de la siguiente manera:

  
    # Definir la fórmula de la red neuronal
    formula <- y ~ x1 + x2

Crear la red neuronal

    nn <- neuralnet(formula, data = train_data, hidden = c(5))


En este ejemplo, "formula" especifica la relación entre las variables de entrada y salida, y "hidden" indica el número de nodos en la capa oculta.

5. Entrenamiento de la red neuronal:

Utiliza la función "train" para entrenar la red neuronal con los datos de entrenamiento:


Entrenar la red neuronal

    trained_nn <- train(nn)


6. Predicción con la red neuronal entrenada:

Utiliza la función "compute" para realizar predicciones con la red neuronal entrenada:


Realizar predicciones con la red neuronal

    predictions <- compute(trained_nn, test_data[, c("x1", "x2")])


En este ejemplo, "test_data[, c("x1", "x2")]" son las variables de entrada para las cuales deseas realizar predicciones.

Este es solo un ejemplo básico para construir y entrenar una red neuronal artificial en R-Cran utilizando la biblioteca "neuralnet". Puedes consultar la documentación de la biblioteca para obtener más información sobre las funciones y opciones disponibles.[@morizet_classification_2016]

## Caso de estudio: Cargar de bibliotecas


```r
library(neuralnet)  # regression

library(nnet) # classification 

library(NeuralNetTools)

library(plyr)
```



## Carga de Datos


```r
library(readr)
Startups <- read_csv("https://ricardorpalma.github.io/R-Dataset/50_Startups_LAC.csv")
#> Rows: 50 Columns: 6
#> ── Column specification ────────────────────────────────────
#> Delimiter: ","
#> chr (1): Pais
#> dbl (5): R_D_Spend, POM, Logist_Market, Profit, Superviv...
#> 
#> ℹ Use `spec()` to retrieve the full column specification for this data.
#> ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```


```r
Categoric <- read_csv("https://ricardorpalma.github.io/R-Dataset//50_Startups_Categoric_LAC.csv")
#> Rows: 50 Columns: 6
#> ── Column specification ────────────────────────────────────
#> Delimiter: ","
#> chr (2): Pais, Supervivencia
#> dbl (4): R_D_Spend, POM, Logist_Market, Profit
#> 
#> ℹ Use `spec()` to retrieve the full column specification for this data.
#> ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

La columna supervivencia de la tabla Categoric tiene etiquetas que identifican la situación en la que terminaron los emprendimientos, a saber:

* **SpinOf** La empresa se separó de una principal y logró su independencia económica

* **RevEq** La empresa alcanzó su punto de equilibrio canceló su deuda con el banco y fue comprada por la competencia.

* **BankR** La empresa no prosperó y el banco se quedó con los activos que vendidos no compensaron el preśtamo inicial (Banca Rota).



## Tratamiento de variables categóricas





```r
tabla1 <- table(Categoric$Pais)
tabla2 <- table(Categoric$Supervivencia)
tabla3 <- table(Categoric$Pais,Categoric$Supervivencia)
```



```r
plot(tabla1, col=c("red","green","blue"))
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-5-1.png" width="672" />


```r
plot(tabla2, col=c("red","green","blue"))
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-6-1.png" width="672" />



```r
plot(tabla3, col=c("red","green","blue"))
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-7-1.png" width="672" />


## Histogramas superpuestos



```r
ind_1 <- which(Categoric$Pais=="Colombia")
p1 <- as.matrix(Categoric[ind_1,5])

ind_2 <- which(Categoric$Pais=="Ecuador")
p2 <- as.matrix(Categoric[ind_2,5])

ind_3 <- which(Categoric$Pais=="Chile")
p3 <- as.matrix(Categoric[ind_3,5])
```


```r
hp1 <- hist(p1)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-9-1.png" width="672" />

```r
hp2 <- hist(p2)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-9-2.png" width="672" />

```r
hp3 <- hist(p3)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-9-3.png" width="672" />

```r

par(mfrow=c(3,1))
plot( hp1, col=rgb(0,0,1,1/4), xlim=c(30000,200000),ylim=c(0,5),main="Ecuador")
plot( hp2, col=rgb(1,0,0,1/4),xlim=c(30000,200000),ylim=c(0,10),main="Colombia") 
plot( hp3, col=rgb(1,0,0,1/4),xlim=c(30000,200000),ylim=c(0,10),main="Chile") 
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-9-4.png" width="672" />



```r
par(mfrow=c(1,3))
plot( hp1, col=rgb(0,0,1,1/4), xlim=c(30000,200000),ylim=c(0,5),main="Ecuador")
plot( hp2, col=rgb(1,0,0,1/4),xlim=c(30000,200000),ylim=c(0,10),main="Colombia") 
plot( hp3, col=rgb(1,0,0,1/4),xlim=c(30000,200000),ylim=c(0,10),main="Chile") 
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-10-1.png" width="672" />





```r
pairs(Categoric[ ,1:3])
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-11-1.png" width="672" />


```r
boxplot(Categoric[ ,1:3])
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-12-1.png" width="672" />




```r
Categoric$Pais <- as.numeric(revalue(Categoric$Pais,
                          c("Colombia"="0", "Ecuador"="1",
                            "Chile"="2")))
#> Warning: NAs introducidos por coerción
```

## Cuadro de campos categóricos


```r
Categoric$Supervivencia <- as.numeric(revalue(Categoric$Supervivencia,
                          c("BankR"="0", "RevEq"="1",
                            "SpinOff"="2")))
```

## Profit versus País



```r
plot(Categoric$Pais, Categoric$Profit)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-15-1.png" width="672" />


## Visualización de Tablas

Tabla Textual


```r

library(kableExtra)
kable(head(Categoric), "pipe",  booktabs = TRUE)%>% kable_styling(font_size = 8)
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```

<table class="table" style="font-size: 8px; margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:right;"> R_D_Spend </th>
   <th style="text-align:right;"> POM </th>
   <th style="text-align:right;"> Logist_Market </th>
   <th style="text-align:right;"> Pais </th>
   <th style="text-align:right;"> Profit </th>
   <th style="text-align:right;"> Supervivencia </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 165349.2 </td>
   <td style="text-align:right;"> 136897.80 </td>
   <td style="text-align:right;"> 471784.1 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 192261.8 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 162597.7 </td>
   <td style="text-align:right;"> 151377.59 </td>
   <td style="text-align:right;"> 443898.5 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 191792.1 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 153441.5 </td>
   <td style="text-align:right;"> 101145.55 </td>
   <td style="text-align:right;"> 407934.5 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 191050.4 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 144372.4 </td>
   <td style="text-align:right;"> 118671.85 </td>
   <td style="text-align:right;"> 383199.6 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 182902.0 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 142107.3 </td>
   <td style="text-align:right;"> 91391.77 </td>
   <td style="text-align:right;"> 366168.4 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 166187.9 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 131876.9 </td>
   <td style="text-align:right;"> 99814.71 </td>
   <td style="text-align:right;"> 362861.4 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 156991.1 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
</tbody>
</table>




Tabla Simple


```r
kable(head(Categoric), "simple")
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")

#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```



 R_D_Spend         POM   Logist_Market   Pais     Profit   Supervivencia
----------  ----------  --------------  -----  ---------  --------------
  165349.2   136897.80        471784.1      0   192261.8               2
  162597.7   151377.59        443898.5      1   191792.1               2
  153441.5   101145.55        407934.5      2   191050.4               2
  144372.4   118671.85        383199.6      0   182902.0               2
  142107.3    91391.77        366168.4      2   166187.9               2
  131876.9    99814.71        362861.4      0   156991.1               2





```r
kbl(Categoric)  %>%
  kable_paper("hover", full_width = F)
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```

<table class=" lightable-paper lightable-hover" style='font-family: "Arial Narrow", arial, helvetica, sans-serif; width: auto !important; margin-left: auto; margin-right: auto;'>
 <thead>
  <tr>
   <th style="text-align:right;"> R_D_Spend </th>
   <th style="text-align:right;"> POM </th>
   <th style="text-align:right;"> Logist_Market </th>
   <th style="text-align:right;"> Pais </th>
   <th style="text-align:right;"> Profit </th>
   <th style="text-align:right;"> Supervivencia </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 165349.20 </td>
   <td style="text-align:right;"> 136897.80 </td>
   <td style="text-align:right;"> 471784.10 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 192261.83 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 162597.70 </td>
   <td style="text-align:right;"> 151377.59 </td>
   <td style="text-align:right;"> 443898.53 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 191792.06 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 153441.51 </td>
   <td style="text-align:right;"> 101145.55 </td>
   <td style="text-align:right;"> 407934.54 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 191050.39 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 144372.41 </td>
   <td style="text-align:right;"> 118671.85 </td>
   <td style="text-align:right;"> 383199.62 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 182901.99 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 142107.34 </td>
   <td style="text-align:right;"> 91391.77 </td>
   <td style="text-align:right;"> 366168.42 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 166187.94 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 131876.90 </td>
   <td style="text-align:right;"> 99814.71 </td>
   <td style="text-align:right;"> 362861.36 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 156991.12 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 134615.46 </td>
   <td style="text-align:right;"> 147198.87 </td>
   <td style="text-align:right;"> 127716.82 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 156122.51 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 130298.13 </td>
   <td style="text-align:right;"> 145530.06 </td>
   <td style="text-align:right;"> 323876.68 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 155752.60 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 120542.52 </td>
   <td style="text-align:right;"> 148718.95 </td>
   <td style="text-align:right;"> 311613.29 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 152211.77 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 123334.88 </td>
   <td style="text-align:right;"> 108679.17 </td>
   <td style="text-align:right;"> 304981.62 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 149759.96 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 101913.08 </td>
   <td style="text-align:right;"> 110594.11 </td>
   <td style="text-align:right;"> 229160.95 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 146121.95 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 100671.96 </td>
   <td style="text-align:right;"> 91790.61 </td>
   <td style="text-align:right;"> 249744.55 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 144259.40 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 93863.75 </td>
   <td style="text-align:right;"> 127320.38 </td>
   <td style="text-align:right;"> 249839.44 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 141585.52 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 91992.39 </td>
   <td style="text-align:right;"> 135495.07 </td>
   <td style="text-align:right;"> 252664.93 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 134307.35 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 119943.24 </td>
   <td style="text-align:right;"> 156547.42 </td>
   <td style="text-align:right;"> 256512.92 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 132602.65 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 114523.61 </td>
   <td style="text-align:right;"> 122616.84 </td>
   <td style="text-align:right;"> 261776.23 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 129917.04 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 78013.11 </td>
   <td style="text-align:right;"> 121597.55 </td>
   <td style="text-align:right;"> 264346.06 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 126992.93 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 94657.16 </td>
   <td style="text-align:right;"> 145077.58 </td>
   <td style="text-align:right;"> 282574.31 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 125370.37 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 91749.16 </td>
   <td style="text-align:right;"> 114175.79 </td>
   <td style="text-align:right;"> 294919.57 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 124266.90 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 86419.70 </td>
   <td style="text-align:right;"> 153514.11 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 122776.86 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 76253.86 </td>
   <td style="text-align:right;"> 113867.30 </td>
   <td style="text-align:right;"> 298664.47 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 118474.03 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 78389.47 </td>
   <td style="text-align:right;"> 153773.43 </td>
   <td style="text-align:right;"> 299737.29 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 111313.02 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 73994.56 </td>
   <td style="text-align:right;"> 122782.75 </td>
   <td style="text-align:right;"> 303319.26 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 110352.25 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 67532.53 </td>
   <td style="text-align:right;"> 105751.03 </td>
   <td style="text-align:right;"> 304768.73 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 108733.99 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 77044.01 </td>
   <td style="text-align:right;"> 99281.34 </td>
   <td style="text-align:right;"> 140574.81 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 108552.04 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 64664.71 </td>
   <td style="text-align:right;"> 139553.16 </td>
   <td style="text-align:right;"> 137962.62 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 107404.34 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 75328.87 </td>
   <td style="text-align:right;"> 144135.98 </td>
   <td style="text-align:right;"> 134050.07 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 105733.54 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 72107.60 </td>
   <td style="text-align:right;"> 127864.55 </td>
   <td style="text-align:right;"> 353183.81 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 105008.31 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 66051.52 </td>
   <td style="text-align:right;"> 182645.56 </td>
   <td style="text-align:right;"> 118148.20 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 103282.38 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 65605.48 </td>
   <td style="text-align:right;"> 153032.06 </td>
   <td style="text-align:right;"> 107138.38 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 101004.64 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 61994.48 </td>
   <td style="text-align:right;"> 115641.28 </td>
   <td style="text-align:right;"> 91131.24 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 99937.59 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 61136.38 </td>
   <td style="text-align:right;"> 152701.92 </td>
   <td style="text-align:right;"> 88218.23 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 97483.56 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 63408.86 </td>
   <td style="text-align:right;"> 129219.61 </td>
   <td style="text-align:right;"> 46085.25 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 97427.84 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 55493.95 </td>
   <td style="text-align:right;"> 103057.49 </td>
   <td style="text-align:right;"> 214634.81 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 96778.92 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 46426.07 </td>
   <td style="text-align:right;"> 157693.92 </td>
   <td style="text-align:right;"> 210797.67 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 96712.80 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 46014.02 </td>
   <td style="text-align:right;"> 85047.44 </td>
   <td style="text-align:right;"> 205517.64 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 96479.51 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 28663.76 </td>
   <td style="text-align:right;"> 127056.21 </td>
   <td style="text-align:right;"> 201126.82 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 90708.19 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 44069.95 </td>
   <td style="text-align:right;"> 51283.14 </td>
   <td style="text-align:right;"> 197029.42 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 89949.14 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 20229.59 </td>
   <td style="text-align:right;"> 65947.93 </td>
   <td style="text-align:right;"> 185265.10 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 81229.06 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 38558.51 </td>
   <td style="text-align:right;"> 82982.09 </td>
   <td style="text-align:right;"> 174999.30 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 81005.76 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 28754.33 </td>
   <td style="text-align:right;"> 118546.05 </td>
   <td style="text-align:right;"> 172795.67 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 78239.91 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 27892.92 </td>
   <td style="text-align:right;"> 84710.77 </td>
   <td style="text-align:right;"> 164470.71 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 77798.83 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 23640.93 </td>
   <td style="text-align:right;"> 96189.63 </td>
   <td style="text-align:right;"> 148001.11 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 71498.49 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 15505.73 </td>
   <td style="text-align:right;"> 127382.30 </td>
   <td style="text-align:right;"> 35534.17 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 69758.98 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 22177.74 </td>
   <td style="text-align:right;"> 154806.14 </td>
   <td style="text-align:right;"> 28334.72 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 65200.33 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 1000.23 </td>
   <td style="text-align:right;"> 124153.04 </td>
   <td style="text-align:right;"> 1903.93 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 64926.08 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 1315.46 </td>
   <td style="text-align:right;"> 115816.21 </td>
   <td style="text-align:right;"> 297114.46 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 49490.75 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 135426.92 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 42559.73 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 542.05 </td>
   <td style="text-align:right;"> 51743.15 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 35673.41 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 116983.80 </td>
   <td style="text-align:right;"> 45173.06 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 14681.40 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
</tbody>
</table>




```r
na.omit(Categoric) %>%
  kbl(caption = "Tablas estilo Tesis Di3") %>%
  kable_classic(full_width = F, html_font = "Cambria")
#> Warning: 'xfun::attr()' is deprecated.
#> Use 'xfun::attr2()' instead.
#> See help("Deprecated")
```

<table class=" lightable-classic" style="font-family: Cambria; width: auto !important; margin-left: auto; margin-right: auto;">
<caption>(\#tab:unnamed-chunk-19)Tablas estilo Tesis Di3</caption>
 <thead>
  <tr>
   <th style="text-align:right;"> R_D_Spend </th>
   <th style="text-align:right;"> POM </th>
   <th style="text-align:right;"> Logist_Market </th>
   <th style="text-align:right;"> Pais </th>
   <th style="text-align:right;"> Profit </th>
   <th style="text-align:right;"> Supervivencia </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 165349.20 </td>
   <td style="text-align:right;"> 136897.80 </td>
   <td style="text-align:right;"> 471784.10 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 192261.83 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 162597.70 </td>
   <td style="text-align:right;"> 151377.59 </td>
   <td style="text-align:right;"> 443898.53 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 191792.06 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 153441.51 </td>
   <td style="text-align:right;"> 101145.55 </td>
   <td style="text-align:right;"> 407934.54 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 191050.39 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 144372.41 </td>
   <td style="text-align:right;"> 118671.85 </td>
   <td style="text-align:right;"> 383199.62 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 182901.99 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 142107.34 </td>
   <td style="text-align:right;"> 91391.77 </td>
   <td style="text-align:right;"> 366168.42 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 166187.94 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 131876.90 </td>
   <td style="text-align:right;"> 99814.71 </td>
   <td style="text-align:right;"> 362861.36 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 156991.12 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 134615.46 </td>
   <td style="text-align:right;"> 147198.87 </td>
   <td style="text-align:right;"> 127716.82 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 156122.51 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 130298.13 </td>
   <td style="text-align:right;"> 145530.06 </td>
   <td style="text-align:right;"> 323876.68 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 155752.60 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 120542.52 </td>
   <td style="text-align:right;"> 148718.95 </td>
   <td style="text-align:right;"> 311613.29 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 152211.77 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 123334.88 </td>
   <td style="text-align:right;"> 108679.17 </td>
   <td style="text-align:right;"> 304981.62 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 149759.96 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 100671.96 </td>
   <td style="text-align:right;"> 91790.61 </td>
   <td style="text-align:right;"> 249744.55 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 144259.40 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 93863.75 </td>
   <td style="text-align:right;"> 127320.38 </td>
   <td style="text-align:right;"> 249839.44 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 141585.52 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 119943.24 </td>
   <td style="text-align:right;"> 156547.42 </td>
   <td style="text-align:right;"> 256512.92 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 132602.65 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 114523.61 </td>
   <td style="text-align:right;"> 122616.84 </td>
   <td style="text-align:right;"> 261776.23 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 129917.04 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 78013.11 </td>
   <td style="text-align:right;"> 121597.55 </td>
   <td style="text-align:right;"> 264346.06 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 126992.93 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 94657.16 </td>
   <td style="text-align:right;"> 145077.58 </td>
   <td style="text-align:right;"> 282574.31 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 125370.37 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 86419.70 </td>
   <td style="text-align:right;"> 153514.11 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 122776.86 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 76253.86 </td>
   <td style="text-align:right;"> 113867.30 </td>
   <td style="text-align:right;"> 298664.47 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 118474.03 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 78389.47 </td>
   <td style="text-align:right;"> 153773.43 </td>
   <td style="text-align:right;"> 299737.29 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 111313.02 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 67532.53 </td>
   <td style="text-align:right;"> 105751.03 </td>
   <td style="text-align:right;"> 304768.73 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 108733.99 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 64664.71 </td>
   <td style="text-align:right;"> 139553.16 </td>
   <td style="text-align:right;"> 137962.62 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 107404.34 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 75328.87 </td>
   <td style="text-align:right;"> 144135.98 </td>
   <td style="text-align:right;"> 134050.07 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 105733.54 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 72107.60 </td>
   <td style="text-align:right;"> 127864.55 </td>
   <td style="text-align:right;"> 353183.81 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 105008.31 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 66051.52 </td>
   <td style="text-align:right;"> 182645.56 </td>
   <td style="text-align:right;"> 118148.20 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 103282.38 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 61994.48 </td>
   <td style="text-align:right;"> 115641.28 </td>
   <td style="text-align:right;"> 91131.24 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 99937.59 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 61136.38 </td>
   <td style="text-align:right;"> 152701.92 </td>
   <td style="text-align:right;"> 88218.23 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 97483.56 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 55493.95 </td>
   <td style="text-align:right;"> 103057.49 </td>
   <td style="text-align:right;"> 214634.81 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 96778.92 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 46426.07 </td>
   <td style="text-align:right;"> 157693.92 </td>
   <td style="text-align:right;"> 210797.67 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 96712.80 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 46014.02 </td>
   <td style="text-align:right;"> 85047.44 </td>
   <td style="text-align:right;"> 205517.64 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 96479.51 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 44069.95 </td>
   <td style="text-align:right;"> 51283.14 </td>
   <td style="text-align:right;"> 197029.42 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 89949.14 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 20229.59 </td>
   <td style="text-align:right;"> 65947.93 </td>
   <td style="text-align:right;"> 185265.10 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 81229.06 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 38558.51 </td>
   <td style="text-align:right;"> 82982.09 </td>
   <td style="text-align:right;"> 174999.30 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 81005.76 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 28754.33 </td>
   <td style="text-align:right;"> 118546.05 </td>
   <td style="text-align:right;"> 172795.67 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 78239.91 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 27892.92 </td>
   <td style="text-align:right;"> 84710.77 </td>
   <td style="text-align:right;"> 164470.71 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 77798.83 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 15505.73 </td>
   <td style="text-align:right;"> 127382.30 </td>
   <td style="text-align:right;"> 35534.17 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 69758.98 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 22177.74 </td>
   <td style="text-align:right;"> 154806.14 </td>
   <td style="text-align:right;"> 28334.72 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 65200.33 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 1315.46 </td>
   <td style="text-align:right;"> 115816.21 </td>
   <td style="text-align:right;"> 297114.46 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 49490.75 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 135426.92 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 42559.73 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 542.05 </td>
   <td style="text-align:right;"> 51743.15 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 35673.41 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 116983.80 </td>
   <td style="text-align:right;"> 45173.06 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 14681.40 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
</tbody>
</table>




## Normailización


Eliminaremos los datos que tienen NA


```r
Categoric <- na.omit(Categoric)
```



```r
normalize<-function(x){
  return ( (x-min(x))/(max(x)-min(x)))
}

Startups_norm<-as.data.frame(lapply(Categoric,FUN=normalize))
summary(Startups_norm$Profit)
#>    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
#>  0.0000  0.4116  0.5259  0.5581  0.7374  1.0000
```

Datos Originales y Datos normalizados


```r
head(Categoric$Profit)
#> [1] 192261.8 191792.1 191050.4 182902.0 166187.9 156991.1
head(Startups_norm)
#>   R_D_Spend       POM Logist_Market Pais    Profit
#> 1 1.0000000 0.6517439     1.0000000  0.0 1.0000000
#> 2 0.9833595 0.7619717     0.9408934  0.5 0.9973546
#> 3 0.9279846 0.3795790     0.8646636  1.0 0.9931781
#> 4 0.8731364 0.5129984     0.8122351  0.0 0.9472924
#> 5 0.8594377 0.3053280     0.7761356  1.0 0.8531714
#> 6 0.7975660 0.3694479     0.7691259  0.0 0.8013818
#>   Supervivencia
#> 1             1
#> 2             1
#> 3             1
#> 4             1
#> 5             1
#> 6             1
```


Muestreo para entrenamento


```r
indice <- sample(2, nrow(Startups_norm), replace = TRUE, prob = c(0.7,0.3))
startups_train <- Startups_norm[indice==1,]
startups_test  <- Startups_norm[indice==2,]
```



## Modelo de Neural Net




```r
library(neuralnet)
attach(Categoric)

startups_model <- neuralnet(Profit ~ R_D_Spend+ POM + Logist_Market + Pais , data = startups_train)

str(startups_model)
#> List of 14
#>  $ call               : language neuralnet(formula = Profit ~ R_D_Spend + POM + Logist_Market +      Pais, data = startups_train)
#>  $ response           : num [1:30, 1] 0.997 0.993 0.801 0.796 0.794 ...
#>   ..- attr(*, "dimnames")=List of 2
#>   .. ..$ : chr [1:30] "2" "3" "6" "7" ...
#>   .. ..$ : chr "Profit"
#>  $ covariate          : num [1:30, 1:4] 0.983 0.928 0.798 0.814 0.788 ...
#>   ..- attr(*, "dimnames")=List of 2
#>   .. ..$ : chr [1:30] "2" "3" "6" "7" ...
#>   .. ..$ : chr [1:4] "R_D_Spend" "POM" "Logist_Market" "Pais"
#>  $ model.list         :List of 2
#>   ..$ response : chr "Profit"
#>   ..$ variables: chr [1:4] "R_D_Spend" "POM" "Logist_Market" "Pais"
#>  $ err.fct            :function (x, y)  
#>   ..- attr(*, "type")= chr "sse"
#>  $ act.fct            :function (x)  
#>   ..- attr(*, "type")= chr "logistic"
#>  $ linear.output      : logi TRUE
#>  $ data               :'data.frame':	30 obs. of  6 variables:
#>   ..$ R_D_Spend    : num [1:30] 0.983 0.928 0.798 0.814 0.788 ...
#>   ..$ POM          : num [1:30] 0.762 0.38 0.369 0.73 0.717 ...
#>   ..$ Logist_Market: num [1:30] 0.941 0.865 0.769 0.271 0.686 ...
#>   ..$ Pais         : num [1:30] 0.5 1 0 0.5 1 0 0.5 0.5 1 0 ...
#>   ..$ Profit       : num [1:30] 0.997 0.993 0.801 0.796 0.794 ...
#>   ..$ Supervivencia: num [1:30] 1 1 1 1 1 1 0.5 0.5 0.5 0.5 ...
#>  $ exclude            : NULL
#>  $ net.result         :List of 1
#>   ..$ : num [1:30, 1] 0.911 0.9 0.832 0.825 0.836 ...
#>   .. ..- attr(*, "dimnames")=List of 2
#>   .. .. ..$ : chr [1:30] "2" "3" "6" "7" ...
#>   .. .. ..$ : NULL
#>  $ weights            :List of 1
#>   ..$ :List of 2
#>   .. ..$ : num [1:5, 1] -1.8371 4.1142 -0.0806 0.3251 0.1266
#>   .. ..$ : num [1:2, 1] 0.0516 0.9286
#>  $ generalized.weights:List of 1
#>   ..$ : num [1:30, 1:4] 3.25 3.35 3.67 3.68 3.65 ...
#>   .. ..- attr(*, "dimnames")=List of 2
#>   .. .. ..$ : chr [1:30] "2" "3" "6" "7" ...
#>   .. .. ..$ : NULL
#>  $ startweights       :List of 1
#>   ..$ :List of 2
#>   .. ..$ : num [1:5, 1] 0.124 -0.661 0.343 -1.603 0.438
#>   .. ..$ : num [1:2, 1] -0.685 -0.509
#>  $ result.matrix      : num [1:10, 1] 0.05496 0.00932 180 -1.83714 4.11423 ...
#>   ..- attr(*, "dimnames")=List of 2
#>   .. ..$ : chr [1:10] "error" "reached.threshold" "steps" "Intercept.to.1layhid1" ...
#>   .. ..$ : NULL
#>  - attr(*, "class")= chr "nn"
```


## Ploteo de la red Neuronal



```r
plot(startups_model, rep = "best")
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-25-1.png" width="672" />

## Ploteo de la red proporcional

Esto me indica cuales son los KPI


```r
par(mar = numeric(4), family = 'serif')
plotnet(startups_model, alpha = 0.6)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-26-1.png" width="672" />



### Evaluación de la performance del modelo



```r
model_results <- compute(startups_model,startups_test[1:4])
predicted_profit <- model_results$net.result
```


##  Predicted profit Vs Actual profit of test data.


```r
cor(predicted_profit,startups_test$Profit)
#>           [,1]
#> [1,] 0.9628344
```




## Desnormalización de los resultados

Dado que hicimos la predicciones con los datos normalizados, ahora deberemos des-normalizarlos [@gholizadeh_prediction_2020]




```r

str_max <- max(Startups$Profit)
str_min <- min(Startups$Profit)

unnormalize <- function(x, min, max) { 
  return( (max - min)*x + min )
}

ActualProfit_pred <- unnormalize(predicted_profit,str_min,str_max)
head(ActualProfit_pred)
#>        [,1]
#> 1  176806.7
#> 4  168710.2
#> 5  169998.1
#> 13 155767.9
#> 15 118832.5
#> 24 103573.9
```


## Mejoramiento de la performance del modelo

Es posible mejorar la performance con el agregado de más capas ocultas.



```r
Startups_model2 <- neuralnet(Profit~R_D_Spend+ POM + Logist_Market + Pais , data = startups_train, hidden = c(2,4))

plot(Startups_model2 ,rep = "best")
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-30-1.png" width="672" />


## Performance del modelo mejorado


```r
model_results2<-compute(Startups_model2,startups_test[1:4])
predicted_Profit2<-model_results2$net.result
cor(predicted_Profit2,startups_test$Profit)
#>           [,1]
#> [1,] 0.9609024
```


## Modelo Mejorado KPI


```r
par(mar = numeric(4), family = 'serif')
plotnet(Startups_model2, alpha = 0.6)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-32-1.png" width="672" />

## Neural Net Clasificación

Armamos el dataset de datos a clasificar



```r
library(nnet)

supervivencia <- as.factor(Categoric$Supervivencia)
R_D_Spend <- as.matrix(Categoric$R_D_Spend)
POM <- as.matrix(Categoric$POM)
Logist_Market <- as.matrix(Categoric$Logist_Market)
Clasificar <- data.frame (supervivencia,R_D_Spend,POM,Logist_Market)
```

## Muestreo


```r
indice <- sample(2, nrow(Clasificar), replace = TRUE, prob = c(0.7,0.3))

clasificar_train <- Startups_norm[indice==1,]
clasificar_test  <- Startups_norm[indice==2,]

supervivientes_clasificados <- factor(clasificar_train$Supervivencia)
```



Entrenamiento de nnet como clasificador



```r
supervivientes_train<-nnet(supervivientes_clasificados~clasificar_train$R_D_Spend + clasificar_train$POM+ clasificar_train$Logist_Market ,data=clasificar_train,size=5, decay=5e-4, maxit=2000)
#> # weights:  38
#> initial  value 30.618845 
#> iter  10 value 9.920325
#> iter  20 value 4.196626
#> iter  30 value 2.889551
#> iter  40 value 2.073058
#> iter  50 value 1.613938
#> iter  60 value 1.539713
#> iter  70 value 1.432790
#> iter  80 value 1.375105
#> iter  90 value 1.325779
#> iter 100 value 1.231268
#> iter 110 value 1.190554
#> iter 120 value 1.179915
#> iter 130 value 1.173316
#> iter 140 value 1.165143
#> iter 150 value 1.150997
#> iter 160 value 1.145478
#> iter 170 value 1.142106
#> iter 180 value 1.138962
#> iter 190 value 1.137330
#> iter 200 value 1.136549
#> iter 210 value 1.135992
#> iter 220 value 1.135597
#> iter 230 value 1.134803
#> iter 240 value 1.130649
#> iter 250 value 1.127304
#> iter 260 value 1.121489
#> iter 270 value 1.118144
#> iter 280 value 1.113116
#> iter 290 value 1.109477
#> iter 300 value 1.104146
#> iter 310 value 1.096284
#> iter 320 value 1.093635
#> iter 330 value 1.091332
#> iter 340 value 1.090065
#> iter 350 value 1.089239
#> iter 360 value 1.088488
#> iter 370 value 1.088024
#> iter 380 value 1.087684
#> iter 390 value 1.087383
#> iter 400 value 1.087240
#> iter 410 value 1.087149
#> iter 420 value 1.087081
#> iter 430 value 1.087052
#> iter 440 value 1.087023
#> iter 450 value 1.087006
#> iter 460 value 1.086995
#> iter 470 value 1.086992
#> iter 480 value 1.086989
#> iter 490 value 1.086983
#> iter 500 value 1.086981
#> iter 510 value 1.086980
#> iter 520 value 1.086978
#> final  value 1.086978 
#> converged
```


## Visualización del clasificador


```r
library(NeuralNetTools)
plotnet(supervivientes_train, alpha = 0.6)
```

<img src="05-Neural_Net_files/figure-html/unnamed-chunk-36-1.png" width="672" />



## Lecturas complementarias

### Estilos de Tablas
<https://cran-r--project-org.translate.goog/web/packages/kableExtra/vignettes/awesome_table_in_html.html?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc#Table_Styles>







