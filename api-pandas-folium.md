# API PANDAS FOLIUM

CROQUIS:

- API
- PANDAS
- FOLIUM, MAPAS

## INSTALAR LIBRERÍAS

La instalación de pandas sirve para escribir datos en CSV, Excel, HDF5 y para poder crear, seleccionar y filtrar las tablas de datos. En este caso nos centramos en el estudio de la web de Zaragoza, con el fin de poder obtener los datos acerca del desarrollo de la pandemia en diferentes países. Hacer uso de la orden !pip install pandas


```python
!pip install pandas folium
```

    Requirement already satisfied: pandas in c:\programdata\anaconda3\lib\site-packages (1.2.4)
    Requirement already satisfied: folium in c:\programdata\anaconda3\lib\site-packages (0.12.1.post1)
    Requirement already satisfied: branca>=0.3.0 in c:\programdata\anaconda3\lib\site-packages (from folium) (0.4.2)
    Requirement already satisfied: jinja2>=2.9 in c:\programdata\anaconda3\lib\site-packages (from folium) (2.11.3)
    Requirement already satisfied: requests in c:\programdata\anaconda3\lib\site-packages (from folium) (2.25.1)
    Requirement already satisfied: numpy in c:\programdata\anaconda3\lib\site-packages (from folium) (1.20.1)
    Requirement already satisfied: MarkupSafe>=0.23 in c:\programdata\anaconda3\lib\site-packages (from jinja2>=2.9->folium) (1.1.1)
    Requirement already satisfied: python-dateutil>=2.7.3 in c:\programdata\anaconda3\lib\site-packages (from pandas) (2.8.1)
    Requirement already satisfied: pytz>=2017.3 in c:\programdata\anaconda3\lib\site-packages (from pandas) (2021.1)
    Requirement already satisfied: six>=1.5 in c:\programdata\anaconda3\lib\site-packages (from python-dateutil>=2.7.3->pandas) (1.15.0)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\programdata\anaconda3\lib\site-packages (from requests->folium) (1.26.4)
    Requirement already satisfied: chardet<5,>=3.0.2 in c:\programdata\anaconda3\lib\site-packages (from requests->folium) (4.0.0)
    Requirement already satisfied: idna<3,>=2.5 in c:\programdata\anaconda3\lib\site-packages (from requests->folium) (2.10)
    Requirement already satisfied: certifi>=2017.4.17 in c:\programdata\anaconda3\lib\site-packages (from requests->folium) (2020.12.5)
    

## Configurar librerías

A continuación importamos las librerías import pandas as pd , que es un tipo de librería con la que recoger los datos para importar la biblioteca de análisis de Pandas a Python.


```python
import pandas as pd
import folium
```

## Variables
- url: https://www.zaragoza.es/sede/servicio/transporte/accidentalidad-trafico/accidente.csv?rows=100
- coords_zrgz
- mapa

Son básica para que el programa trabaje con unos datos y pueda crear los listados y tablas. En este caso hace referencia a los datos disponibles del COVID-19.


```python
url = 'https://www.zaragoza.es/sede/servicio/transporte/accidentalidad-trafico/accidente.csv?rows=20'
coords_zrgz = [41.649693,-0.887712]
mapa = folium.Map(location=coords_zrgz)
```

Determinamos las variables con sus datos y enlaces, para poder obtener los gráficos y listas al relacionarles.


