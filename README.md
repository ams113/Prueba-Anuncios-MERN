# Prueba-Anuncios-MERN
### SPA responsive encargada de monstrar los anuncios más relevantes utilizando el stack MERN
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
  
**Reglas para calificar anuncio completo completo**

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

## Diseño de interfaces 
##### Fase 0
La aplicación constará de dos interfaces y un modal
- Una interfaz principal con un Muro de anuncios 
- Una interfaz secundaria con el detalle del anuncio seleccionado.
- Un modal para añadir un anuncio al muro
##### Fase 1
- Interfaz del login
- Interfaz de regisro
##### Fase 2
- Interfaz gestión de anuncios.


    

