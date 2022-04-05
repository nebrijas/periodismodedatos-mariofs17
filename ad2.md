# Actividad dirigida 2

En cuanto a la práctica de Web Scraping realizada sobre los [Datos de los Juegos Olímpicos de 2020](https://resultados.elpais.com/deportivos/juegos-olimpicos/medallero/). Lo primero que realizamos fue la creación de una librerías [requests](https://docs.python-requests.org/en/latest/), que es utilizada para importar los datos de una web y las peticiones. Importaremos el [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), que es una biblioteca de Python para analizar documentos HTML que te has descargado.

El siguente paso será el de definir las variables de estudio del documento junto con la definción de la [URL](https://resultados.elpais.com/deportivos/juegos-olimpicos/medallero/). Para poder estudiar y definir la muestra en función de los datos disponibles en la web elegida.

Continuamos con la petición a la web, con la primera variable definida (Si el estatus code no es 200 no se puede leer la página).
Con las primeras condiciones de búsqueda presentadas en con los if.

Pasamos de resquests a BeautifulSoup, que significa el objeto BeautifulSoup representa el documento analizado como un todo. En la mayoría de los casos, puede tratarlo como un objeto Etiqueta.

Definimos las variables de datos: las variables paises, oros, platas, bronces y totales; y las identificamos con la función find_all(), que significa buscar todos y analizar todas estas variables de datos (relacionados con los Juegos Olímpicos).

Hacemos la pregunta definitiva que nos dará paso a la solución final, la pregunta es un método de asegurarse de que el usuario quiere recibir el listado del [País](https://resultados.elpais.com/deportivos/juegos-olimpicos/medallero/)

Bucle para obtener los datos, que tiene la funcionalidad de obtener todos los divs, donde están las entradas. El bucle se utiliza para recorrer los elementos de un objeto iterable (lista, tupla, conjunto, diccionario, …) y ejecutar un bloque de código.

Al ejecutar el bucle, hemos programado para que salgan los resultados de búsqueda y si la función es falsa, salga "Qué lástima, y...".

[scraping](https://github.com/nebrijas/periodismodedatos-mariofs17/blob/main/scraping.ipynb)


```
from bs4 import BeautifulSoup
import requests
#Datos sobre los Juegos Olímpicos en 2020

respuesta=input('¿QUIERES CONOCER LOS 20 PAÍSES QUE HAN OBTENIDO MÁS MEDALLAS EN 2020?\n \n Si tu respuesta es Sí, presiona "s" \n')
if(respuesta == 's'):
  print('\nRESULTADOS DE LOS DATOS DE LOS JUEGOS OLÍMPICOS 2020\n')
  print ('PAÍSES')
  URL = "https://resultados.elpais.com/deportivos/juegos-olimpicos/medallero/"
  # Realizamos la petición a la web
  req = requests.get(URL)
  # Si el estatus code no es 200 no se puede leer la página
  if (req.status_code != 200):
    raise Exception("No se puede hacer Web Scraping en"+ URL)
  # Pasamos el contenido HTML de la web a un objeto BeautifulSoup()
  html = BeautifulSoup(req.text, "html.parser")
  # Obtenemos todos los divs donde están las entradas
  paises = html.find_all("th",{"class":"pais"})
  oros = html.find_all("td",{"class":"m_oro"})
  platas = html.find_all("td",{"class":"m_plata"})
  bronces = html.find_all("td",{"class":"m_bronce"})
  totales = html.find_all("td",{"class":"m_total"})
  for i in range (20):
    # Con el método "getText()" no nos devuelve el HTML
    print("%d. %s \nOro: %s Plata: %s Bronce: %s \n Total: %s \n " % (i+1, paises[i+1].text.strip(),oros[i].text.strip(),platas[i].text.strip(),bronces[i].text.strip(), totales[i].text.strip()))

else:
  print('Qué lástima, y...')




```
