# Prueba-Anuncios-MERN
### SPA responsive encargada de mostrar los anuncios más relevantes utilizando el stack MERN
**FrontEnd:** [Front-Anuncios](https://github.com/ams113/frontAnuncios).

**BackEnd:** [Back-Anuncios](https://github.com/ams113/Back-Anuncios).

**Persistencia de datos** [MongoDB en local](https://docs.mongodb.com/manual/administration/install-community/).

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
- Definir las rutas para acceso la api con *express* [GET,POST] http://localhost:4000/api/ads
- Implemetar la función de puntuación del anuncio.
- Implementar GraphQL
- Implementar autentificación a la api con JWT

## Pruebas unitarias
- Realizar pruebas unitarias a los componetes del front con JEST y Enzyme
- Realizar pruebas a la api de acceso con la herramienta postman.

## Trabajo futuro
Como trabajo futuro en se podría implementar:
- Diseño responsive para el móvil o crear una PWA
- Utilizar Mongo Compass persistencia en la nube en lugar de una persistencia local.
- CRUD que permita gestionar los anuncios.
- Autenticación para los usuarios a través de tokens de acceso (JWT) e implementar google SingIn
- Protección de las rutas
- Implementar Https
- Gestión del perfil de usuario
- Sistema de logs para la app
- Dokerizar el proyecto.



    

