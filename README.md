# 29.febrero.2016
matrices, vectores, NA
### 29 de febrero ###
## not available (NA), matrices, vectores

Datos especiales: NA 's.
 
#En algunos casos las componentes de un objeto pueden no ser completamente conocidas.
#Cuando un elemento o valor es not available le asignamos el valor especial NA .
#En general una operación con elementos NA resulta NA ,
x<- NA
x+1

+
#a no ser que Mediante una opción de la función, podamos omitir o tratar los datos
#faltantes de forma especial. na.rm=FALSE (que3resultado NA cuando3
#La opción por defecto en cualquier función es3indica que NO elimina los NA ),
#que da como existe al menos un dato faltante. Con la opción na.rm=TRUE ,
#la operación se efectúa con los datos válidos.

y<-c(x,3,5,x)
#Asignamos al vector en este caso con dos valores perdidos y dos dados
#y dos NA y dos números.

#mean(y)
#Calcula la media teniendo en cuenta los NA 's.

mean(y,na.rm=TRUE)
#Calcula la media SIN tener en cuenta los NA 's.

sqrt(-17)
#Produce un Warning message avisando que es un NaN .
sqrt(-17+0i)
#Calcula el resultado y devuelve un número complejo, asi si se puede
x<-5/0
#Asignamos a x un valor innito.
exp(-x)
#Devuelve el valor 0.
exp(x)-exp(x)
#Devuelve NaN : es una indeterminación.

#### VECTORES ####

v <- numeric() #almacena en v una estructura vacía de vector numérico.
#character() es un vector de caracteres vacío, y lo mismo ocurre con otrostipos.

v[3] <- 17 #transforma componentes serán3NA ). en un vector de longitud 3, (cuyas dos primeras
## en loa entrada tres quiero que le asigne un 17
v  ## en las primeras dos entradas da NA porque no tiene nada

asignaciones
x <- 3 #es equivalente a
3 -> x
#pero no a
x < - 3 ## con espacio no funciona

x1<-logical(4) #Inicializa un vector de longitud 4 cuyos elementos son FALSE
        
x4<-character(4) #Inicializa un vector de caracteres de longitud 4
x4      
#Las comparaciones que dan un resultado lógico son:
#< (menor), <=(menor igual), > (mayor), >= (mayorigual), == (igual), != (diferente).
            
x<-c(1:10)
is.numeric(x) #resulta en TRUE
is.vector(x) # resulta en TRUE
is.complex(x) # resulta en FALSE
             ##con los renglones pasados preguntas  que es x
is.character(x)#resulta en   FALSE
x<-as.character(x) ## cambiamos a caracter
x 

nombre<-c("Luis", "María") # Vector de caracteres, generamos un vector
edad<-c(23, 24)
varon<-c(TRUE, FALSE); adult <- edad>18
adult
estatura<-c(1.77, 1.64)
estatura[2] #Devuelve 1.64, dame la estatuta de la posicion dos

#R tiene grandes facilidades para generar vectores de secuencias de números.
#El operador más usual es : desde:hasta desde ) de uno. que genera una secuencia 
#incrementos (o decremento si hasta es menor que en Este operador tiene la prioridad más alta en una #expresión. La función seq() permite generar sucesiones más complejas. Dispone
#de varios argumentos ( from, to, by, length ) = (desde, hasta, separacion entre los datos, longitud)
#Existen funciones similares que realizan los cálculos más rápidamente (muy útiles a la
#hora de programar). 
#Una función relacionada es
#rep() ,
#?seq .
#que permite duplicar un objeto de
#formas diversas. Su forma más sencilla es
#rep(x, times=5) que x , una tras otra.

pi:1 # va desde oi hasta 1
seq(0,1,length=10) ## secuencia de 0 a 1 con longitud 10
seq(3) # equivale a 1:3 y a seq(1,3)
seq(1,5,by=0.5) #secuencia de 1 a 5 con especio de .5
-1:1/0
rep(1:4,2) ## repite del 1 al 4 dos veces
rep(1:4,c(2,3,1,2)) # repita del 1 al 4 pero entre pareces va cuantas veces quieres que se relita cada numero
rep(1:4,c(2,2)) # error, tamaños no coinciden
sequence(c(2,3)) # aqui hace la secuandi del 1 al 2 y despues del 1 al 3

### MUESTRAS ###

x<-c(1:10)
sample(x,3)
sample(x) # Permutaciones de los elementos de x
y<-sample(5:15,5)
y

#### 33 VECTOR DE NOMBRES

frutos<-c(5,10,1,20) # asignamos entradas
names(frutos)<-c("pera","banana","melon","naranja") # asignamos nombre a las entradas
postre<-frutos[c("pera","melon")] # asugnamos y pedimos solo dos valores
postre ## llamamos


### MATRICES ###

matrix ()

x <- c(1:6)
dim (x) <- c(2,3)
dimnames <- list(c("Fila 1", "Fila 2"), c("COL 1", "Col 2", "Col 3"))
matriz1 <- (matrix (1:12, ncol= 3, byrow= TRUE, dimnames = list(letters [1:4], LETTERS [1:3])))
## le decimos que queremos que la matriz valla del 1 al 12 con 3 columnas, dimnbames nombre de las filas y comulnas
matriz1
matriz1 [1,1] # llamas la posicion 1,1
matriz1 [,c(2,3)] # de la matriz1 me tome a partir de la columbna dos y la tres
## en una matriz sienmpre la primera entreda son los renglones o filas
# ponemos la , para que tome todas las filas y ya indicamos cuales columnas
matriz1 [1,c(3)] # aqui ya incadicamos fila y columna

## funciones utules para trabajar con matrices

# ncol -> numero de columnas de x
#nrow -> numero de filas de x
#t(x) -> transpuesta de x
## diag(x) -> extrae diagonal de matriz o crea una matriz diagonal
# col(x) -> crea una matriz con elemento ij igual al valor j
# row -> crea una matriz con elemento ij igual al valor i
#cbind -> combina secuencia de vectores/ matrices por columnas
#rbind -> combina secuencia de vectores/ matrices por renglones

## EJEMPLO ##
 x<- matrix(1:6,2,3)
x
y <- matrix(1:6, 3, 2)
y
y[3,]; y[3]
ncol(x) ; nrow(y)
t(x)
cbind(1,x) # en laprimera columna trabaja en 1 y despues la matriz x
cbind(1:3, 1:6) #primera columna del 1 al 3 y en la seguna del 1 al 6
