# Plantico
Los datos a importar deben estar contenidos en un excel con el nombre de "DatosTabla" deben tener los siguientes titulos organizados en columnas Tratamiento Tiempo Longitud. Se debe comprobar que el archivo está abierto en la sección de Environment en RStudio. Algunas formas de ayuda para localizar los archivos son la función file.choose() Observacion: Si bien los datos que estan indicados son para la variable longitud, esta variable puede ser cambiada por otra que sea de interes por el investigador Un ejemplo de importar el excel en la consola es el siguiente:

DatosTabla <- read_excel("Aquisedebeutilizarfile.choose()parasaberlaruta/DatosTabla.xlsx",col_types = c("text","text","numeric"))

un ejemplo de utiizacion de Plantico sería:

install.packages("devtools")

library(devtools)

require(devtools)

install_github("kbqt14/Plantico")

library(Plantico)

require("Plantico")

require(dplyr)

require(readxl)

require(psych)

require(ggplot2)


Al correr el paquete podemos utilizar sus funciones

Resumentiempo_t  permite ver el numero de tratamientos, la media, mediana, y otros parametros estadisticos descriptivos.

Un ejemplo de utilizacion es la siguiente

Resumentiempo_t(DatosTabla, 1)

Al ejecutar esta función se tendran los resultados para el día 1.


El paquete cuenta con la posibilidad de filtrar los distintos tiempos con sus respectivos tratamientos y generar asi una tabla resumen con el analisis de varianza a distintos tiempos y prueba a posteriori de Tukey y grafica de boxplot en el tiempo que uno indique. Para ello se debe utilizar la funcion Tabla_t_A de la siguiente forma para obtener el analisis de varianza, Test de Tukey y boxplot:

Tabla_t_A(DatosTabla, 1 )para ANOVA y boxplot de los tratamientos del tiempo 1,

Tabla_t_A(DatosTabla, 2 )para ANOVA y boxplot de los tratamientos del tiempo 2, y así sucesivamente para los tiempos de interés


Para obtener una grafica de barras de un tiempo en especifico se puede utilizar la funion Graficadebarratiempo_t 
Un ejemplo de utilizacion seria Graficadebarratiempo_t(DatosTabla,2) donde se podrán observar los resultados del dia 2. 

Para elaborar un grafico de lineas se puede utilizar la funcion Grafico_lineas_tiempo_t 
El ejemplo de utilizacion seria Grafico_lineas_tiempo_t(DatosTabla,7) Donde mostraria el grafico de lineas hasta el dia 7, sin embargo esto se puede editar segun la necesidad del usuario.

El objetivo del paquete es poder utilizar los datos estadisticos descriptivos y de esta manera obtener conclusiones respecto a las plantas que son sometidas a estrés por con concentraciones de distintas sustancias.
