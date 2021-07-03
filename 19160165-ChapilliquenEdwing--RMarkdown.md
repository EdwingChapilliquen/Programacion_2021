Resolución de la Práctica en Rmarkdown
================
19160165 ChapilliquenEdwing

# Práctica calificada 01

-----

## Problemas Ejercicios

### **1. ¿Qué cantidad de dinero sobra al repartir 10000$ entre 3 personas?**

Para este problema usaremos el operador `%%` para hallar el residuo de
una operación.

``` r
sobrante <- 10000%%3
sobrante
```

    ## [1] 1

> *rpta: Sobra 1$*

### **2. ¿Es el número 4560 divisible por 3?**

Para saber si es divisible usamos el operador `%%` para obtener el
residuo de una división, si este es igual a 0 entonces sí es divisible
por 3, si ejecuta un número diferente de 0, no es divisible por 3.

``` r
divisible <- 4560 %% 3
divisible
```

    ## [1] 0

> *rpta: Sí es divisible por 3*

### **3. Construya un vector con los números enteros del 2 al 87. ¿Cuáles de esos números son divisibles por 7?**

Se quiere saber **los números** que son divisibles en ese vector,
entonces:

``` r
vector_prob3 <- c(2:87)
```

Ahora a del `vector_prob3` extraemos aquellos números que al dividir
entre 7 tengan residuo igual a 0:

``` r
rpta_prob3 <- vector_prob3[(vector_prob3 %% 7) == 0]
rpta_prob3
```

    ##  [1]  7 14 21 28 35 42 49 56 63 70 77 84

> *rpta: Los números son: {7,14,21,28,35,42,49,56,63,70,77,84}*

### **4. Construya dos vectores, el primero con los números enteros desde 7 hasta 3, el segundo vector con los primeros cinco números positivos divisibles por 5.**

**- Sea A la condición de ser par en el primer vector.**

**- Sea B la condición de ser mayor que 10 en el segundo vector.**

**- ¿En cuál de las 5 posiciones se cumplen A y B simultáneamente?.**

Creamos los dos vectores, el primero del 7 al 3 y para el segundo se
crea un vector de los primeros cinco números divisibles entre 5.

``` r
vector1 <- 7:3 
vector1
```

    ## [1] 7 6 5 4 3

``` r
x <- 1:25
x1 <- x[(x%%5)==0]
vector2 <- x1
vector2 
```

    ## [1]  5 10 15 20 25

Para la primera condición:

``` r
A <- c()
for(i in vector1){
  if (i%%2==0)
    A <- c(A,i)
}
A
```

    ## [1] 6 4

Para la segunda condición:

``` r
B <- c()
for(i in vector2){
  if(i > 10)
    B <- c(B,i)
}
B 
```

    ## [1] 15 20 25

Para la tercera condición:

  - No se cumpliría ningún caso.

### **5. Consulte este [link](https://github.com/fhernanb/Manual-de-R/blob/master/images/anecdota_gauss.PNG) en el cual hay una anéctoda de Gauss niño. Use R para obtener el resultado de la suma solicitada por el profesor del niño Gauss.**

Notamos que el debemos hallar la sumatoria del 1 al 100 y usamos la
función `sum()`

``` r
gauss <- sum(1:100)
gauss
```

    ## [1] 5050

> *rpta: 5050*

### **6. Construya un vector con los siguientes elementos: 1, -4, 5, 9, -4. Escriba un procedimiento para extraer las posiciones donde está el valor mínimo en el vector.**

Construimos el vector y hacemos una condición, la cual nos dará por
resultado la posición del mínimo elemento.

``` r
vector3 <- c(1, -4, 5, 9, -4)
for(i in 1:length(vector3)){
  if(min(vector3)==vector3[i])
    print(i)
}
```

    ## [1] 2
    ## [1] 5

> *rpta: Los mínimos elementos se encuentran en las posiciones 2 y 5.*

### **7. Calcular 8\!**

Usamos la función `prod()` con una secuencia del 1 al 8

``` r
prob7 <- prod((1:8))
prob7
```

    ## [1] 40320