```python
mapa= folium.Map(location=coords_zrgz)
mapa
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe src="about:blank" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" data-html=%3C%21DOCTYPE%20html%3E%0A%3Chead%3E%20%20%20%20%0A%20%20%20%20%3Cmeta%20http-equiv%3D%22content-type%22%20content%3D%22text/html%3B%20charset%3DUTF-8%22%20/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%3Cscript%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20L_NO_TOUCH%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20L_DISABLE_3D%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%3C/script%3E%0A%20%20%20%20%0A%20%20%20%20%3Cstyle%3Ehtml%2C%20body%20%7Bwidth%3A%20100%25%3Bheight%3A%20100%25%3Bmargin%3A%200%3Bpadding%3A%200%3B%7D%3C/style%3E%0A%20%20%20%20%3Cstyle%3E%23map%20%7Bposition%3Aabsolute%3Btop%3A0%3Bbottom%3A0%3Bright%3A0%3Bleft%3A0%3B%7D%3C/style%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//code.jquery.com/jquery-1.12.4.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js%22%3E%3C/script%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css%22/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cmeta%20name%3D%22viewport%22%20content%3D%22width%3Ddevice-width%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20initial-scale%3D1.0%2C%20maximum-scale%3D1.0%2C%20user-scalable%3Dno%22%20/%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cstyle%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%23map_bd0280be99a04da8b7fb49f143768e1f%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20position%3A%20relative%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20width%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20height%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20left%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20top%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%3C/style%3E%0A%20%20%20%20%20%20%20%20%0A%3C/head%3E%0A%3Cbody%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cdiv%20class%3D%22folium-map%22%20id%3D%22map_bd0280be99a04da8b7fb49f143768e1f%22%20%3E%3C/div%3E%0A%20%20%20%20%20%20%20%20%0A%3C/body%3E%0A%3Cscript%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20map_bd0280be99a04da8b7fb49f143768e1f%20%3D%20L.map%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22map_bd0280be99a04da8b7fb49f143768e1f%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20center%3A%20%5B41.649693%2C%20-0.887712%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20crs%3A%20L.CRS.EPSG3857%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoom%3A%2010%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoomControl%3A%20true%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20preferCanvas%3A%20false%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29%3B%0A%0A%20%20%20%20%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20tile_layer_253e1d287f1745c5a9ebb1fc2403be18%20%3D%20L.tileLayer%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22https%3A//%7Bs%7D.tile.openstreetmap.org/%7Bz%7D/%7Bx%7D/%7By%7D.png%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%22attribution%22%3A%20%22Data%20by%20%5Cu0026copy%3B%20%5Cu003ca%20href%3D%5C%22http%3A//openstreetmap.org%5C%22%5Cu003eOpenStreetMap%5Cu003c/a%5Cu003e%2C%20under%20%5Cu003ca%20href%3D%5C%22http%3A//www.openstreetmap.org/copyright%5C%22%5Cu003eODbL%5Cu003c/a%5Cu003e.%22%2C%20%22detectRetina%22%3A%20false%2C%20%22maxNativeZoom%22%3A%2018%2C%20%22maxZoom%22%3A%2018%2C%20%22minZoom%22%3A%200%2C%20%22noWrap%22%3A%20false%2C%20%22opacity%22%3A%201%2C%20%22subdomains%22%3A%20%22abc%22%2C%20%22tms%22%3A%20false%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%3C/script%3E onload="this.contentDocument.open();this.contentDocument.write(    decodeURIComponent(this.getAttribute('data-html')));this.contentDocument.close();" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>



Ordenamos que pinte el mapa de Zaragoza y que lo sitúe con los datos de la variable.


```python
df = pd.read_csv(url,delimiter=";")
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>year</th>
      <th>type</th>
      <th>accidentType</th>
      <th>firstAddress</th>
      <th>secondAddress</th>
      <th>geometry</th>
      <th>reason</th>
      <th>area</th>
      <th>creationDate</th>
      <th>daniosMateriales</th>
      <th>falloMecanico</th>
      <th>estadoPavimento</th>
      <th>tipoEstadoPavimento</th>
      <th>estadoAtmosfera</th>
      <th>tipoEstadoAtmosfera</th>
      <th>afectado</th>
      <th>vehiculo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>SALIDA CALZADA</td>
      <td>NaN</td>
      <td>COSTA, JOAQUIN</td>
      <td>PERAL, ISAAC</td>
      <td>-0.8818527060979306,41.649027473051156</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>NaN</td>
      <td>2014-10-09T00:00:00Z</td>
      <td>True</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>CADENA(MARQUES DE LA)</td>
      <td>NaN</td>
      <td>-0.8645810716721081,41.661585829868585</td>
      <td>DISTANCIA DE SEGURIDAD, no mantener</td>
      <td>2560.0</td>
      <td>2014-10-23T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>GOMEZ AVELLANEDA, G.</td>
      <td>CASTRO, R. (POETA)</td>
      <td>-0.887776415002892,41.666992622958105</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>2598.0</td>
      <td>2014-10-23T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>COLIS FRONTOLATERAL</td>
      <td>NaN</td>
      <td>MONZON</td>
      <td>GARCIA CONDOY, H.</td>
      <td>-0.8825260453930127,41.62957498750602</td>
      <td>CEDA EL PASO, no respetar prioridad de paso</td>
      <td>2555.0</td>
      <td>2014-10-23T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>SALIDA CALZADA</td>
      <td>NaN</td>
      <td>RIOJA</td>
      <td>NAVARRA, AVENIDA DE</td>
      <td>-0.908314757720389,41.6562121210704</td>
      <td>PERDIDA del control por VELOCIDAD INADECUADA</td>
      <td>2554.0</td>
      <td>2014-10-24T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>OTRAS</td>
      <td>NaN</td>
      <td>MUEL</td>
      <td>NaN</td>
      <td>-0.8691088511672924,41.65949772773082</td>
      <td>Caída de ocupante en Transporte Público</td>
      <td>2578.0</td>
      <td>2014-10-24T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>ATROPELLO</td>
      <td>NaN</td>
      <td>PIGNATELLI, RAMON VIA</td>
      <td>NaN</td>
      <td>-0.8880337913721866,41.633353667694024</td>
      <td>PEATÓN cruza calz SIN PREFER. fuera de paso</td>
      <td>2606.0</td>
      <td>2014-10-24T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>CAIDA SOBRE CALZADA</td>
      <td>NaN</td>
      <td>ALIERTA, AV. CESAREO</td>
      <td>AULA, LUIS</td>
      <td>-0.8708838775078237,41.6390382112928</td>
      <td>INVADIR otro carril en el mismo sentido de cir...</td>
      <td>2583.0</td>
      <td>2014-10-24T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2014</td>
      <td>COLIS. MARCHA ATRÁS</td>
      <td>NaN</td>
      <td>CERBUNA, PEDRO</td>
      <td>NaN</td>
      <td>-0.8970649943808023,41.64083344974765</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>2556.0</td>
      <td>2014-10-24T00:00:00Z</td>
      <td>True</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN LATERAL</td>
      <td>NaN</td>
      <td>ASALTO</td>
      <td>COCCI, JORGE</td>
      <td>-0.8718525605769747,41.64904657717317</td>
      <td>INVADIR otro carril en el mismo sentido de cir...</td>
      <td>4657.0</td>
      <td>2013-12-20T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>10</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>OTRAS</td>
      <td>NaN</td>
      <td>ARAGON (CORONA DE)</td>
      <td>SAN ANTONIO M CLARET</td>
      <td>-0.8964627561577849,41.64322365075108</td>
      <td>Caída de ocupante en Transporte Público</td>
      <td>63.0</td>
      <td>2013-12-21T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>11</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>FRAGUA, LA</td>
      <td>GASSIER, PIERRE</td>
      <td>-0.8778095796207178,41.68753087470739</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>4780.0</td>
      <td>2013-12-22T00:00:00Z</td>
      <td>True</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>12</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>SALIDA CALZADA</td>
      <td>NaN</td>
      <td>PIRINEOS, AV. DE LOS</td>
      <td>NaN</td>
      <td>-0.8812157329722801,41.661646612715046</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>4661.0</td>
      <td>2013-12-22T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>13</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>TORRES, CAMINO DE LAS</td>
      <td>NaN</td>
      <td>-0.8762000299022707,41.6454384961757</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>4667.0</td>
      <td>2013-12-22T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>14</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>ATROPELLO</td>
      <td>NaN</td>
      <td>RIOJA</td>
      <td>NAVARRA, AVENIDA DE</td>
      <td>-0.9089013552408617,41.65543768899759</td>
      <td>PEATÓN cruza calz SIN PREFER. en PASO CON semá...</td>
      <td>4664.0</td>
      <td>2013-12-22T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>15</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>ITALIA</td>
      <td>NaN</td>
      <td>-0.9004729973337304,41.65180346604993</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>4671.0</td>
      <td>2013-12-22T00:00:00Z</td>
      <td>True</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>16</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>AGUSTIN, PASEO MARIA</td>
      <td>MAYANDIA (GENERAL)</td>
      <td>-0.8917562993466011,41.65233828238132</td>
      <td>DISTANCIA DE SEGURIDAD, no mantener</td>
      <td>18.0</td>
      <td>2013-12-20T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>17</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>AGUSTIN, PASEO MARIA</td>
      <td>SANTA ANA</td>
      <td>-0.888856043735591,41.65040494617356</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>4718.0</td>
      <td>2013-12-23T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>18</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>CASPE, AV.COMPROMISO</td>
      <td>NaN</td>
      <td>-0.8629911318784169,41.645335650478316</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>4723.0</td>
      <td>2013-12-23T00:00:00Z</td>
      <td>False</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
    <tr>
      <th>19</th>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
      <td>2013</td>
      <td>COLISIÓN ALCANCE</td>
      <td>NaN</td>
      <td>MURANO, ISLA DE AV.</td>
      <td>NaN</td>
      <td>-0.8870207060655807,41.609992514227066</td>
      <td>PERDIDA del control por FALTA de ATENCIÓN</td>
      <td>NaN</td>
      <td>2013-12-23T00:00:00Z</td>
      <td>True</td>
      <td>False</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>BUEN ESTADO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>https://www.zaragoza.es/sede/servicio/transpor...</td>
    </tr>
  </tbody>
</table>
</div>



Ordenamos que lea y clasifique la tabla en función de los valores, como las coordenadas, los nombres o los tipos de calzada.


```python
df.columns
```




    Index(['id', 'year', 'type', 'accidentType', 'firstAddress', 'secondAddress',
           'geometry', 'reason', 'area', 'creationDate', 'daniosMateriales',
           'falloMecanico', 'estadoPavimento', 'tipoEstadoPavimento',
           'estadoAtmosfera', 'tipoEstadoAtmosfera', 'afectado', 'vehiculo'],
          dtype='object')



Obtenemos toda la infomación que hay en las columnas, para saber el número de variables.


