# Prueba-Anuncios-MERN
### SPA responsive encargada de monstrar los anuncios más relevantes utilizando el stack MERN
## Requisitos funcionales.
El anuncio tiene que tener un valor de 0 a 100.

**Reglas de valoración generales**

- No foto <span style="color:red">**-10**</span>
- Foto HD <span style="color:green">**20**</span>
- Foto SD <span style="color:green">**10**</span>
- Descripción <span style="color:green">**5**</span>

**Reglas de valoración para la descripción del tipo** +Inmueble*

- Piso
  - Por número de palabras:
    - Si es =< 20 <span style="color:green">**10**</span>
    - Si es =< 50 <span style="color:green">**30**</span>
- Chalet
   - Por número de palabras:
   - Si es =< 50 <span style="color:green">**50** text</span>
- Tags valorados en la descripción:
  - Luminoso <span style="color:green">**5**</span>
  - Cuidado <span style="color:green">**5**</span>
  - Fabuloso <span style="color:green">**5**</span>
  - Único <span style="color:green">**5**</span>
  - Excepcional <span style="color:green">**5**</span>
  - Ocasión <span style="color:green">**5**</span>
  
**Reglas para calificar anuncio completo completo**

- Tipo vehículo <span style="color:green">**40**</span> si tiene:
 - KM
 - Color
 - Fabricante
- Tipo Frigrorífico <span style="color:green">**40**</span> si tiene:
 - Altura en cm
 - *Excecionalmente no necesita descripción*
- Tipo Inmueble
 - Metros cuadrados
 
 **Los anuncios serán irrelevantes con una valoración menor de 40**
 
 **Scroll infinito** 
  
    

