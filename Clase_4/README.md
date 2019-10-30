#### Listas

Una lista en R es un objeto que consiste en una colección de objetos ordenados conocidos como *componentes*. Los tipos de datos que podemos almacenar en una lista van desde simples caracteres, números, vectores, matrices, data frames, entre otros tipos de objetos.

#### Crear una Listas

Podemos crear una lista utilizando la función `list()`

```
chr <- "A" ## asignar un carácter

num <- 23  ## asignar un número

vec_num <- c(2, 3, 6, 2, 7, 10, 23)  ## crear un vector numérico

vec_char <- c("blanco", "rojo", "azul", "rojo")  ## crear un vector de caracteres

mat_char <- matrix(c("uno", "dos", "tres"),3,3)  ## crear una matriz de caracteres

mat_num <- matrix(1:12,3,4)  ## crear una matriz numérica

iris <- iris  ##  asignar un data frame

## Crear la lista con todos los objetos antes creados utilizando la función list

all_obj <- list(chr, num, vec_num, vec_char, mat_char, mat_num, iris)
```

#### Acceder a los componentes de una lista

```
## los componentes de las listas se encuentran en el orden que se colocaron
str(all_obj)  ## en este caso la lista all_obj contiene 7 componentes

## Para entrar a los componentes de utiliza doble corchete

all_obj[[3]]  

all_obj[[5]]

all_obj[[7]]

## Para entrar a los elementos de cada componente de utiliza corchetes

all_obj[[3]][3]

all_obj[[5]][3,2]

all_obj[[7]][1:50, ]
```

#### Cambiar los nombres de los componentes de una lista

```
names(all_obj) <- c("one", "two", "three", "four", "five", "six", "seven")

## ahora podremos acceder a los componentes de una lista utilizando el operador `$`

all_obj$one

all_obj$four

all_obj$four[4]

all_obj$six[2,4]

all_obj$seven$Species
```

#### Agregar y quitar componentes a una lista
```
eight <- c(3,4,3,6,7)  ## crear nuevo vector

all_obj[[8]] <- eight   ## guardarlo en la lista en la posición 8

all_obj[["eight"]] <- eight   ## guardarlo con un nombre

all_obj[[8]] <- NULL  ## eliminar el octavo elemento
```

####  Rutas (path, en inglés)

Las rutas sirven para localizar un archivo o carpeta, siguiendo una estructura de directorios o árbol de directorios.

```
/
└── home/
    └── cactus/
        └── Documentos/
            └── Clases_R/
                └── Clase_4/
                     ├── README.md
                     ├── data/
                     │   └── Radial_Spine_P01.csv
                     ├── meta/  
                     │   └── Info_data.csv
                     ├── out/
                     │   └── Results.txt
                     └── bin/
                         └── Read_Radial_Spine.r
```

#### Rutas relativas y absolutas
Una ruta *absoluta* representa la ruta completa del recurso. Dicho de otra forma, se parte desde el directorio raíz hasta llegar al recurso.

```
/home/cactus/Documentos/Clases_R/Clase_4/data/Mediciones.csv
```

Las rutas relativas representa sólo una parte de la ruta. Esto es posible porque en las rutas relativas se tiene en cuenta el directorio actual de trabajo.

```
Clases_R/Clase_4/data/Mediciones.csv
```
#### Directorio de trabajo (Working directory)

El directorio de trabajo (wd) es dónde estamos, al menos que le indiques lo contrario, todo archivo que se genere como parte de la ejecución de un programa se guardará aquí. También este será el lugar donde cualquier programa/script buscará los archivos que le pidas, y NO los encontrará si no están exactamente ahí.

Las rutas utilizan dos símbolos especiales, un punto (.) y dos puntos seguidos (..). Los dos puntos seguidos se utilizan para subir en la jerarquía. Un único punto representa el directorio actual.

#### Obtener la ruta del directorio de trabajo en R
```
## Ejemplo con base en la estructura anterior

getwd()

[1] "/home/cactus"
```

#### Cambiar de directorio de trabajo en R

Para cambiar de directorio hay que ir a `Session` -> `Set Working Directory`. Existen tres opciones para seleccionar el directorio.

`To Source File Location`.- Cuando abramos un script y seleccionemos esta opción, el wd se establecerá en el lugar donde tengamos guardado el script.

`To Files Pane Location`.- El wd se establecerá en donde indiquemos que están nuestros archivos de acuerdo al panel de Files.

`Choose Directory...`.- Se abrirá una ventana donde podremos seleccionar la carpeta que sera nuestro wd, también podemos activar esta opción con la combinación de teclas `ctrl+shift+H`.

Otra opción es utilizar la función `setwd()`

```
setwd("/home/cactus/Stoich_repos/Clases_R/Clase_4/bin")
```