```python
df['geometry']
```




    0     -0.8818527060979306,41.649027473051156
    1     -0.8645810716721081,41.661585829868585
    2      -0.887776415002892,41.666992622958105
    3      -0.8825260453930127,41.62957498750602
    4        -0.908314757720389,41.6562121210704
    5      -0.8691088511672924,41.65949772773082
    6     -0.8880337913721866,41.633353667694024
    7       -0.8708838775078237,41.6390382112928
    8      -0.8970649943808023,41.64083344974765
    9      -0.8718525605769747,41.64904657717317
    10     -0.8964627561577849,41.64322365075108
    11     -0.8778095796207178,41.68753087470739
    12    -0.8812157329722801,41.661646612715046
    13      -0.8762000299022707,41.6454384961757
    14     -0.9089013552408617,41.65543768899759
    15     -0.9004729973337304,41.65180346604993
    16     -0.8917562993466011,41.65233828238132
    17      -0.888856043735591,41.65040494617356
    18    -0.8629911318784169,41.645335650478316
    19    -0.8870207060655807,41.609992514227066
    Name: geometry, dtype: object



Sirve para conocer los datos de la tabla y donde sale la información en formato texto con un sentido. Además puede haber números que representen al texto


```python
df.info

```




    <bound method DataFrame.info of                                                    id  year  \
    0   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    1   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    2   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    3   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    4   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    5   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    6   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    7   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    8   https://www.zaragoza.es/sede/servicio/transpor...  2014   
    9   https://www.zaragoza.es/sede/servicio/transpor...  2013   
    10  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    11  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    12  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    13  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    14  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    15  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    16  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    17  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    18  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    19  https://www.zaragoza.es/sede/servicio/transpor...  2013   
    
                       type  accidentType           firstAddress  \
    0        SALIDA CALZADA           NaN         COSTA, JOAQUIN   
    1      COLISIÓN ALCANCE           NaN  CADENA(MARQUES DE LA)   
    2      COLISIÓN ALCANCE           NaN   GOMEZ AVELLANEDA, G.   
    3   COLIS FRONTOLATERAL           NaN                 MONZON   
    4        SALIDA CALZADA           NaN                  RIOJA   
    5                 OTRAS           NaN                   MUEL   
    6             ATROPELLO           NaN  PIGNATELLI, RAMON VIA   
    7   CAIDA SOBRE CALZADA           NaN   ALIERTA, AV. CESAREO   
    8   COLIS. MARCHA ATRÁS           NaN         CERBUNA, PEDRO   
    9      COLISIÓN LATERAL           NaN                 ASALTO   
    10                OTRAS           NaN     ARAGON (CORONA DE)   
    11     COLISIÓN ALCANCE           NaN             FRAGUA, LA   
    12       SALIDA CALZADA           NaN   PIRINEOS, AV. DE LOS   
    13     COLISIÓN ALCANCE           NaN  TORRES, CAMINO DE LAS   
    14            ATROPELLO           NaN                  RIOJA   
    15     COLISIÓN ALCANCE           NaN                 ITALIA   
    16     COLISIÓN ALCANCE           NaN   AGUSTIN, PASEO MARIA   
    17     COLISIÓN ALCANCE           NaN   AGUSTIN, PASEO MARIA   
    18     COLISIÓN ALCANCE           NaN   CASPE, AV.COMPROMISO   
    19     COLISIÓN ALCANCE           NaN    MURANO, ISLA DE AV.   
    
               secondAddress                                geometry  \
    0           PERAL, ISAAC  -0.8818527060979306,41.649027473051156   
    1                    NaN  -0.8645810716721081,41.661585829868585   
    2     CASTRO, R. (POETA)   -0.887776415002892,41.666992622958105   
    3      GARCIA CONDOY, H.   -0.8825260453930127,41.62957498750602   
    4    NAVARRA, AVENIDA DE     -0.908314757720389,41.6562121210704   
    5                    NaN   -0.8691088511672924,41.65949772773082   
    6                    NaN  -0.8880337913721866,41.633353667694024   
    7             AULA, LUIS    -0.8708838775078237,41.6390382112928   
    8                    NaN   -0.8970649943808023,41.64083344974765   
    9           COCCI, JORGE   -0.8718525605769747,41.64904657717317   
    10  SAN ANTONIO M CLARET   -0.8964627561577849,41.64322365075108   
    11       GASSIER, PIERRE   -0.8778095796207178,41.68753087470739   
    12                   NaN  -0.8812157329722801,41.661646612715046   
    13                   NaN    -0.8762000299022707,41.6454384961757   
    14   NAVARRA, AVENIDA DE   -0.9089013552408617,41.65543768899759   
    15                   NaN   -0.9004729973337304,41.65180346604993   
    16    MAYANDIA (GENERAL)   -0.8917562993466011,41.65233828238132   
    17             SANTA ANA    -0.888856043735591,41.65040494617356   
    18                   NaN  -0.8629911318784169,41.645335650478316   
    19                   NaN  -0.8870207060655807,41.609992514227066   
    
                                                   reason    area  \
    0           PERDIDA del control por FALTA de ATENCIÓN     NaN   
    1                 DISTANCIA DE SEGURIDAD, no mantener  2560.0   
    2           PERDIDA del control por FALTA de ATENCIÓN  2598.0   
    3         CEDA EL PASO, no respetar prioridad de paso  2555.0   
    4        PERDIDA del control por VELOCIDAD INADECUADA  2554.0   
    5             Caída de ocupante en Transporte Público  2578.0   
    6         PEATÓN cruza calz SIN PREFER. fuera de paso  2606.0   
    7   INVADIR otro carril en el mismo sentido de cir...  2583.0   
    8           PERDIDA del control por FALTA de ATENCIÓN  2556.0   
    9   INVADIR otro carril en el mismo sentido de cir...  4657.0   
    10            Caída de ocupante en Transporte Público    63.0   
    11          PERDIDA del control por FALTA de ATENCIÓN  4780.0   
    12          PERDIDA del control por FALTA de ATENCIÓN  4661.0   
    13          PERDIDA del control por FALTA de ATENCIÓN  4667.0   
    14  PEATÓN cruza calz SIN PREFER. en PASO CON semá...  4664.0   
    15          PERDIDA del control por FALTA de ATENCIÓN  4671.0   
    16                DISTANCIA DE SEGURIDAD, no mantener    18.0   
    17          PERDIDA del control por FALTA de ATENCIÓN  4718.0   
    18          PERDIDA del control por FALTA de ATENCIÓN  4723.0   
    19          PERDIDA del control por FALTA de ATENCIÓN     NaN   
    
                creationDate  daniosMateriales  falloMecanico estadoPavimento  \
    0   2014-10-09T00:00:00Z              True          False     BUEN ESTADO   
    1   2014-10-23T00:00:00Z             False          False     BUEN ESTADO   
    2   2014-10-23T00:00:00Z             False          False     BUEN ESTADO   
    3   2014-10-23T00:00:00Z             False          False     BUEN ESTADO   
    4   2014-10-24T00:00:00Z             False          False     BUEN ESTADO   
    5   2014-10-24T00:00:00Z             False          False     BUEN ESTADO   
    6   2014-10-24T00:00:00Z             False          False     BUEN ESTADO   
    7   2014-10-24T00:00:00Z             False          False     BUEN ESTADO   
    8   2014-10-24T00:00:00Z              True          False     BUEN ESTADO   
    9   2013-12-20T00:00:00Z             False          False     BUEN ESTADO   
    10  2013-12-21T00:00:00Z             False          False     BUEN ESTADO   
    11  2013-12-22T00:00:00Z              True          False     BUEN ESTADO   
    12  2013-12-22T00:00:00Z             False          False     BUEN ESTADO   
    13  2013-12-22T00:00:00Z             False          False     BUEN ESTADO   
    14  2013-12-22T00:00:00Z             False          False     BUEN ESTADO   
    15  2013-12-22T00:00:00Z              True          False     BUEN ESTADO   
    16  2013-12-20T00:00:00Z             False          False     BUEN ESTADO   
    17  2013-12-23T00:00:00Z             False          False     BUEN ESTADO   
    18  2013-12-23T00:00:00Z             False          False     BUEN ESTADO   
    19  2013-12-23T00:00:00Z              True          False     BUEN ESTADO   
    
        tipoEstadoPavimento estadoAtmosfera  tipoEstadoAtmosfera  \
    0                   NaN     BUEN ESTADO                  NaN   
    1                   NaN     BUEN ESTADO                  NaN   
    2                   NaN     BUEN ESTADO                  NaN   
    3                   NaN     BUEN ESTADO                  NaN   
    4                   NaN     BUEN ESTADO                  NaN   
    5                   NaN     BUEN ESTADO                  NaN   
    6                   NaN     BUEN ESTADO                  NaN   
    7                   NaN     BUEN ESTADO                  NaN   
    8                   NaN     BUEN ESTADO                  NaN   
    9                   NaN     BUEN ESTADO                  NaN   
    10                  NaN     BUEN ESTADO                  NaN   
    11                  NaN     BUEN ESTADO                  NaN   
    12                  NaN     BUEN ESTADO                  NaN   
    13                  NaN     BUEN ESTADO                  NaN   
    14                  NaN     BUEN ESTADO                  NaN   
    15                  NaN     BUEN ESTADO                  NaN   
    16                  NaN     BUEN ESTADO                  NaN   
    17                  NaN     BUEN ESTADO                  NaN   
    18                  NaN     BUEN ESTADO                  NaN   
    19                  NaN     BUEN ESTADO                  NaN   
    
                                                 afectado  \
    0                                                 NaN   
    1   https://www.zaragoza.es/sede/servicio/transpor...   
    2   https://www.zaragoza.es/sede/servicio/transpor...   
    3   https://www.zaragoza.es/sede/servicio/transpor...   
    4   https://www.zaragoza.es/sede/servicio/transpor...   
    5   https://www.zaragoza.es/sede/servicio/transpor...   
    6   https://www.zaragoza.es/sede/servicio/transpor...   
    7   https://www.zaragoza.es/sede/servicio/transpor...   
    8                                                 NaN   
    9   https://www.zaragoza.es/sede/servicio/transpor...   
    10  https://www.zaragoza.es/sede/servicio/transpor...   
    11                                                NaN   
    12  https://www.zaragoza.es/sede/servicio/transpor...   
    13  https://www.zaragoza.es/sede/servicio/transpor...   
    14  https://www.zaragoza.es/sede/servicio/transpor...   
    15                                                NaN   
    16  https://www.zaragoza.es/sede/servicio/transpor...   
    17  https://www.zaragoza.es/sede/servicio/transpor...   
    18  https://www.zaragoza.es/sede/servicio/transpor...   
    19                                                NaN   
    
                                                 vehiculo  
    0   https://www.zaragoza.es/sede/servicio/transpor...  
    1   https://www.zaragoza.es/sede/servicio/transpor...  
    2   https://www.zaragoza.es/sede/servicio/transpor...  
    3   https://www.zaragoza.es/sede/servicio/transpor...  
    4   https://www.zaragoza.es/sede/servicio/transpor...  
    5   https://www.zaragoza.es/sede/servicio/transpor...  
    6   https://www.zaragoza.es/sede/servicio/transpor...  
    7   https://www.zaragoza.es/sede/servicio/transpor...  
    8   https://www.zaragoza.es/sede/servicio/transpor...  
    9   https://www.zaragoza.es/sede/servicio/transpor...  
    10  https://www.zaragoza.es/sede/servicio/transpor...  
    11  https://www.zaragoza.es/sede/servicio/transpor...  
    12  https://www.zaragoza.es/sede/servicio/transpor...  
    13  https://www.zaragoza.es/sede/servicio/transpor...  
    14  https://www.zaragoza.es/sede/servicio/transpor...  
    15  https://www.zaragoza.es/sede/servicio/transpor...  
    16  https://www.zaragoza.es/sede/servicio/transpor...  
    17  https://www.zaragoza.es/sede/servicio/transpor...  
    18  https://www.zaragoza.es/sede/servicio/transpor...  
    19  https://www.zaragoza.es/sede/servicio/transpor...  >



