#### importar datos a R

Muchas veces importar datos a R puede ser frustrante, la clave es saber que tipo archivo queremos cargar y sus características. Tener esta información previa ayudara a elegir la función y los argumentos adecuados.

#### Importar archivos `.txt`.

Si tenemos un archivo `.txt` o separado por tabuladores, la función que nos ayudara a importar este formato es `read.table()` o `read.delim()`.

```
rad_spin <- read.table("radial_spine_length.txt")

## Observa los encabezados
## Pide ayuda a R y busca el argumento que te ayuda a poner los encabezados como nombres de columnas.

rad_spin <- read.delim("radial_spine_length.txt")

## Observa los encavezados

```

#### Importar archivos `.csv`.

Si tenemos un archivo `.csv` o separado por comas, la función que nos ayudara a importar este formato es `read.csv()`.

```
rad_spin <- read.csv("radial_spine_length.csv")

## Observa los encabezados
```

#### Guardar datos `data.frame` o `matrix` en formato `.txt` o `.csv`.

Los objetos de tipo `data.frame` y `matrix` pueden ser guardados en un archivo manteniendo su estructura.

```
data("iris")

write.table(iris, file = "iris.txt")

write.csv(iris, file = "iris.csv")
```

#### Ejercicios

1.- Descarga el repositorio de la clase y descomprimelo.

2.- Ve a la carpeta de Clase_5 y crea una carpeta que se llame `bin`.

3.- En `RStudio` genera un nuevo `script`.

4.- Establece tu `working directory` en la carpeta `bin`.

5.- Importa el archivo `ejercicio.txt` que se encuentra en la carpeta `data`.

   * Los encabezados tienen que ser los nombres de las columnas.
   * Elige la primera columna como nombres de filas
   * Elige la primera columna como nombres de fila

6.- Carga la base de datos de `iris`.

7.- Guardala en formato en formato `.txt` separado por comas en la carpeta data.

   * Al guardarlo elimina las comillas.

#### Estructuras de control cíclicas (`loops`)

Este tipo de estructura permite repetir una cantidad de veces cualquiera una serie se instrucciones. En R podemos ejecutar dos tipos `loops`: for y while.

#### `for loop`

Ejecuta un `loop` una cantidad fija de veces. La estructura de un `for loop` es la siguiente:

```
for (variable in vector){
  operación
}
```
Ejemplos.-

```
## Creamos un vector vació
vec <- vector()

for (i in 1:10) {  ## 1:10 = [1]  1  2  3  4  5  6  7  8  9 10
  vec[i] <- i      ## guardara cada número en el vector
}

## si tenemos muchos archivos que queremos importar y unir en un solo dataframe

## la función list.files crea un vector con el nombre de los archivos que tengamos en nuestra carpeta
iris_files <- list.files(".", pattern = "flower")

## revisamos el vector
iris_files

## creamos un dataframe vació
iris_prub <- data.frame()

## tomara cada elemento del vector iris_files
for (i in iris_files) {
  df_iris <- read.csv(i)   ## importara cada elemento del vector
  iris_prub <- rbind(iris_prub, df_iris)  ## combinara por filas cada archivo importado
}
```

Ejercicio.-
```
iris_mean <- data.frame()

for (i in 1:4){

  df_mean <- data.frame(mean(iris[,i]))

  col_name <- data.frame(colnames(iris)[i])

  df_iris <- cbind(col_name, df_mean)

  iris_mean <- rbind(iris_mean, df_iris)
}
```
1.- Describe que hace cada paso del loop

2.- Cuales son los nombres de las columnas del df iris_mean

3.- Modifica el `loop` para que los nombres de las columnas sean `flower_part` y `mean`.

4.- Intenta modificar el `loop` para obtener la media de cada parte floral por especie. 
