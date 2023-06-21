---
parent: Decisions
nav_order: 100
title: Iteración 2 ADR 3

# status: aprobado 
# date: 2023-06-20
# deciders: 
  * Julian Andres Mendez Melo
  * Alejandro Ahogado Prieto 
# consulted: 
  * Maria Alejandra Vargas
  * Luccas Rojas
# informed:
  * Mariangela Gabriela Paez

# Selección de patrón de diseño (Repository) para almacenamiento en BBDD

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. 
En este caso es importante encontrar una solución para almacenar las ordenes de trabajo y el inventario existente de los materiales (cada uno con un identificador único), de este modo se puede tener una consulta más organizada y aislar la capa de datos. 

## Decision Drivers

* RF5 - Almacenamiento de datos en la BBDD: Se debe garantizar la posibilidad de almacenar las órdenes de trabajo y el inventario existente de los materiales, el cuál va a irse actualizando constantemente. Se necesita que se continue respetando la modularidad del sistema y la escalabilidad del mismo. 

## Considered Options

* Patrón de diseño (Repository)

## Decision Outcome

Opción planteada: "Patrón de diseño (Repository)", porque de acuerdo a los requerimientos planteados este patrón permite continuar con la separación de responsabilidades, garantizando un sistema con una alta modularidad y mantenimiento. De igual manera, al proporcionar una capa de abstracción entre la lógica y la base de datos, se abre la posibilidad de realizar migraciones sin afectar la lógica de la aplicación (lo cuál es viable que suceda por el tipo de datos que se van a almacenar ya que el inventario puede cambiar se manera significativa). 

### Consequences
* Bueno, porque facilita la implementación de pruebas específicas.
* Bueno, porque aumenta la confiabilidad del sistema al tener una mayor cobertura en las pruebas.
*Bueno, ya que se tiene un aislamiento y almacenamiento de la información.
* Malo, porque si no se implementa de manera adecuada puede afectar el rendimiento.
   
### Confirmation
Este ítem es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo, tras la implementación de este patrón de diseño se sugiere la revisión del funcionamiento, por medio de pruebas tales como:
- Consistencia de datos
- Funcionalidad (operaciones CRUD)
- Rendimiento (acceso a datos)
- Integridad de datos
- Seguridad

## Pros and Cons of the Options

### {Repository}
* Bueno, porque garantiza una arquitectura escalable y mantenible.

* Bueno, porque facilitar la separación de responsabilidades. Al separar la lógica del acceso a datos de la lógica del negocio.
* Bueno, porque se puede reutilizar código del acceso a datos.
* Bueno, porque brinda flexibilidad frente a las tecnologías implementadas en el sistema. 
* Neutral, porque el rendimiento asociado depende de la implementación específica que se realice, al igual que la escalabilidad del sistema, la cual se ve estrechamente relacionada con las estrategias y arquitectura en general.
* Malo, el mantenimiento puede ser costoso y más si dentro de este se cuenta con más de una base de datos
*Malo, la cantidad de información que se debe almacenar por cada sensor sino está bien empaquetada se tiene un aumento en el gasto de recursos ya que se tienen accesos no controlados a la base de datos.

## More Information