Desglosar la información de la página web (recopilación en bruto)


```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>accidentType</th>
      <th>area</th>
      <th>tipoEstadoPavimento</th>
      <th>tipoEstadoAtmosfera</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>20.000000</td>
      <td>0.0</td>
      <td>18.000000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2013.450000</td>
      <td>NaN</td>
      <td>3234.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.510418</td>
      <td>NaN</td>
      <td>1551.515843</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2013.000000</td>
      <td>NaN</td>
      <td>18.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2013.000000</td>
      <td>NaN</td>
      <td>2557.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2013.000000</td>
      <td>NaN</td>
      <td>2602.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2014.000000</td>
      <td>NaN</td>
      <td>4666.250000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2014.000000</td>
      <td>NaN</td>
      <td>4780.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>





Información númerica que en este caso no nos aporta nada.


```python
df["type"].unique()
```




    array(['SALIDA CALZADA', 'COLISIÓN ALCANCE', 'COLIS FRONTOLATERAL',
           'OTRAS', 'ATROPELLO', 'CAIDA SOBRE CALZADA', 'COLIS. MARCHA ATRÁS',
           'COLISIÓN LATERAL'], dtype=object)



Es una descripción de los valores únicos de la columna type


```python
df['geometry']
```




    0     -0.8818527060979306,41.649027473051156
    1     -0.8645810716721081,41.661585829868585
    2      -0.887776415002892,41.666992622958105
    3      -0.8825260453930127,41.62957498750602
    4        -0.908314757720389,41.6562121210704
    5      -0.8691088511672924,41.65949772773082
    6     -0.8880337913721866,41.633353667694024
    7       -0.8708838775078237,41.6390382112928
    8      -0.8970649943808023,41.64083344974765
    9      -0.8718525605769747,41.64904657717317
    10     -0.8964627561577849,41.64322365075108
    11     -0.8778095796207178,41.68753087470739
    12    -0.8812157329722801,41.661646612715046
    13      -0.8762000299022707,41.6454384961757
    14     -0.9089013552408617,41.65543768899759
    15     -0.9004729973337304,41.65180346604993
    16     -0.8917562993466011,41.65233828238132
    17      -0.888856043735591,41.65040494617356
    18    -0.8629911318784169,41.645335650478316
    19    -0.8870207060655807,41.609992514227066
    Name: geometry, dtype: object



Obtener las coordenadas para poder situarlas en el mapa, el plan es poder pintar encima del mapa (accidentes, tipos de vehículo).


```python
type(df["geometry"][0])
```




    str



Te indica que es una cadena de valores y no puedes utilizarla en el mapa. Hemos preguntado sobre que tipo de datos es.




```python
df["geometry"][0].split(",")
```




    ['-0.8818527060979306', '41.649027473051156']



Hemos analizado que el separador es la ",", por lo que nos interesa para separar la información en latitud y longitud.
Ya tenemos una lista que podemos manipular.


```python
point = df["geometry"][0].split(",")
point
```




    ['-0.8818527060979306', '41.649027473051156']



Crear un punto con los dos valores anteriores, significa nombrar los valores para poder referirte a ellos (les estamos creando) 


```python
type(point)
```




    list



Es una comprobación de que "point" ya es una lista de dos elementos

Ahora tenemos que obtener dos columnas, para guardar los elementos de las filas


```python
longitudes = []
latitudes = []
```

Ahora mismo son dos listas sin datos para rellenarlas con bucles


```python
for i in df['geometry']:
    punto_coord = i.split(',')
    longitudes += [float(punto_coord[1])]
