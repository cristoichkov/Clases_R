#### Operaciones aritméticas básicas
Se pueden realizar operaciones aritméticas básicas, por lo tanto, funciona como una calculadora.

Comando para operaciones aritméticas básicas:
```
sum() ## suma

prod() ## multiplicación

sqrt() ## Raíz

exp() ## Exponencial

log() ## Logaritmo natural

log10() ## Logaritmo base 10

length() ## Número de elementos

sin() ## Seno

cos() ## Coseno

tan() ## Tangente
```
* Nota.- en R y en muchos otros lenguajes de programación, el símbolo `#` se utiliza para comentar los códigos.

#### Asignación de variables
Se pueden asignar valores a una variable utilizando el símbolo `=` o `<-`. Los mas apropiado es utilizar la flecha, ya que el símbolo igual puede ocasionar confusiones en la interpretación de los códigos tanto para el lenguaje y el humano.    

```
x <- 3 ## se pueden asignar números
y <- 6
x*y ## y realizar operaciones entre las variables

example <- "skull" ##  para asignar palabras o letras se tienen que poner entre comillas
```

<p align="center">
<img src= "R_as_var.png" width="300">
</p>
<p align="center">
Figura 1.- El nombre de la variable puede ser cualquiera que el usuario elija, se recomienda que no tenga espacios ni caracteres especiales.
</p>

#### Tipos de variables


**Variable**.- valor de una característica que interese registrar de un objeto de estudio.

***Cualitativas***.- se refieren a características o cualidades que no pueden ser medidas con números.

**Nominal**.-  presenta modalidades no numéricas que no admiten un criterio de orden. Ejemplo:
  - Color de pétalos: rojo, azul, amarillo y naranja.
  - Margen de la hoja: dentado, aserrado, lobado y entero.


**Ordinal**.- presenta modalidades no numéricas, en las que existe un orden. Ejemplos:
  - Vértebra.- primera, segunda, tercera, etc.
  - Raíz.- principal, secundaria y terciaria.

***Cuantitativa***.- se refiere a atributos que expresan una cantidad o cantidad de magnitud y por tanto toma valores numéricos.

**Discreta**.- son variables numéricas que tienen un número contable de valores. Ejemplo:
  - Número de espinas.- 15, 17, 25, 28, etc.
  - Número de tépalos.- 20, 18, 36, 23, etc.

**Continua**.- son variables numéricas que tienen un número infinito de valores. Ejemplo:
 - Longitud de la región hilomicropilar.- 1.2, 2.3, 1.8, 3.2, etc.
 - Ancho del tallo.- 7.8, 4.6, 6.5, 5.6, 6.6, etc.


#### Estructuras de datos en R

Tipos de datos en R:
```
## Numéricos - Cuantitativos

## variable cuantitativa discreta
typeof(5L) ## es necesario poner L después del número para forzar a que sea un integer

## variable cuantitativa continua
typeof(5.5) ## double en otros lenguajes se conocen como float, son números que permiten decimales

## variable cualitativa - R siempre tomara las variables cualitativas como nominales

typeof("skull") ## character siempre se ponen entre comillas

## si se quiere dar orden a una variable cualitativa en R se tiene que especificar con un comando que se explicara mas adelante

```

#### Vectores

Un vector es una estructura de datos básica en R que contiene elementos del mismo tipo.


**Crear vectores**

Ejemplo 1.- En R los vectores son generalmente creados usando la funcion `c()`.
```
## Ejemplo de vector

vec_num <- c(2, 3, 6, 2, 7, 10, 23)

typeof(vec_num)

class(vec_num)

vec_char <- c("blanco", "rojo", "azul", "rojo") ## siempre entre comillas

typeof(vec_chr)

class(vec_chr)

vec <- c(1, 4, "blanco", "azul") ## que resultado nos da?

## Para conocer cuantos elementos contiene un vector se utiliza la función  lenght()

lenght(vec_num)
```

Ejemplo 2.- Crear un vector usando el operador `:`
```
x <- 1:7

y <- 2:-2
```

Ejemplo 3.- Crear un vector con la función seq()
```
seq(1, 3, by=0.2)  ## crea un vector del 1 al 3 incrementando 0.2 cada vez

seq(1, 5, length.out=4) ## crea un vector del 1 al 5 con 4 elementos
```

Ejemplo 4.- Crear un vector con la función rep()
```
rep(c(0, 0, 7), times = 3) ## el vector se repetiré 3 veces

rep(c(2, 4, 2), each = 3) ## se repetirá cada elemento del vector tres veces,  

rep(c(0, 7), times = c(4,2)) ## el primer elemento del vector se repetirá 4 veces y el segundo 2 veces
```


**Acceder a los elementos de un vector**


Se puede acceder a los elementos de un vector mediante indexación vectorial. El índice vectorial en R comienza desde 1, a diferencia de la mayoría de los lenguajes de programación donde el índice comienza desde 0 (p. ej. python).

```
vec_num <- c(2, 3, 6, 2, 7, 10, 23)

vec_num[3] ## acceder al tercer elemento

vec_num[c(2, 4)]  ## acceder al segundo y cuarto elemento

vec_num[-6]  ## selecciona todos los elementos excepto el sexto

vec_num[vec_num < 7]  ## filtra los elemento menores a 7

vec_num[vec_num <= 7]  ## filtra los elemento menores o iguales a 7
```
**Operaciones con vectores**

Las operaciones aritméticas de vectores se realizan elemento por elemento.

```
x <- c(2, 3, 5, 4, 3)

x + 5  ## sumar 5 a cada elemento del vectores

x * 5  ## multiplicar cada elemento por 5

y <- c(5, 4, 8, 7, 10)

x + y ## los dos vectores tienen que ser de la misma longitud


## si los vectores tienen longitudes diferentes y el mayor es múltiplo del menor
## se reciclan los números del menor.

x <- c(1, 5) ## longitud 2

y <- c(5, 2, 4, 5, 4, 2, 4, 5) ## longitud 8

x + y

## se suma el elemento 1 de x al elemento 1 de y así sucesivamente hasta completar la
## longitud de x, ahora el elemento 1 de x se suma al elemento 3 de y y así sucesivamente.
```

**Combinar vectores**

```
fruits <- c("Apple", "oranges", "banana")

vegetables <- c("cabbage", "spinach", "tomatoes")

all_basket_items <- c(fruits, vegetables)

## fruits seran los primeros elemento seguidos de vegetables

all_basket_items
```
