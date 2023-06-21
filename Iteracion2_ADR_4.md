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

# Selección del patrón de diseño (Command)

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados.
Se debe asignar al operario las máquinas que debe manejar dentro del proceso productivo. 

## Decision Drivers

* RF7 - Asignación de ordenes de trabajo y máquinas a operarios (fabricación de componentes): Es importante realizar una asignación de ordenes de trabajos por operarios de forma adecuada en función de los recursos y la maquinaria disponible. Por lo que se requiere persistir información sobre operario asignado, la orden de trabajo y la máquina relacionada, así como ejecutar las correspondientes asignaciones.

## Considered Options

* Patrón de diseño (Command)

## Decision Outcome

Opcion planteada: "Patrón de diseño (Command)", porque de acuerdo a los requerimientos planteados este patrón permite encapsular una asignación como objeto, lo que da lugar a parametrizar los operarios con diferentes asignaciones de ordenes de trabajo y sus correspondientes maquinas.

### Consequences
* Bueno, porque garantiza la separación de responsabilidades entre los objetos involucrados por medio del encapsulamiento de las asignaciones. 
* Bueno, porque facilita la extensión de nuevas funcionalidades gracias al concepto de encapsulamiento de acciones en los comandos, teniendo que el sistema tenga una mejor adaptación a los cambios.
* Bueno, porque al tratarse de comandos es posible llegar a realizar un historial de acciones, el cual se puede almacenar con el objetivo de realizar análisis y seguimiento de las ordenes de trabajo por operario.

* Malo, porque puede aumentar la complejidad del sistema al momento de crear múltiples clases y gestionar las relaciones entre ellas.
   
### Confirmation
Este ítem es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo, tras la implementación de este patrón de diseño se sugiere la revisión del funcionamiento, por medio de pruebas tales como:

Encapsulamiento de ordenes de trabajo
Consumo de memoria (creación de múltiples comandos)
Rendimiento 

## Pros and Cons of the Options

### {Command}
* Bueno, porque ofrece flexibilidad al momento de adaptarse a cambios futuros. 
* Neutral, porque dependiendo del número de objetos se puede dificultar la depuración de problemas. 
* Malo, porque ante la presencia de múltiples comandos se puede dar una sobrecarga de memoria en sistemas cuando no se cuenta con los recursos  suficientes.

## More Information