longitudes
    
```




    [41.649027473051156,
     41.661585829868585,
     41.666992622958105,
     41.62957498750602,
     41.6562121210704,
     41.65949772773082,
     41.633353667694024,
     41.6390382112928,
     41.64083344974765,
     41.64904657717317,
     41.64322365075108,
     41.68753087470739,
     41.661646612715046,
     41.6454384961757,
     41.65543768899759,
     41.65180346604993,
     41.65233828238132,
     41.65040494617356,
     41.645335650478316,
     41.609992514227066]



Comienza el bucle con las filas del "geometry" (i) y para ello creas un objeto que separe las celdas de "geometry".
En longitudes añadimos otro elemento de la columna. 


```python
for i in df['geometry']:
    punto_coord = i.split(',')
    latitudes += [float(punto_coord[0])]
latitudes
```




    [-0.8818527060979306,
     -0.8645810716721081,
     -0.887776415002892,
     -0.8825260453930127,
     -0.908314757720389,
     -0.8691088511672924,
     -0.8880337913721866,
     -0.8708838775078237,
     -0.8970649943808023,
     -0.8718525605769747,
     -0.8964627561577849,
     -0.8778095796207178,
     -0.8812157329722801,
     -0.8762000299022707,
     -0.9089013552408617,
     -0.9004729973337304,
     -0.8917562993466011,
     -0.888856043735591,
     -0.8629911318784169,
     -0.8870207060655807]



Hacemos lo mismo con latitudes pero tenemos que cambiar el  "1" por el "0", que es el primer número de python. *El float se utiliza para dar un formato decimal a los números*


```python
df_coord = pd.DataFrame({'long':longitudes,'lat':latitudes})
df_coord
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>long</th>
      <th>lat</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>41.649027</td>
      <td>-0.881853</td>
    </tr>
    <tr>
      <th>1</th>
      <td>41.661586</td>
      <td>-0.864581</td>
    </tr>
    <tr>
      <th>2</th>
      <td>41.666993</td>
      <td>-0.887776</td>
    </tr>
    <tr>
      <th>3</th>
      <td>41.629575</td>
      <td>-0.882526</td>
    </tr>
    <tr>
      <th>4</th>
      <td>41.656212</td>
      <td>-0.908315</td>
    </tr>
    <tr>
      <th>5</th>
      <td>41.659498</td>
      <td>-0.869109</td>
    </tr>
    <tr>
      <th>6</th>
      <td>41.633354</td>
      <td>-0.888034</td>
    </tr>
    <tr>
      <th>7</th>
      <td>41.639038</td>
      <td>-0.870884</td>
    </tr>
    <tr>
      <th>8</th>
      <td>41.640833</td>
      <td>-0.897065</td>
    </tr>
    <tr>
      <th>9</th>
      <td>41.649047</td>
      <td>-0.871853</td>
    </tr>
    <tr>
      <th>10</th>
      <td>41.643224</td>
      <td>-0.896463</td>
    </tr>
    <tr>
      <th>11</th>
      <td>41.687531</td>
      <td>-0.877810</td>
    </tr>
    <tr>
      <th>12</th>
      <td>41.661647</td>
      <td>-0.881216</td>
    </tr>
    <tr>
      <th>13</th>
      <td>41.645438</td>
      <td>-0.876200</td>
    </tr>
    <tr>
      <th>14</th>
      <td>41.655438</td>
      <td>-0.908901</td>
    </tr>
    <tr>
      <th>15</th>
      <td>41.651803</td>
      <td>-0.900473</td>
    </tr>
    <tr>
      <th>16</th>
      <td>41.652338</td>
      <td>-0.891756</td>
    </tr>
    <tr>
      <th>17</th>
      <td>41.650405</td>
      <td>-0.888856</td>
    </tr>
    <tr>
      <th>18</th>
      <td>41.645336</td>
      <td>-0.862991</td>
    </tr>
    <tr>
      <th>19</th>
      <td>41.609993</td>
      <td>-0.887021</td>
    </tr>
  </tbody>
</table>
</div>



Hacemos un dataframe de las dos columnas para colocarlas, aprovechando que ya están ordenadas por el "0" y el "1"


