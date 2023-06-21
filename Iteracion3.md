---
parent: Decisions
nav_order: 100
title: Iteración 3

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

# Selección de patrón de diseño (Data Access) para almacenamiento en BBDD

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. En este caso es importante encontrar una solución para almacenar las ordenes de trabajo y el inventario existente de los materiales (cada uno con un identificador único). 

## Decision Drivers

* RF5 - Almacenamiento de datos en la BBDD: Se debe garantizar la posibilidad de almacenar las órdenes de trabajo y el inventario existente de los materiales, el cuál va a irse actualizando constantemente. Se necesita que se continue respetando la modularidad del sistema y la escalabilidad del mismo. 

## Considered Options

* Patrón de diseño (Data Access)

## Decision Outcome

Opción planteada: "Patrón de diseño (Data Access)", porque de acuerdo a los requerimientos planteados este patrón permite continuar con la separación de responsabilidades, garantizando un sistema con una alta modularidad y mantenimiento. De igual manera, al proporcionar una capa de abstracción entre la lógica y la base de datos, se abre la posibilidad de realizar migraciones sin afectar la lógica de la aplicación (lo cuál es viable que suceda por el tipo de datos que se van a almacenar ya que el inventario puede cambiar se manera significativa). Asi mismo, este patrón facilita la posibilidad de optimizar el acceso los datos para mejorar la escalabilidad y rendimiento del sistema. 

### Consequences
* Bueno, porque facilita la implementación de pruebas específicas.
* Bueno, porque aumenta la confiabilidad del sistema al tener una mayor cobertura en las pruebas.
* Bueno, porque garantiza una arquitectura escalable y mantenible.
* Malo, porque la complejidad en la implementación puede aumentar por los componentes necesarios y la consistencia entre estos.
* Malo, puede presentarse una sobrecarga de código.
* Malo, porque si no se optimiza de manera adecuada puede afectar el rendimiento.
   
### Confirmation
Este item es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo tras la implementación de este patrón de diseño se sugiere la revision del funcionamiento, por medio de pruebas tales cómo:

- Consistencia de datos
- Funcionalidad (operaciones CRUD)
- Rendimiento (acceso a datos)
- Integridad de datos
- Seguridad

## Pros and Cons of the Options

### {DAO}

* Bueno, porque facilitar la separación de responsabilidades. Al separar la lógica del acceso a datos de la lógica del negocio.
* Bueno, porque se puede reutilizar código del acceso a datos.
* Bueno, porque brinda flexibilidad frente a las tecnologías implementadas en el sistema. 
* Neutral, porque el rendimiento asociado depende de la implementación específica que se realice, al igual que la escalabilidad del sistema, la cuál se ve estrechamente relacionado con las estrategias y arquitectura en general.
* Malo, por la complejidad en su implementación al buscar establecer la comunicación concreta entre el negocio y los datos.

## More Information

PENDIENTE, links relacionados
