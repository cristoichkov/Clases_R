#### Data frames

Data frame podría traducirse como: Hoja de datos o marco de datos. La estructura de un data frame es muy similar a la de una matriz, la diferencia es que una matriz solo admite valores de un mismo tipo, mientras que en un data frame puede incluir diferente tipos de datos.

|   Tipo          |   Ejemplo   |     R     |
|-----------------|:-----------:|:---------:|
|Entero           |      1      |  integer  |
|Cadena de texto  |    "uno"    | character |
|Factor           |     uno     | factor    |
|Lógico           |    TRUE     | logical   |
|Perdido          |     NA      | NA        |

#### Factor
Los factores son usados para representar las variables cualitativas o categóricas. Por defecto los factores no tienen orden (variable cualitativa nominal), pero el usuario puede establecer un orden (variable cualitativa ordinal). Los factores son importantes ya que serán utilizados análisis estadísticos y gráficos.

```
## tenemos un vector con varios meses y algunos se repiten
meses <- c("mayo", "junio", "abril", "noviembre", "octubre", "mayo", "mayo", "junio", "abril", "octubre", "noviembre", "enero", "enero")
class(meses)
meses

## convertir meses a factores
meses <- factor(meses)
class(meses)
meses

## R ordena los niveles alfabéticamente
## 1-abril, 2-enero, 3-junio, 4-mayo, 5-noviembre, 6-octubre
str(meses)

## ordenar los niveles diferente
meses_fac2 <- factor(meses, levels = c("enero", "abril", "mayo", "junio", "octubre", "noviembre"))

## 1-enero, 2-abril, 3-mayo, 4-junio, 5-octubre, 6-noviembre
str(meses_fac2)

summary(meses_fac2) ## resumen de nuestros datos
```

#### Lógico
Las expresiones booleanas son declaraciones lógicas que son verdaderas o falsas. Para nuestros propósitos, a menudo usaremos expresiones booleanas para comparar cantidades. Por ejemplo, la expresión booleana `1<2` es verdadera, mientras que la expresión booleana `1>2` es falsa.

| Operador  |   Descripción            |
|-----------|:------------------------:|
|<          |menor que                 |
|<=         |menor o igual que         |
|>          |mayor que                 |
|>=         |mayor o igual que         |
|==         |igual que                 |
|!=         |no igual que              |
| x&#124;y  |x or y                    |
|x&y        |x and y                   |

```
## x or y
x <- c(1:10)
x[(x>8) | (x<5)]
```

##### Datos perdidos
Los valores faltantes (missing data) se representan con el símbolo `NA`. Es importante saber si nuestros datos tienen datos faltantes, ya que generalmente las pruebas estadísticas son sensibles o no aceptan NAs.

```
## vector con missing data
x <- c(1:4, NA, 6:7, NA)

## existen NAs en nuestros datos?
is.na(x)

## eliminar NAs de un vector
x <- x[!is.na(x)]
```

#### Crear Data Frames
Se pueden crear data frames (`df`) con la función `data.frame()`.
```
## crear vectores con diferentes tipos de datos
entero <- 1:4
factor <- factor(c("a", "b", "c", "d"))
numero <- c(1.2, 3.4, 4.5, 5.6)
cadena <- as.character(c("a", "b", "c", "d"))
logico <- as.logical(c("TRUE", "FALSE", "FALSE", "TRUE"))

## unir todos los vectores en un df
mi_df <- data.frame(entero, factor, numero, cadena, logico)

## ver la estructura del df
str(mi_df)
```
#### Set de datos *Iris*
Ronald Fisher trabajo con tres especies de *Iris* (*I. setosa*, *I. virginica* e *I. versicolor*), he hizo la medición del largo y ancho del pétalo y sépalo. Estos cuantifican la variación morfológica de la flor, todas las medidas están en centímetros.

<p align="center">
<img src="iris.png" width="600">
</p>
<p align="center">
</p>

#### Visualización rápida de Datos
```
head(iris) ## ver las primeras 6 filas

tail(iris) ## ver las ultimas 6 filas

str(iris) ## estructura de Datos

summary(iris) ## resumen rápido de los datos

colnames(iris) ## nombres de las columnas

nrow(iris) ## número de filas = # de observaciones

ncol(iris) ## número de columnas = # de variables
```

#### Manipulación de data frames
Es similar a una matriz, por lo tanto se pueden utilizar los mismos comandos.

Ejercicio:
```
## Extrae las variables Species y Sepal.Width

## Selecciona las observaciones del 51 al 100

## Selecciona las observaciones del 1 al 50 y del 101 al 150

## Cambia los nombres de las columnas (Especies, Petalo_Ancho, Petalo_Largo, Sepalo_Ancho, Sepalo_Largo)

## Obtén el promedio del ancho del sépalo por especie
```