```python
df_accidentes = pd.concat([df['type'],df_coord],axis=1)
df_accidentes
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>type</th>
      <th>long</th>
      <th>lat</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>SALIDA CALZADA</td>
      <td>41.649027</td>
      <td>-0.881853</td>
    </tr>
    <tr>
      <th>1</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.661586</td>
      <td>-0.864581</td>
    </tr>
    <tr>
      <th>2</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.666993</td>
      <td>-0.887776</td>
    </tr>
    <tr>
      <th>3</th>
      <td>COLIS FRONTOLATERAL</td>
      <td>41.629575</td>
      <td>-0.882526</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SALIDA CALZADA</td>
      <td>41.656212</td>
      <td>-0.908315</td>
    </tr>
    <tr>
      <th>5</th>
      <td>OTRAS</td>
      <td>41.659498</td>
      <td>-0.869109</td>
    </tr>
    <tr>
      <th>6</th>
      <td>ATROPELLO</td>
      <td>41.633354</td>
      <td>-0.888034</td>
    </tr>
    <tr>
      <th>7</th>
      <td>CAIDA SOBRE CALZADA</td>
      <td>41.639038</td>
      <td>-0.870884</td>
    </tr>
    <tr>
      <th>8</th>
      <td>COLIS. MARCHA ATRÁS</td>
      <td>41.640833</td>
      <td>-0.897065</td>
    </tr>
    <tr>
      <th>9</th>
      <td>COLISIÓN LATERAL</td>
      <td>41.649047</td>
      <td>-0.871853</td>
    </tr>
    <tr>
      <th>10</th>
      <td>OTRAS</td>
      <td>41.643224</td>
      <td>-0.896463</td>
    </tr>
    <tr>
      <th>11</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.687531</td>
      <td>-0.877810</td>
    </tr>
    <tr>
      <th>12</th>
      <td>SALIDA CALZADA</td>
      <td>41.661647</td>
      <td>-0.881216</td>
    </tr>
    <tr>
      <th>13</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.645438</td>
      <td>-0.876200</td>
    </tr>
    <tr>
      <th>14</th>
      <td>ATROPELLO</td>
      <td>41.655438</td>
      <td>-0.908901</td>
    </tr>
    <tr>
      <th>15</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.651803</td>
      <td>-0.900473</td>
    </tr>
    <tr>
      <th>16</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.652338</td>
      <td>-0.891756</td>
    </tr>
    <tr>
      <th>17</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.650405</td>
      <td>-0.888856</td>
    </tr>
    <tr>
      <th>18</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.645336</td>
      <td>-0.862991</td>
    </tr>
    <tr>
      <th>19</th>
      <td>COLISIÓN ALCANCE</td>
      <td>41.609993</td>
      <td>-0.887021</td>
    </tr>
  </tbody>
</table>
</div>



Concatenar el data frame original con el de coordenadas
Axis = 1 significa que se va a añadir en formato horizontal


```python
marcador = folium.Marker(coords_zrgz, popup="¡Hola Zaragoza!")
mapa = mapa.add_child(marcador)
mapa
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe src="about:blank" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" data-html=%3C%21DOCTYPE%20html%3E%0A%3Chead%3E%20%20%20%20%0A%20%20%20%20%3Cmeta%20http-equiv%3D%22content-type%22%20content%3D%22text/html%3B%20charset%3DUTF-8%22%20/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%3Cscript%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20L_NO_TOUCH%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20L_DISABLE_3D%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%3C/script%3E%0A%20%20%20%20%0A%20%20%20%20%3Cstyle%3Ehtml%2C%20body%20%7Bwidth%3A%20100%25%3Bheight%3A%20100%25%3Bmargin%3A%200%3Bpadding%3A%200%3B%7D%3C/style%3E%0A%20%20%20%20%3Cstyle%3E%23map%20%7Bposition%3Aabsolute%3Btop%3A0%3Bbottom%3A0%3Bright%3A0%3Bleft%3A0%3B%7D%3C/style%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//code.jquery.com/jquery-1.12.4.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js%22%3E%3C/script%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css%22/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cmeta%20name%3D%22viewport%22%20content%3D%22width%3Ddevice-width%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20initial-scale%3D1.0%2C%20maximum-scale%3D1.0%2C%20user-scalable%3Dno%22%20/%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cstyle%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%23map_bd0280be99a04da8b7fb49f143768e1f%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20position%3A%20relative%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20width%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20height%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20left%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20top%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%3C/style%3E%0A%20%20%20%20%20%20%20%20%0A%3C/head%3E%0A%3Cbody%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cdiv%20class%3D%22folium-map%22%20id%3D%22map_bd0280be99a04da8b7fb49f143768e1f%22%20%3E%3C/div%3E%0A%20%20%20%20%20%20%20%20%0A%3C/body%3E%0A%3Cscript%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20map_bd0280be99a04da8b7fb49f143768e1f%20%3D%20L.map%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22map_bd0280be99a04da8b7fb49f143768e1f%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20center%3A%20%5B41.649693%2C%20-0.887712%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20crs%3A%20L.CRS.EPSG3857%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoom%3A%2010%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoomControl%3A%20true%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20preferCanvas%3A%20false%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29%3B%0A%0A%20%20%20%20%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20tile_layer_253e1d287f1745c5a9ebb1fc2403be18%20%3D%20L.tileLayer%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22https%3A//%7Bs%7D.tile.openstreetmap.org/%7Bz%7D/%7Bx%7D/%7By%7D.png%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%22attribution%22%3A%20%22Data%20by%20%5Cu0026copy%3B%20%5Cu003ca%20href%3D%5C%22http%3A//openstreetmap.org%5C%22%5Cu003eOpenStreetMap%5Cu003c/a%5Cu003e%2C%20under%20%5Cu003ca%20href%3D%5C%22http%3A//www.openstreetmap.org/copyright%5C%22%5Cu003eODbL%5Cu003c/a%5Cu003e.%22%2C%20%22detectRetina%22%3A%20false%2C%20%22maxNativeZoom%22%3A%2018%2C%20%22maxZoom%22%3A%2018%2C%20%22minZoom%22%3A%200%2C%20%22noWrap%22%3A%20false%2C%20%22opacity%22%3A%201%2C%20%22subdomains%22%3A%20%22abc%22%2C%20%22tms%22%3A%20false%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_51e66bc97a6948d5a3d8a26c1f054a77%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B41.649693%2C%20-0.887712%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_83116e178be149c19c7d545628e45a47%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_29aea08186064a3480184de213e50e7d%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_29aea08186064a3480184de213e50e7d%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3E%C2%A1Hola%20Zaragoza%21%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_83116e178be149c19c7d545628e45a47.setContent%28html_29aea08186064a3480184de213e50e7d%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_51e66bc97a6948d5a3d8a26c1f054a77.bindPopup%28popup_83116e178be149c19c7d545628e45a47%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%3C/script%3E onload="this.contentDocument.open();this.contentDocument.write(    decodeURIComponent(this.getAttribute('data-html')));this.contentDocument.close();" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>



Marcar unas coordenadas en el mapa original de Zaragoza


