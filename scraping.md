# Práctica de Web Scraping Ampliada

## Importar librerías 

Ahora importo la libería [requests](https://docs.python-requests.org/en/latest/)

Es utilizada para importar los datos de una web y las peticiones web.


```python
import requests
```

Voy a importar de la librería [bs4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) `BeautifulSoup`


```python
from bs4 import BeautifulSoup
```

Es una biblioteca de Python para analizar documentos HTML que te has descargado. 

## Variables

Explicación de las variables que definirán y clasificarán los datos de la web. Para poder estudiar y definir la muestra en función de los datos disponibles en la web elegida.

### Definimos URL

La URL que hemos escogido es un listado de los páises con más medallas olímpicas elaborada por El País.


```python
URL = "https://resultados.elpais.com/deportivos/juegos-olimpicos/medallero/"
```

### Realizamos la petición a la web

Si el estatus code no es `200` no se puede leer la página, si el code es 200, te sale el mensaje "vamos a por ellos". Por lo que el code sirve para restingrir a los buscadores y las lecturas de la página

Los mensjaes que nos saldrán si el code es o no es `200´


```python
req = requests.get(URL)
if (req.status_code != 200):
    raise Exception("No se puede hacer Web Scraping en"+ URL)
if (req.status_code == 200):
    print("Vamos a por ello")
```

### De resquests a BeautifulSoup

Pasamos el contenido HTML de la web a un objeto BeautifulSoup(), que significa el objeto BeautifulSoup representa el documento analizado como un todo. En la mayoría de los casos, puede tratarlo como un objeto Etiqueta.


```python
html = BeautifulSoup(req.text, "html.parser")
```

### Variables de datos

Definimos las variables `paises`, `oros`, `platas`, `bronces` y `totales`; y las identificamos con la función `find_all()`, que significa buscar todos y analizar todas estas variables de datos (relacionados con los Juegos Olímpicos).


```python
  paises = html.find_all("th",{"class":"pais"})
  oros = html.find_all("td",{"class":"m_oro"})
  platas = html.find_all("td",{"class":"m_plata"})
  bronces = html.find_all("td",{"class":"m_bronce"})
  totales = html.find_all("td",{"class":"m_total"})
```

## Hacemos la pregunta


```python
La pregunta es un método de asegurarse de que el usuario quiere recibir el listado del País.
Hacemos la pregunta definitiva que nos dará paso a la solución final,
```


```python
respuesta=input('¿QUIERES CONOCER LOS 20 PAÍSES QUE HAN OBTENIDO MÁS MEDALLAS EN 2020?\n \n Si tu respuesta es Sí, presiona "s" \n')
if(respuesta == 's'): 
    print('\nDe acuerdo\n')
  

```

    ¿QUIERES CONOCER LOS 20 PAÍSES QUE HAN OBTENIDO MÁS MEDALLAS EN 2020?
     
     Si tu respuesta es Sí, presiona "s" 
    s
    
    De acuerdo
    
    

## Bucle para obtener los datos

Tiene la funcionalidad de obtener todos los divs, donde están las entradas. El bucle se utiliza para recorrer los elementos de un objeto iterable (lista, tupla, conjunto, diccionario, …) y ejecutar un bloque de código.

Al ejecutar el bucle, hemos programado para que salgan los resultados de búsqueda y si la función es falsa, salga "Qué lástima, y...".



```python
print('\nRESULTADOS DE LOS DATOS DE LOS JUEGOS OLÍMPICOS 2020\n')
print ('PAÍSES')

for i in range (20):
    # Con el método "getText()" no nos devuelve el HTML
    print("%d. %s \nOro: %s Plata: %s Bronce: %s \n Total: %s \n " % (i+1, paises[i+1].text.strip(),oros[i].text.strip(),platas[i].text.strip(),bronces[i].text.strip(), totales[i].text.strip()))

else:
  print('Qué lástima, y...')
```


```python

```
