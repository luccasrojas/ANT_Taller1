---
parent: Decisions
nav_order: 100
title: Iteración 2

# status: Aprobada
# date: 2023-06-20
# deciders: 
  * Julian Andres Mendez Melo
  * Alejandro Ahogado Prieto 
# consulted: 
  * Maria Alejandra Vargas
  * Luccas Rojas
# informed:
  * Mariangela Gabriela Paez

# Selección de patrón de diseño (Strategy)

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. 
En este caso es importante garantizar el correcto funcionamiento de los algoritmos en la operación del sistema y contar con la posibilidad de una elección de forma eficiente. 

## Decision Drivers

* RF7 - Disponibilidad de algoritmos inteligentes predictivos (optimización de ordenes de trabajo y predicción de fallos): Se debe garantizar la disposición de algoritmos predictivos. Como resultado, es necesario encapsular ambos algoritmos de tal forma que se facilite la selección y ejecución del algoritmo dependiendo las necesidades de cada situación.

## Considered Options

* Patrón de diseño (Strategy)

## Decision Outcome

Opción planteada: "Patrón de diseño (Strategy)", porque de acuerdo a los requerimientos planteados este patrón permite la selección del algoritmo adecuado de forma dinámica, así como la definición de su lógica en clases separadas, la configuración de parámetros y criterios de forma flexible.

### Consequences
* Bueno, porque permite usar los algoritmos de forma dinámica sin afectar el módulo que los implemente.
* Bueno, porque garantiza la separación de responsabilidades en el sentido que cada algoritmo implementa su lógica por aparte sin afectar a otros componentes del sistema.
*Malo, porque se genera un nuevo procesamiento en la elección del algoritmo. 
* Malo, porque se puede aumentar la complejidad del sistema si se tienen múltiples algoritmos en caso que se agreguen con la escalabilidad.
* Malo, porque se puede presentar un elevado consumo en el sistema al momento de realizar la comunicación entre la clase principal y sus estrategias. 
   
### Confirmation
Este ítem es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo, tras la implementación de este patrón de diseño se sugiere la revisión del funcionamiento, por medio de pruebas tales como:

Correcto funcionamiento (selección de hiperparámetros)
Consumo de recursos
Rendimiento 

Para el caso del algoritmo de optimización de las ordenes de trabajo se pueden establecer métricas de evaluación como por ejemplo la reducción de tiempo de entrega, la asignación de recursos o la minimización de los costos, y de acuerdo a esto evaluar su efectividad.

## Pros and Cons of the Options

### {Strategy}
* Bueno, permite optimizar procesos dependiendo de la situación y los datos que hayan sido procesados anteriormente. 
* Malo, este nuevo componente implica costos y mantenimiento adicionales.

## More Information
