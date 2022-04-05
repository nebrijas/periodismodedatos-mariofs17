# Pasos
Los pasos que vamos a tener que hacer para poder hacer scraping por la web son:

## Instalación de Pandas
La instalación de [pandas](https://github.com/nebrijas/periodismodedatos-mariofs17/blob/main/api-covid19-pandas.ipynb) sirve para escribir datos en CSV, Excel, HDF5 y para poder crear, seleccionar y filtrar las tablas de datos. En este caso nos centramos en el estudio de la API de Covid-19, con el fin de poder obtener los datos acerca del desarrollo de la pandemia en diferentes países. Recordar hacer uso de la orden ```!pip install pandas```

## Configuración
A continuación importamos las librerías ```import pandas as pd``` , que es un tipo de librería con la que recoger los datos para importar la biblioteca de análisis de Pandas a Python.

## Variables
La [URL](https://api.covid19api.com/countries "URL") es básica para que el programa trabaje con unos datos y pueda crear los listados y tablas. En este caso hace referencia a los datos disponibles del COVID-19. 

## Creación de dataframe
Utilizamos la función ```read_json``` para leer los datos en JSON de la API:
Básicamente el dataframe sirve para guardar y manipular conjuntos datos en distintos tipos de columnas o tablas. Conocido como "cruzar datos". 


## Explorar tabla
- Cabecera
- Cola
- Info

Para explorar los datos de la tabla utilizaremos el código ```df.tail ()``` . Con el paréntesis podemos determinar el número concreto de la fila que queremos visualizar. Si el paréntesis está vacío, el propio programa nos dará los 5 primeros o últimos valores (head o cola tail)
Con la función df.describe() se realizó una descripción númerica de la tabla y con el código df.info(), se pudo consultar un resumen del dataframe con el fin de conocer si hay o no celdas vacías en esta tabla. Df significa dataframe.

## Acceso a datos

En esta sección utilizaremos la orden: df['Country'], para obtener los datos que se encuentren en "Country" y que estos se muestren en columnas. 
Además, hicimos una prueba para que se imprimiera justo el país que aparece en la posición 200 de la lista a través de la orden df['Country'][200], en el que el resultado fue Angola.  


## Tiempo real España

## Tiempo real Colombia

## Comparativa España-Colombia

## Triple comparativa

## Seleccionar más columnas

## Tipos de gráfico

## Exportar datos
En este último aparatdo utilizaremos las funciones ```vs.to_csv('vs.csv')```y ```vs2.to_csv('vs2.csv')``` , para guardar ambas comparativas en un archivo CSV (para guardar los datos en un formato de tabla estructurada). 
También, debemos guardar los gráficos relativos utilizando la siguiente función: ```grafico =vs.plot() fig = grafico.get_figure() fig.savefig('vs.png')```.
Los archivos se guardarán en png
 





