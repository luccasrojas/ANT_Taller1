---
parent: Decisions
nav_order: 100
title: Iteración 1

# status: proposed
# date: 2023-06-18
# deciders: 
  * Julian Andres Mendez Melo
  * Alejandro Ahogado Prieto 
# consulted: 
  * Maria Alejandra Vargas
  * Luccas Rojas
# informed:
  * Mariangela Gabriela Paez

# Selección del estilo arquitectónico (Event Driven)

## Context and Problem Statement
De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el estilo arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. 

## Decision Drivers

* RF3 - Gestión de los datos de los sensores IoT: De acuerdo al estado de los sensores pueden generarse eventos en el sistema que faciliten la comunicación en tiempo real con otros componentes suscritos a estos eventos, que les permita cumplir con las necesidades planteadas.
* RF8 - Notificar actualizaciones, fallos o sobrecargas: Se necesita garantizar una comunicación asíncrona, que le permita al sistema estar preparado para ejecutar ciertas acciones de acuerdo al evento generado por los sensores.
  
## Considered Options

* Estilo arquitectónico Event driven

## Decision Outcome

Opción planteada: "Estilo arquitectónico Event driven" porque de acuerdo a los requerimientos planteados este estilo permite cumplir con un sistema altamente reactivo y flexible, garantizando la comunicación asíncrona a través de eventos. De igual manera, el estilo event-driven asegura el correcto funcionamiento de un sistema dependiente de las notificaciones y dispuesto a responder de forma eficiente a los datos y al entorno. 

Además, este estilo arquitectónico permite que los usuarios se suscriban a los eventos en los que tengan interés como: actualizaciones de la producción, fallos en los sensores o sobrecarga en la producción. Este a su vez puede ser de tipo simple o en "stream".

### Consequences

* Bueno, porque permite integración de diferentes sistemas y componentes.
* Bueno, porque permite manejar escenarios donde la concurrencia es necesaria.
* Bueno, porque garantiza un desacoplamiento de componentes al pemitir suscribirse a la informacion necesaria.
* Malo, porque puede presentarse dificultad en la gestión de eventos al existir muchos suscriptores.
* Malo, porque debido a la naturaleza asincróna, las pruebas y depuración del sistema pueden volverse más complejas.

### Confirmation

Este item es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo tras la implementación de este estilo arquitectónico se sugiere la revision del funcionamiento, por medio de pruebas tales cómo:
- Integración
- Unidad (se refiere a los sensores)
- Rendimiento
- Consumo de recursos
- Seguridad

## Pros and Cons of the Options

### {Event driven}
* Bueno, porque asegura la posibilidad de manejar un sistema altamente escalable.
* Bueno, porque permite un sistema con una alta disponibilidad por su tolerancia a fallos.
* Neutral, porque depende de una buena planificacion y diseño para su implementación.
* Neutral, porque puede presentarse un alto consumo de recursos pero depende mucho de la infraestructura actual del cliente. 


## More Information

Link alternativa 2: PENDIENTE
Revisión:
- Se agregó información al *Decision Outcome* para evidenciar la necesidad de la suscripción a eventos por parte de los usuarios de la linea de producción, debido a esto se reafirma que el estilo arquitectónico Event-Driven es el adecuado para este caso.
- Se cambió algunas *consecuencias* por *Pros y cons* de acuerdo a la plantilla dada para que correspondieran con la descripción. 


