# Prueba-Anuncios-MERN
### SPA responsive encargada de mostrar los anuncios más relevantes utilizando el stack MERN
**FrontEnd:** [Front-Anuncios](https://github.com/ams113/frontAnuncios).

**BackEnd:** [Back-Anuncios](https://github.com/ams113/Back-Anuncios).

**Persistencia de datos** [MongoDB en la nube](https://www.mongodb.com/products/compass).

**Datos de ejemplo** [Datos anuncio](https://github.com/ams113/Back-Anuncios/tree/master/Data).



## Requisitos funcionales.
El anuncio tiene que tener un valor de 0 a 100 pts.

**Reglas de valoración generales**

- No foto <span style="color:red">**-10 pts**</span>
- Foto HD <span style="color:green">**20 pts**</span>
- Foto SD <span style="color:green">**10 pts**</span>
- Descripción <span style="color:green">**5 pts**</span>

**Reglas de valoración para la descripción del tipo** *Inmueble*

- Piso
  - Por número de palabras:
    - Si es =< 20 <span style="color:green">**10 pts**</span>
    - Si es =< 50 <span style="color:green">**30 pts**</span>
- Chalet
  - Por número de palabras:
    - Si es =< 50 <span style="color:green">**50 pts**</span>
- Tags valorados en la descripción:
  - Luminoso <span style="color:green">**5 pts**</span>
  - Cuidado <span style="color:green">**5 pts**</span>
  - Fabuloso <span style="color:green">**5 pts**</span>
  - Único <span style="color:green">**5 pts**</span>
  - Excepcional <span style="color:green">**5 pts**</span>
  - Ocasión <span style="color:green">**5 pts**</span>
  
**Reglas para calificar anuncio completo**

- Tipo vehículo <span style="color:green">**40 pts**</span> si tiene:
 - KM
 - Color
 - Fabricante
- Tipo Frigrorífico <span style="color:green">**40 pts**</span> si tiene:
 - Altura en cm
 - *Excecionalmente no necesita descripción*
- Tipo Inmueble
 - Metros cuadrados
 
 **Los anuncios serán irrelevantes con una valoración menor de 40 pts**
 
 **Scroll infinito** 
  
### Observaciones de los requisitos.
- Según los toppings de valoración un piso puede llegar a tener 120 puntos de valoración.
- El algoritmo de valoración se dará mayor relevancia a los del tipo inmueble.

## Diseño de screens para el frontend
#### Fase 1
La aplicación constará de dos interfaces y un modal
- Una interfaz principal con un Muro de anuncios 
 - Incluir Lazyload para la carga de los anuncios.
- Una interfaz secundaria con el detalle del anuncio seleccionado.
- Un modal para añadir un anuncio al muro

#### Fase 1
- Interfaz del login
- Interfaz de regisro

## Diseño de la estructura backend
- Conexión con la base de datos mediante *Mongoose*
- Definir el modelo de esquema para la colección de Mongo Anuncio.
- Definir las rutas para acceso la api http://localhost:4000/graphql
- Implemetar la función de puntuación del anuncio.
- Implementar GraphQL
- Implementar autentificación a la api con JWT

## Boceto de la interfaz de usuario


![interfaces](https://github.com/ams113/Prueba-Anuncios-MERN/blob/master/interfaces.PNG?raw=true)

## Arquitectura del proyecto

Se trata de diseñar una arquitectura microservicos lo más desacoplada posible, y preparado para trabajar en la nube. Que consta de un Frontend la parte de la interfaz de usuario o cliente, el backend donde se accede a la información y se trata y un servicio de alojamiento en la nube. Para el almacenamiento de las imagenes se utiliza AWS y para lo demás se utiliza Mongo Compass. La comunicación con la API del backend se realiza con el cliente de Apollo que se ha integrado en nuestro frontEnd.

Para el FrontEnd desarrollado con react.js tiene una interfaz pública donde te puedes registrar o loguear con tu usuario de manera segura ya que la contraseña se guarda
cifrada. La autenticación y autorización se maneja a través de la tecnologia JWT. En la parte privada podrás consultar los anuncios más relevantes según la calidad de la información de estos o subir un anuncio.

![register](https://github.com/ams113/Prueba-Anuncios-MERN/blob/master/register.PNG?raw=true)

![login](https://github.com/ams113/Prueba-Anuncios-MERN/blob/master/login.PNG?raw=true)

Para el backend se utliza la tecnología de Node.js junto a la plataforma ![Apollo](https://www.apollographql.com/) que integra la interfaz de GraphQL, con esta tecnología nos permite tener una API de acceso a la informacion mantenible y versátil según la información requeriada por los distintos dispositivos o clientes, ya que centra el acceso a la información en un único endpoint. Además, GraphQL al tener bien definida y estructurada la información con la que trabaja, facilita la autodocumentación de la API.

Cuando un cliente quiere se registra en nuestra APP el backend almacena la información la cifra y la almacena por un canal seguro en la nube. El Servidor valida a un usuario con un token de acceso temporal. Que le permite durante 24 horas poder interactuar con la APP después tiene que volver a loguear. En el caso caso de tener distintos perfiles de usuario gracias al token se pordía hablitiar o no determinados servicios.

Publicar un anuncio se realiza por partes, la información del anuncio a una petición a través de graph y el backend guarda esa información en la nube con el driver de mongoose, pero las imágenes se almamacen en un servicio de amazon en concreto el Bucket S3 AWS un servicio muy ecónomico y elástico. Después, el servico asíncrono de **puntuación del anuncio analiza el anuncio y le da una puntuación de calidad** actualizando la información la puntuación del anuncio aposteriori.

![anuncio](https://github.com/ams113/Prueba-Anuncios-MERN/blob/master/anuncio.PNG?raw=true)

El servicio de puntuación de anuncio como otros servicios podrían ser independinte, se podria introducir un sistema de colas mediande Apache KAFKA de manera que todos los servicios estarían dados de alta en la plataforma y mediante un patrón publicador/subcritor dandole a unestro proyecto un enfoque de mayor consistencia a una arquitectura de micro servicios, temporalidad y escalabilidad. Esta tencnología se comunica mediate web sockets para entederse con "mensajes" de subscripción a los topic o entrega de información.

Para el desplieque y la contrucción de las partes se utiliza docker, es una forma de virtualización ligera que nos libera de la dependecia con los sistemas operativos donde se despliega el proyecto. Una vez, selecionado el lugar de desplieque mediante docker-compose agrupamos todo el despliegue de nuestro proyecto y la configuación de los accesos y variables de entorno. En el caso de kafka necesitaremos levantar un docker con el servidor zookeeper con el que poder trabajar.

Una arquitectura tolerante a fallos, con Docker nos permite que si un servico se cae automaticamente lo levanta, o levantar una copia de él en caso de sobrecarga con esto ganamos mayor disponibilidad de nuestros servicios, también mongo permite repartir la infomción en distintos clusters en caso que de falle uno otro se hace cargo y la infomación siempre esta accesible.

## Pruebas unitarias
- Realizar pruebas unitarias a los componetes del front con JEST y Enzyme
- Realizar pruebas a la api de acceso con la herramienta postman graphQL beta.

## Trabajo futuro
Como trabajo futuro en se podría implementar:
- Barra de búsqueda de anuncios
- Diseño responsive para el móvil o crear una PWA
- Gestión de los anuncios.
- Gestion de usuaros
- Protección de las rutas
- Implementar Https
- Sistema de logs para la app
- Despliegue total en la nube
- Terminar desplegar kafka 
- Sistema de seguimiento  para los anuncios y alerta mediante push.



    

