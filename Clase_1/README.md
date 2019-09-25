
### R es un lenguaje de programación orientada a objetos

##### Operaciones aritmeticas basicas
Se pueden realizar operaciones aritméticas básicas, por lo tanto, funciona como una calculadora.

Comando para operaciones aritméticas básicas:
```
sum() ## suma

prod() ## multiplicación

sqrt() ## Raíz

exp() ## Exponencial

log() ## Logaritmo natural

log10() ## Logaritmo base 10

length() ## N´umero de elementos

sin() ## Seno

cos() ## Coseno

tan() ## Tangente
```
* Nota.- en R y en muchos otros lenguajes de programación, el simbolo `#` se utiliza para comentar los códigos.

##### Asignación de variables
Se pueden asignar valores a una variable utilizando el simbolo `=` o `<-`. Los mas apropiado es utilizar la flecha, ya que el símbolo igual puede ocasionar confusiones en la interpretación de los códigos tanto para el lenguaje y el humano.    

```
x <- 3 ## se pueden asignar números
y <- 6
x*y ## y realizar operaciones entre las variables

example <- "skull" ##  para asignar palabras o letras se tienen que poner entre comillas
```

##### Tipos de variables


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


 ##### Estructuras de datos en R

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

**Vectores**.- es una estructura de datos básica en R que contiene elementos del mismo tipo.
