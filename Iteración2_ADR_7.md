---
parent: Decisions
nav_order: 100
title: Iteración 2

# status: Aprobada
# date: 2023-06-23
# deciders: 
  * Julian Andres Mendez Melo
  * Alejandro Ahogado Prieto 
# consulted: 
  * Maria Alejandra Vargas
  * Luccas Rojas
# informed:
  * Mariangela Gabriela Paez

# Selección del patrón de diseño (Circuit Breaker)

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. 

Lo anterior con el fin de garantizar los 4 intentos cada 30 segundos y así indentificar que si se supera esté número de intentos, entonces considerar el dispositivo como caído. 


## Decision Drivers

* RF9 - Reconocimiento del estado y conexión del dispositivo:  Es importante garantizar que el tiempo entre cada intento de conexión no supere los 30 segundos y, además, al superarse los 4 intentos, entonces se considere el dispositivo como caído. Por lo tanto, se requiere detectar fallos con el fin de evitar que se repitan solicitudes fallidas de forma constante y cerrar la conexión en caso que las solicitudes fallidas superen los 4 intentos.

## Considered Options

* Patrón de diseño (Circuit Breaker)

## Decision Outcome

Opcion planteada: "Patrón de diseño (Circuit Breaker)", porque de acuerdo a los requerimientos planteados este patrón encapsula la lógica con el fin de que un fallo de conexión de un dispositivo no ocurra repetitivamente, sino que frente a una solicitud fallida entonces se genera un tiempo de espera antes del siguiente intento de conexión, además de que permite manejar las situaciones en las que se intenta multiples solicitudes para asegurar que después de 4 intentos se considere el dispositivo como fuera de servicio.

### Consequences
* Bueno, porque se puede definir el tiempo y el número de peticiones en función de la familia de sensores.
* Bueno,   porque ante la presencia de un fallo es posible mostrar al usuario un mensaje amigable junto al error ocasionado.
* Bueno, porque permite ajustar un tiempo de espera entre cada reintento evitando así las esperas en las prolongadas peticiones que seguiran fallando. 
* Malo, porque al momento de ocurrir un error puede ser complejo realizar una depuración con el propósito de hallar el origen del problema. 
   
### Confirmation
Este ítem es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo, tras la implementación de este patrón de diseño se sugiere la revisión del funcionamiento, por medio de pruebas tales como:

Tiempo de espera (durante cada intento)
Resolución de lógica (asegurarse que luego de 4 intentos el dispositivo se identifique como fuera de servicio)
Rendimiento 

## Pros and Cons of the Options

### {Circuit Breaker}
* Bueno, porque permite identificar rapidamente los fallos presentes en servidor cuando este se encuentra caído, evitando tiempos de esperas excesivos.
* Bueno, porque ayuda a disminuir el tiempo del sistema en darse cuenta que un componente se encuentra fuera de servicio, y de esta manera, se espera mejorar la mantenibilidad.
* Malo, porque al intentar realizar múltiples intentos se puede ocasionar un impacto negativo en el rendimiento del sistema. 
* Neutro, porque al no configurarse de forma adecuada el circuit breaker se puede generar una inestabilidad en el sistema que impida la capacidad de escalar en un futuro.

## More Information