> *rpta: 40320*

### **8. Evaluar la siguiente sumatoria: ** \(\sum_{i=3}^{i=7} e^i\)

Hallamos mediante la función `sum` y definimos el número neperiano *e*

``` r
i <- c(3:7)
e <- 2.71828
prob8 <- sum(e^i)
prob8
```

    ## [1] 1723.151

> *rpta: 1723.151*

### **9. Evaluar la siguiente productoria: ** \(\prod_{i=1}^{i=10}log\sqrt(i)\)

``` r
i <- c(1:10)
prob9 <- prod(log(sqrt(i)))
prob9
```

    ## [1] 0

> *rpta: 0*

### **10. Realizar una función que permita calcular el area de una corona circular.**

<center>

![Área de segmento
circular](https://upload.wikimedia.org/wikipedia/commons/f/fb/Circularsegment.svg)

</center>

Para este caso tendremos que hacer una función que sea la resta entre
dos áreas, la primera el sector circular y la segunda el triángulo.

Entonces, para el área1 (ar1) y área2(ar2), tendremos que definir el
radio (R), teta (\(\theta\)) y la distancia (d) que será la mitad del
radio.

``` r
R=25
teta= 70 #grados
d=R/2

ar1 <- function(R,teta){
  result <- (((pi*(R^2))*teta)/360)
  return(result)
}
area1 <- ar1(R,teta)
area1
```

    ## [1] 381.7908

``` r
ar2 <- function(d,R){
  result2 <- (sqrt(R^2 - d^2))
  return(result2)
}
area2 <-ar2(d,R)
area2
```

    ## [1] 21.65064

``` r
ar_final <- area1 - area2
ar_final
```

    ## [1] 360.1401

### **11. Construya un vector cualquiera e inviertalo, es decir, que el primer elemento quede de último, el segundo de penúltimo y así sucecivamente. Compare su resultado con el de la función `rev()`**

### **12. Calcular lo siguiente:** \(\sum_{i=10}^{i=100} (i^3 +4i^2)\)

Hallamos mediante la función `sum`

``` r
i <- 10:100
prob12 <- sum(i^3 + 4*i^2)
prob12
```

    ## [1] 26852735

> *rpta: 26852735*

### **13. Calcular lo siguiente: ** \(\sum_{i=1}^{i=25} (\frac{2^i}{i} + \frac{3^i}{i^2})\)

Hallamos mediante la función `sum`

``` r
i <- 1:25
prob13 <- sum(((2^i)/i)+((3^i)/i^2))
prob13
```

    ## [1] 2129170437

> *rpta: 2129170437*

### **14. Lea el siguiente [archivo](https://raw.githubusercontent.com/fhernanb/datos/master/Paises.txt)**

**+ Calcular el número de variables del dataset** **+ ¿Cuántos países
hay en el dataset?** **+ ¿Cuál es el país con mayor población?** **+
¿Cuál es el país con alfabetización más baja?**

Para resolver el problema leemos el archivo y vemos que hay en él:

``` r
archivo <- read.delim("https://raw.githubusercontent.com/fhernanb/datos/master/Paises.txt")
head(archivo)
```

    ##           Pais poblacion alfabetizacion tasamortinf   PIB
    ## 1   Acerbaján_      7400             98        35.0  3000
    ## 2   Afganistán     20500             29       168.0   205
    ## 3     Alemania     81200             99         6.5 17539
    ## 4 Arabia_Saudí     18000             62        52.0  6651
    ## 5   Argentina_     33900             95        25.6  3408
    ## 6     Armenia_      3700             98        27.0  5000

Ahora para el primer punto llamamos la función `names()` el cual nos
dará las variables y también la función `length()`que nos dirá el
número de variables del data set:

``` r
num_var <- names(archivo)
length(num_var)
```

    ## [1] 5

> *rpta: 5*

Una vez visto lo que contiene el documento para el segundo punto,
sabemos que en las filas están los países, se utiliza la función
`nrow()` que nos indica el número de filas, o sea el número de países.

``` r
num_pai <- nrow(archivo)
num_pai 
```

    ## [1] 107

> *rpta: 107*

Para el tercer punto, usamos la función`subset()` para que nos de como
resultado el país con mayor población.

``` r
país_max_pob <- subset(archivo, poblacion==max(archivo$poblacion)) 
país_max_pob
```

    ##      Pais poblacion alfabetizacion tasamortinf PIB
    ## 25 China_   1205200             78          52 377

> *rpta: China*

Y para el último punto también usaremos la función `subet()` teniendo en
cuenta que la alfabetización debe ser la mínima.

``` r
pais_baj_alf <- subset(archivo, alfabetizacion == min(archivo$alfabetizacion))
pais_baj_alf
```

    ##            Pais poblacion alfabetizacion tasamortinf PIB
    ## 19 Burkina_Faso     10000             18         118 357

> *rpta: Burkina\_Faso*

### **15. En R hay unas base de datos incluídas, una de ellas es la base de datos llamada mtcars. Para conocer las variables que están en mtcars usted puede escribir en la consola `?mtcars`o también `help(mtcars)`. De la base de mtcars obtenga bases de datos que cumplen las siguientes condiciones.**

**+ Autos que tengan un rendimiento menor a 18 millas por galón de
combustible.** **+ Autos que tengan 4 cilindros.** **+ Autos que pesen
más de 2500 libras y tengan transmisión manual.**

Vemos primero lo que hay en el archivo mediante `head()`:

``` r
head(mtcars)
```

    ##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
    ## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
    ## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
    ## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
    ## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
    ## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
    ## Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1

En el primer punto, para un rendimiento menor a 18 millas por galon de
combustible (mpg) creamos un `subset()` que nos arroje los autos:

``` r
menor_millas <- subset(mtcars, mpg < 18.0)
menor_millas
```

    ##                      mpg cyl  disp  hp drat    wt  qsec vs am gear carb
    ## Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
    ## Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4
    ## Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
    ## Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3
    ## Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3
    ## Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4
    ## Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4
    ## Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4
    ## Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2
    ## AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2
    ## Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4
    ## Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4
    ## Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8

Para el segundo caso obtener que tengan más de 4 cilindros (cyl)

``` r
cilin_4 <- subset(mtcars, cyl == 4)
cilin_4
```

    ##                 mpg cyl  disp  hp drat    wt  qsec vs am gear carb
    ## Datsun 710     22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
    ## Merc 240D      24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
    ## Merc 230       22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
    ## Fiat 128       32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
    ## Honda Civic    30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2
    ## Toyota Corolla 33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1
    ## Toyota Corona  21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1
    ## Fiat X1-9      27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1
    ## Porsche 914-2  26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2
    ## Lotus Europa   30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2
    ## Volvo 142E     21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2

Y para el tercer caso el manual (am) está dado por el valor de 1 y más
de 2500 libras(wt):

``` r
libras_manual <- subset(mtcars, wt > 2.500 & am == 1)
libras_manual
```

    ##                 mpg cyl disp  hp drat    wt  qsec vs am gear carb
    ## Mazda RX4      21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
    ## Mazda RX4 Wag  21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
    ## Ford Pantera L 15.8   8  351 264 4.22 3.170 14.50  0  1    5    4
    ## Ferrari Dino   19.7   6  145 175 3.62 2.770 15.50  0  1    5    6
    ## Maserati Bora  15.0   8  301 335 3.54 3.570 14.60  0  1    5    8
    ## Volvo 142E     21.4   4  121 109 4.11 2.780 18.60  1  1    4    2

### **16. La ecuación de tiempo es la diferencia entre el tiempo solar medio y el tiempo solar aparente ([Referencia](http://pbarbier.com/eqtime/eqtime.html)). Si bien esta varía, la forma analítica de esta ecuación se muestra a continuación (Usar x como un rango de 0 a 365). Replicar el gráfico:**

y= 2.\(\pi\).(x-81)/365

<center>

*f(y)=9.87.sin(2y)-7.53.cos(y) - 1.5.sin(y)*

</center>
