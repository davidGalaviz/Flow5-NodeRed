# Flow5-NodeRed
Este repositorio contiene el flow 5 del curso de NodeRed. visto en los contenidos de codigoIoT

## Introducción

En este flow podrá observarse un conjunto de gráficas en Dasboard, las cuales tienen como proposito reportar la información climática recibida manualmente por MQTT, la información recibida automáticamente por API y la información de varios usuarios compartida por MQTT en un broker publico. Se usaran los siguientes nodos

- Mqtt-in y Mqtt-out

   > El nodo **mqtt-in** se conecta a un broker de mqtt y se suscribe al tema especificado
   > El nodo **mqtt-out** se conecta a un broker y publica al tema especificado
- Json

   > El nodo **json** convierte una string de un json a su objeto de JavaScript y viceversa
- Function
 
   > El nodo **function** ejecuta una función de JavaScript en el mensaje que esta siendo recibido 
- Los nodos **guage** y **chart** de los nodos dashboard
- HTTP request

   > El nodo **HTTP request** manda un http request y regresa la respuesta

### Material Necesario

Para realizar este ejercicio necesitaras lo siguente

- [Ubuntu 20.04](https://ubuntu.com/download/desktop)
- [NodeJs](https://nodejs.org/en/)
  - [NPM](https://www.npmjs.com/)
  - [NodeRed](https://nodered.org/)
  - Nodos Dashboard
      > Se pueden instalar desde Manage palette en node red, En este caso instalamos **node-red-dashboard**
  - [Mosquitto](https://mosquitto.org/)

### Material de referencia

- [Instalación de Virtual Box](https://edu.codigoiot.com/course/view.php?id=810)
  - [Instalación de Ubuntu 20.04](https://edu.codigoiot.com/course/view.php?id=812)
- [Instalación de NodeRed](https://edu.codigoiot.com/course/view.php?id=817)
- [Introducción a NodeRed](https://edu.codigoiot.com/course/view.php?id=278)
- [Introducción a Mosquitto](https://edu.codigoiot.com/course/view.php?id=851)

# Instrucciones

## Requisitos previos

1. Tener instalado todo el software listado en el **Material necesario**
2. Arrancar NodeRed escribiendo el comando `node-red` en la terminal
3. Abrir aplicacion de NodeRed en un navegador con la dirección ["http://localhost:1880"](http://localhost:1880/#flow/d0319225ca32761b)
4. Cuenta en OpenWeatherMap.org. Este es el servidor del cual se obtendrán los datos del clima por API
5. API Key valida. Deberás generar una API Key con tu cuenta de openweathermaps.org

## Instrucciones de preparación del entorno

Para ejecutar este flow, es necesario lo siguiente:

1. Arrancar NodeRed con el comando node-red
2. Importar el flow del repositorio.
3. Coloca tu API Key personal en la API Call del nodo HTTP Request.
4. Actualiza la IP del broker público.
   > nslookup broker.hivemq.com
5. Hacer clic en el boton Deploy.

## Instrucciones de operación

- Para observar el resutlado de este flow, abre un navegador y dirígete a localhost:1880/ui.
- Para activar las gráficas de clima manual, debes enviar por MQTT un mensaje que contenga un JSON con las variables ID, temp y hum.
   > mosquitto_pub -h localhost -t ccodigoIoT/fow5/mqtt -m '{"ID":"Hugo Vargas","temp":18,"hum":78}'

# Resultados 

El flow debera verse como el flow de la siguiente imagen

![resultados del flow](https://github.com/davidGalaviz/Flow5-NodeRed/blob/main/flow5%20nodos.png)

Entra a [http://localhost:1880/ui](http://localhost:1880/ui/#!/0?socketid=OGWdowKrOPcSz4pfAAAD) para ver el Dashboard

![resultados en el Dashboard](https://github.com/davidGalaviz/Flow5-NodeRed/blob/main/flow5climaPublico.png)

## Evidencias

[Repositorio](https://github.com/davidGalaviz/flow4-NodeRed)

# Creditos

Desarrollado por David Galaviz

[GitHub](https://github.com/davidGalaviz)