```python
for indice, fila in df_accidentes.iterrows():
    marcador = folium.Marker([fila['lat'],fila['long']],\
                            popup=fila['type'])
    mapa.add_child(marcador)
mapa
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe src="about:blank" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" data-html=%3C%21DOCTYPE%20html%3E%0A%3Chead%3E%20%20%20%20%0A%20%20%20%20%3Cmeta%20http-equiv%3D%22content-type%22%20content%3D%22text/html%3B%20charset%3DUTF-8%22%20/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%3Cscript%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20L_NO_TOUCH%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20L_DISABLE_3D%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%3C/script%3E%0A%20%20%20%20%0A%20%20%20%20%3Cstyle%3Ehtml%2C%20body%20%7Bwidth%3A%20100%25%3Bheight%3A%20100%25%3Bmargin%3A%200%3Bpadding%3A%200%3B%7D%3C/style%3E%0A%20%20%20%20%3Cstyle%3E%23map%20%7Bposition%3Aabsolute%3Btop%3A0%3Bbottom%3A0%3Bright%3A0%3Bleft%3A0%3B%7D%3C/style%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//code.jquery.com/jquery-1.12.4.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js%22%3E%3C/script%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css%22/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cmeta%20name%3D%22viewport%22%20content%3D%22width%3Ddevice-width%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20initial-scale%3D1.0%2C%20maximum-scale%3D1.0%2C%20user-scalable%3Dno%22%20/%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cstyle%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%23map_bd0280be99a04da8b7fb49f143768e1f%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20position%3A%20relative%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20width%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20height%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20left%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20top%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%3C/style%3E%0A%20%20%20%20%20%20%20%20%0A%3C/head%3E%0A%3Cbody%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cdiv%20class%3D%22folium-map%22%20id%3D%22map_bd0280be99a04da8b7fb49f143768e1f%22%20%3E%3C/div%3E%0A%20%20%20%20%20%20%20%20%0A%3C/body%3E%0A%3Cscript%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20map_bd0280be99a04da8b7fb49f143768e1f%20%3D%20L.map%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22map_bd0280be99a04da8b7fb49f143768e1f%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20center%3A%20%5B41.649693%2C%20-0.887712%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20crs%3A%20L.CRS.EPSG3857%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoom%3A%2010%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoomControl%3A%20true%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20preferCanvas%3A%20false%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29%3B%0A%0A%20%20%20%20%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20tile_layer_253e1d287f1745c5a9ebb1fc2403be18%20%3D%20L.tileLayer%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22https%3A//%7Bs%7D.tile.openstreetmap.org/%7Bz%7D/%7Bx%7D/%7By%7D.png%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%22attribution%22%3A%20%22Data%20by%20%5Cu0026copy%3B%20%5Cu003ca%20href%3D%5C%22http%3A//openstreetmap.org%5C%22%5Cu003eOpenStreetMap%5Cu003c/a%5Cu003e%2C%20under%20%5Cu003ca%20href%3D%5C%22http%3A//www.openstreetmap.org/copyright%5C%22%5Cu003eODbL%5Cu003c/a%5Cu003e.%22%2C%20%22detectRetina%22%3A%20false%2C%20%22maxNativeZoom%22%3A%2018%2C%20%22maxZoom%22%3A%2018%2C%20%22minZoom%22%3A%200%2C%20%22noWrap%22%3A%20false%2C%20%22opacity%22%3A%201%2C%20%22subdomains%22%3A%20%22abc%22%2C%20%22tms%22%3A%20false%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_51e66bc97a6948d5a3d8a26c1f054a77%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B41.649693%2C%20-0.887712%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_83116e178be149c19c7d545628e45a47%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_29aea08186064a3480184de213e50e7d%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_29aea08186064a3480184de213e50e7d%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3E%C2%A1Hola%20Zaragoza%21%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_83116e178be149c19c7d545628e45a47.setContent%28html_29aea08186064a3480184de213e50e7d%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_51e66bc97a6948d5a3d8a26c1f054a77.bindPopup%28popup_83116e178be149c19c7d545628e45a47%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_a92ebc1abac548c687b120e487830391%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8818527060979306%2C%2041.649027473051156%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_c4777dc1e0664ce9a9c2d6d57e06984b%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_4638140a8d9c4d29be3da5bab6c6d41b%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_4638140a8d9c4d29be3da5bab6c6d41b%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ESALIDA%20CALZADA%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_c4777dc1e0664ce9a9c2d6d57e06984b.setContent%28html_4638140a8d9c4d29be3da5bab6c6d41b%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_a92ebc1abac548c687b120e487830391.bindPopup%28popup_c4777dc1e0664ce9a9c2d6d57e06984b%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_5c1757227fd84748b1dc15ceaec077b5%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8645810716721081%2C%2041.661585829868585%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_f38b651d26574457be7e19be75389723%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_60a88d70439e45bdae398fc049c33df7%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_60a88d70439e45bdae398fc049c33df7%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_f38b651d26574457be7e19be75389723.setContent%28html_60a88d70439e45bdae398fc049c33df7%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_5c1757227fd84748b1dc15ceaec077b5.bindPopup%28popup_f38b651d26574457be7e19be75389723%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_7a6c79b8e8e348858d8df887b8c03d68%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.887776415002892%2C%2041.666992622958105%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_81256f0da37f457ea7961febf33a0480%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_a781fffd706346f1a78e0c2efd67cd7e%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_a781fffd706346f1a78e0c2efd67cd7e%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_81256f0da37f457ea7961febf33a0480.setContent%28html_a781fffd706346f1a78e0c2efd67cd7e%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_7a6c79b8e8e348858d8df887b8c03d68.bindPopup%28popup_81256f0da37f457ea7961febf33a0480%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_88a13a83b6814fa89a40e24e886d885c%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8825260453930127%2C%2041.62957498750602%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_d418531d158d476599833e1239c7d2c4%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_06ff8418ac014d52ac5be4717389b91f%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_06ff8418ac014d52ac5be4717389b91f%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLIS%20FRONTOLATERAL%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_d418531d158d476599833e1239c7d2c4.setContent%28html_06ff8418ac014d52ac5be4717389b91f%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_88a13a83b6814fa89a40e24e886d885c.bindPopup%28popup_d418531d158d476599833e1239c7d2c4%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_28d0b6a9e0c9429e918a44f034619df9%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.908314757720389%2C%2041.6562121210704%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_0162c94767644a9685411acc485f8f1f%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_15b81072dd5c4ad5aa7c4acae7b1c03b%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_15b81072dd5c4ad5aa7c4acae7b1c03b%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ESALIDA%20CALZADA%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_0162c94767644a9685411acc485f8f1f.setContent%28html_15b81072dd5c4ad5aa7c4acae7b1c03b%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_28d0b6a9e0c9429e918a44f034619df9.bindPopup%28popup_0162c94767644a9685411acc485f8f1f%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_e80e2cf9685c449b99a05e62121945e8%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8691088511672924%2C%2041.65949772773082%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_67038c1dfb9f4637b712b1c0c9239d85%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_dfd28ebf12ff4f36905096151286fbbd%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_dfd28ebf12ff4f36905096151286fbbd%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3EOTRAS%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_67038c1dfb9f4637b712b1c0c9239d85.setContent%28html_dfd28ebf12ff4f36905096151286fbbd%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_e80e2cf9685c449b99a05e62121945e8.bindPopup%28popup_67038c1dfb9f4637b712b1c0c9239d85%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_db07e2433e394959b1be2c79df92d8b0%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8880337913721866%2C%2041.633353667694024%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_3a114402883b481eb443e1b0ce2ebdba%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_d52ca52895ee49c7a6f531243f8d3ea6%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_d52ca52895ee49c7a6f531243f8d3ea6%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3EATROPELLO%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_3a114402883b481eb443e1b0ce2ebdba.setContent%28html_d52ca52895ee49c7a6f531243f8d3ea6%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_db07e2433e394959b1be2c79df92d8b0.bindPopup%28popup_3a114402883b481eb443e1b0ce2ebdba%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_e514cd369796486e9802b1711547368f%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8708838775078237%2C%2041.6390382112928%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_e2558f8672ce470aa0a9d90e5cbdf5a4%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_c41f227007594232b9416f4f4e36a917%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_c41f227007594232b9416f4f4e36a917%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECAIDA%20SOBRE%20CALZADA%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_e2558f8672ce470aa0a9d90e5cbdf5a4.setContent%28html_c41f227007594232b9416f4f4e36a917%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_e514cd369796486e9802b1711547368f.bindPopup%28popup_e2558f8672ce470aa0a9d90e5cbdf5a4%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_6d8c79a70dcf417a9fdc93b2062cc673%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8970649943808023%2C%2041.64083344974765%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_6433ad7ae8d24a8483f5872788c9feb4%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_fdc85672087941d5be7b8b9479cfb098%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_fdc85672087941d5be7b8b9479cfb098%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLIS.%20MARCHA%20ATR%C3%81S%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_6433ad7ae8d24a8483f5872788c9feb4.setContent%28html_fdc85672087941d5be7b8b9479cfb098%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_6d8c79a70dcf417a9fdc93b2062cc673.bindPopup%28popup_6433ad7ae8d24a8483f5872788c9feb4%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_83dd9abd99e2425381ce0dce5f79f5f2%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8718525605769747%2C%2041.64904657717317%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_13fa37182c924b7ba1734df6a4e4529b%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_e0b20d3160b94df1824bc861f326a7bc%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_e0b20d3160b94df1824bc861f326a7bc%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20LATERAL%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_13fa37182c924b7ba1734df6a4e4529b.setContent%28html_e0b20d3160b94df1824bc861f326a7bc%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_83dd9abd99e2425381ce0dce5f79f5f2.bindPopup%28popup_13fa37182c924b7ba1734df6a4e4529b%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_05d0f958f31442ed8141998634b45806%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8964627561577849%2C%2041.64322365075108%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_a0c6c12c009242d4af21503c2802e0b3%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_f6187a84ba414bb1ab56363508f1a3cf%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_f6187a84ba414bb1ab56363508f1a3cf%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3EOTRAS%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_a0c6c12c009242d4af21503c2802e0b3.setContent%28html_f6187a84ba414bb1ab56363508f1a3cf%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_05d0f958f31442ed8141998634b45806.bindPopup%28popup_a0c6c12c009242d4af21503c2802e0b3%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_07e07ba9f5b04695b4560a5ee5ff0740%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8778095796207178%2C%2041.68753087470739%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_745c97861c1b41a6916f54ccdc531766%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_bb046ce964314703bced4c8f14022321%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_bb046ce964314703bced4c8f14022321%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_745c97861c1b41a6916f54ccdc531766.setContent%28html_bb046ce964314703bced4c8f14022321%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_07e07ba9f5b04695b4560a5ee5ff0740.bindPopup%28popup_745c97861c1b41a6916f54ccdc531766%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_43e8c8937b0e40c3923720f332c42714%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8812157329722801%2C%2041.661646612715046%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_cadb007342924d60ba1fe92c5c661474%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_5722d1e73e62457da97bb4bd5d3dccb6%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_5722d1e73e62457da97bb4bd5d3dccb6%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ESALIDA%20CALZADA%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_cadb007342924d60ba1fe92c5c661474.setContent%28html_5722d1e73e62457da97bb4bd5d3dccb6%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_43e8c8937b0e40c3923720f332c42714.bindPopup%28popup_cadb007342924d60ba1fe92c5c661474%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_b99bcb92a6544221a402751d87c04b62%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8762000299022707%2C%2041.6454384961757%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_80bd9a5f2e054663aa3a91385d45c5cb%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_2be5c08f0b4746a2ad52f9e5b7f7b608%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_2be5c08f0b4746a2ad52f9e5b7f7b608%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_80bd9a5f2e054663aa3a91385d45c5cb.setContent%28html_2be5c08f0b4746a2ad52f9e5b7f7b608%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_b99bcb92a6544221a402751d87c04b62.bindPopup%28popup_80bd9a5f2e054663aa3a91385d45c5cb%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_1959bc08c5b94692bb4e2357a392cb88%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.9089013552408617%2C%2041.65543768899759%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_26284a2bd3094652a0a4319e95ff9364%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_4c1b2b2206ee4383a96da78d3dcdb942%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_4c1b2b2206ee4383a96da78d3dcdb942%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3EATROPELLO%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_26284a2bd3094652a0a4319e95ff9364.setContent%28html_4c1b2b2206ee4383a96da78d3dcdb942%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_1959bc08c5b94692bb4e2357a392cb88.bindPopup%28popup_26284a2bd3094652a0a4319e95ff9364%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_cc6b9242eb7f43bb952c6b9c2ba70f79%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.9004729973337304%2C%2041.65180346604993%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_8b53a210cccc42eb8f53a2bf3ec955c8%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_246bb8f2f45146f89f7fb5f6a79cc099%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_246bb8f2f45146f89f7fb5f6a79cc099%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_8b53a210cccc42eb8f53a2bf3ec955c8.setContent%28html_246bb8f2f45146f89f7fb5f6a79cc099%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_cc6b9242eb7f43bb952c6b9c2ba70f79.bindPopup%28popup_8b53a210cccc42eb8f53a2bf3ec955c8%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_a2191d6599564148bf82ebd87568d98d%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8917562993466011%2C%2041.65233828238132%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_cc16e5e5797042348e94f20a7d723613%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_caee25e515184bc59d6dc6bd8c3ab77f%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_caee25e515184bc59d6dc6bd8c3ab77f%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_cc16e5e5797042348e94f20a7d723613.setContent%28html_caee25e515184bc59d6dc6bd8c3ab77f%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_a2191d6599564148bf82ebd87568d98d.bindPopup%28popup_cc16e5e5797042348e94f20a7d723613%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_c227d79cb6ed47db8fbfe1333124477e%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.888856043735591%2C%2041.65040494617356%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_540987877b20485589cc8a11ff77ce04%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_bb1f808c01004999816c750cf019da14%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_bb1f808c01004999816c750cf019da14%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_540987877b20485589cc8a11ff77ce04.setContent%28html_bb1f808c01004999816c750cf019da14%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_c227d79cb6ed47db8fbfe1333124477e.bindPopup%28popup_540987877b20485589cc8a11ff77ce04%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_9335fe44f37246ec914148e81767b723%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8629911318784169%2C%2041.645335650478316%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_55240c42cec14383a87255a446d2e8d4%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_06f216bc1d6b4a1889c92e837a5df405%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_06f216bc1d6b4a1889c92e837a5df405%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_55240c42cec14383a87255a446d2e8d4.setContent%28html_06f216bc1d6b4a1889c92e837a5df405%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_9335fe44f37246ec914148e81767b723.bindPopup%28popup_55240c42cec14383a87255a446d2e8d4%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20marker_ac3bedf34fa0433dad3406ffa71d608c%20%3D%20L.marker%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5B-0.8870207060655807%2C%2041.609992514227066%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_bd0280be99a04da8b7fb49f143768e1f%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20var%20popup_b38e99a06ff140158cea87a0871f58b7%20%3D%20L.popup%28%7B%22maxWidth%22%3A%20%22100%25%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20html_6be93a08f8664133abd2bfc200bb07b5%20%3D%20%24%28%60%3Cdiv%20id%3D%22html_6be93a08f8664133abd2bfc200bb07b5%22%20style%3D%22width%3A%20100.0%25%3B%20height%3A%20100.0%25%3B%22%3ECOLISI%C3%93N%20ALCANCE%3C/div%3E%60%29%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20popup_b38e99a06ff140158cea87a0871f58b7.setContent%28html_6be93a08f8664133abd2bfc200bb07b5%29%3B%0A%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20marker_ac3bedf34fa0433dad3406ffa71d608c.bindPopup%28popup_b38e99a06ff140158cea87a0871f58b7%29%0A%20%20%20%20%20%20%20%20%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%3C/script%3E onload="this.contentDocument.open();this.contentDocument.write(    decodeURIComponent(this.getAttribute('data-html')));this.contentDocument.close();" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>



Realizar un bucle para crear un mapa con cada uno de los puntos de nuestra tabla
