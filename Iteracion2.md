---
parent: Decisions
nav_order: 100
title: Iteración 2

# status: proposed
# date: 2023-06-20
# deciders: 
  * Julian Andres Mendez Melo
  * Alejandro Ahogado Prieto 
# consulted: 
  * Maria Alejandra Vargas
  * Luccas Rojas
# informed:
  * Mariangela Gabriela Paez

# Selección de primer patrón de diseño (Observer)

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. En este caso es importante encontrar una solución para comunicar los diferentes sensores entre sí y notificar a los que se encuentren suscritos. 

## Decision Drivers

* RF1 - Visualización de analíticas (proceso productivo y órdenes de trabajo): Se debe garantizar una visualización en tiempo real de las analíticas del sistema. Por lo que es importante que el estado de las diferentes etapas del proceso vaya siendo presentado en los gráficos correspondientes, lo cuál debe verse reflejado en el porcentaje del personal y de los recursos asignados. 
* RF4 - Visualizar las analíticas de los sensores IoT: Es importante conocer en tiempo real el envío de mensajes entre los sensores, la recepción de los datos y el estado de sus conexiones.

## Considered Options

* Patrón de diseño (Observer)

## Decision Outcome

Opcion planteada: "Patrón de diseño (Observer)", porque de acuerdo a los requerimientos planteados este patrón permite establecer una comunicación desacoplada entre los diferentes componentes observadores, garantizando una interacción constante y efectiva entre el modulo de visualización y los diferentes estados que se puedan presentar.

### Consequences
* Bueno, porque se garantiza una actualización en tiempo real de los estados y sus datos asociados.
* Bueno, porque evita realizar múltiples consultas sobre los mismos datos.
* Bueno, porque se continúa garantizando la arquitectura flexible y desacoplada.
* Bueno, porque se abre la posibilidad de tener un sistema altamente escalable al poder agregar nuevos objetos observadores en caso de ser necesario.

* Malo, porque puede darse un elevado consumo de recursos debido al exceso de notificaciones.
* Malo, porque se puede presentar un rendimiento deficiente en caso de no contar con la infraestructura necesaria.
* Malo, porque al ser un flujo de actualización constante puede ser difícil depurarlo.
   
### Confirmation
Este item es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo tras la implementación de este patrón de diseño se sugiere la revision del funcionamiento, por medio de pruebas tales cómo:

Integración
Rendimiento (cantidad de notificaciones)
Consumo de recursos
Actualización en tiempo real

## Pros and Cons of the Options

### {Observer}

* Bueno, porque se garantiza comunicación eficiente entre los elementos relacionados (estado del proceso productivo y órdenes de trabajo, con la visualización de las gráficas y los datos presentados).
* Bueno, porque permite presentar siempre información precisa y actualizada.
* Neutral, porque la gestión del sistema (notificaciones y actualizaciones) puede generar una complejidad adicional.
* Malo, porque puede haber un impacto en el rendimiento en caso de que se quieran procesar analiticas de una cantidad muy grande de observadores a la vez, con una alta frecuencia de actualización.

## More Information

PENDIENTE, links relacionados
