# Prueba-Anuncios-MERN
### SPA responsive encargada de monstrar los anuncios más relevantes utilizando el stack MERN
## Requisitos funcionales.
El anuncio tiene que tener un valor de 0 a 100.
**Reglas de valoración generales**
- No foto <span style="color:red">some ** -10 ** text</span>
- Foto HD <span style="color:green">some ** 20 ** text</span>
- Foto SD <span style="color:green">some ** 10 ** text</span>
- Descripción <span style="color:green">some ** 5 ** text</span>
**Reglas de valoración para la descripción del tipo** +Inmueble*
- Piso
  - Por número de palabras:
    =< 20 <span style="color:green">some ** 10 ** text</span>
    =< 50 <span style="color:green">some ** 30 ** text</span>
- Chalet
  - Por número de palabras:
    =< 50 <span style="color:green">some ** 50 ** text</span>
- Tags valorados en la descripción:
  - Luminoso <span style="color:green">some ** 5 ** text</span>
  - Cuidado <span style="color:green">some ** 5 ** text</span>
  - Fabuloso <span style="color:green">some ** 5 ** text</span>
  - Único <span style="color:green">some ** 5 ** text</span>
  - Excepcional <span style="color:green">some ** 5 ** text</span>
  - Ocasión <span style="color:green">some ** 5 ** text</span>
**Reglas para calificar anuncio completo completo**
- Tipo vehículo <span style="color:green">some ** 40 ** text</span> si tiene:
 - KM
 - Color
 - Fabricante
- Tipo Frigrorífico <span style="color:green">some ** 40 ** text</span> si tiene:
 - Altura en cm
 - *Excecionalmente no necesita descripción*
- Tipo Inmueble
 - Metros cuadrados
 **Los anuncios serán irrelevantes con una valoración menor de 40**
 **Scroll infinito** 
  
    

