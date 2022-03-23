# Actividad dirigida 2

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

#Datos sobre los Juegos Olímpicos en 2016
respuesta=input('¿QUIERES CONOCER LOS 20 PAÍSES QUE HAN OBTENIDO MÁS MEDALLAS EN 2016? \n \n Si tu respuesta es Sí, presiona "s" \n')

if(respuesta == 's'):
  print('\nRESULTADOS DE LOS DATOS DE LOS JUEGOS OLÍMPICOS 2016\n')
  URL2 = "https://resultados.elpais.com/deportivos/juegos-olimpicos/medallero/"
  print ('PAÍSES')
  req2 = requests.get(URL2)
  if (req2.status_code != 200):
    raise Exception("No se puede hacer Web Scraping en"+ URL2)

  # Pasamos el contenido HTML de la web a un objeto BeautifulSoup()
  html2 = BeautifulSoup(req2.text, "html.parser")
  paises2 = html2.find_all("th",{"class":"pais"})
  oros2 = html2.find_all("td",{"class":"m_oro"})
  platas2 = html2.find_all("td",{"class":"m_plata"})
  bronces2 = html2.find_all("td",{"class":"m_bronce"})
  totales2 = html2.find_all("td",{"class":"m_total"})
  for i in range (20):
    print("%d. %s \nOro: %s Plata: %s Bronce: %s \n Total: %s \n " % (i+1, paises2[i+1].text.strip(),oros2[i].text.strip(),platas2[i].text.strip(),bronces2[i].text.strip(), totales2[i].text.strip()))

else:
  print('¡Vaya qué pena! Hasta la próxima')


````
