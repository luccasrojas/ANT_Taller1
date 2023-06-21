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

# Selección de patrón de diseño (Strategy)

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. En este caso es importante garantizar el correcto funcionamiento de los algoritmos en la operación del sistema y contar con la posibilidad de una elección de forma eficiente. 

## Decision Drivers

* RF7 - Disponibilidad de algoritmos inteligentes predictivos (optimización de ordenes de trabajo y predicción de fallos): Se debe garantizar la disposición de algoritmos predictivos. Como resultado, es necesario encapsular ambos algoritmos de tal forma que se facilite la selección y ejecución del algoritmo dependiendo las necesidades de cada situación.

## Considered Options

* Patrón de diseño (Strategy)

## Decision Outcome

Opcion planteada: "Patrón de diseño (Strategy)", porque de acuerdo a los requerimientos planteados este patrón permite la selección del algoritmo adecuado de forma dinámica, así como la definición de su lógica en clases separadas y la configuración de parámetros y criterios de forma flexible.

### Consequences
* Bueno, porque permite usar los algoritmos de forma dinámica sin afectar el modulo que los implemente.
* Bueno, porque garantiza la separación de responsabilidades en el sentido que cada algoritmo implementa su lógica por aparte sin afectar a otros componentes del sistema.
* Bueno, porque facilita el ajuste de parámetros y criterios debido a su naturaleza de encapsular los algoritmos en clases aisladas.
* Malo, porque se puede aumentar la complejidad del sistema si se opta por incluir múltiples clases.
* Malo, porque se puede presentar un elevado consumo en el sistema al momento de realizar la comunicación entre la clases principal y sus estrategias. 
   
### Confirmation
Este ítem es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo tras la implementación de este patrón de diseño se sugiere la revisión del funcionamiento, por medio de pruebas tales cómo:

Correcto funcionamiento (selección de hiperparámetros)
Consumo de recursos
Rendimiento 

Para el caso del algoritmo de optimización de ordenes de trabajo se pueden establecer metricas de evaluación como por ejemplo la reducción de tiempo de entrega, la asignación de recursos o la minimización de los costos, y de acuerdo a esto evaluar la efectividad del algoritmo.

## Pros and Cons of the Options

### {Strategy}

* Bueno, porque facilita la adaptación a diferentes situaciones y cambios debido a su flexibilidad al momento de seleccionar diferentes algoritmos de forma dinámica.
* Bueno, porque permite la separación de responsabilidades debido a que cada estrategía se encapsula en su propia clase.
* Neutral, porque dependiendo de la complejidad del proyecto en algunas veces no es justificable el esfuerzo inicial al momento de la creación de múltiples clases y sus interfaces. 
* Malo, porque al implementar cada estrategía en su propia clase, se puede llegar a presentar una sobrecarga de clases y archivos que ocasione la dificultad de navegación  y mantenimiento del sistema.

## More Information
