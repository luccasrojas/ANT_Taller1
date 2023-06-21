---
parent: Decisions
nav_order: 100
title: Iteración 2 ADR 6

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

# Selección de patrón de diseño (Abstract Factory)

## Context and Problem Statement

De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados. En este caso es importante encontrar una solución para realizar la diferenciación de los tipos de sensores, con su respectiva funcionalidad. 
## Decision Drivers

* RF6 - Identificación de los sensores del sistema: Se debe garantizar la posibilidad de crear y gestionar diferentes familias de objetos (sensores) con características específicas.
## Considered Options

* Patrón de diseño (Abstract Factory)

## Decision Outcome

Opción planteada: "Patrón de diseño (Abstract Factory)", porque de acuerdo a los requerimientos planteados este patrón proporciona una solución coherente y consistente, para poder crear y gestionar las diferentes familias de sensores con características específicas. Abriendo la posibilidad de que el sistema pueda adaptarse y crecer con nuevas familias de sensores en el futuro.
* Bueno, porque facilita la creación y gestión de los diferentes sensores.
* Bueno, porque brinda flexibilidad y extensibilidad en el sistema en el caso de necesitar agregar nuevas familias de sensores sin tener que modificar el código existente.
* Bueno, porque garantiza la creación consistente los diferentes sensores, al seguir una interfaz definida.
* Malo, porque la complejidad inicial en la implementación aumenta de manera significativa en términos de código y diseño requerido, al tener que definir para cada familia su interfaz abstracta, fábrica concreta y productos correspondientes. 
* Malo, puede presentarse un mayor consumo de recursos, cómo por ejemplo de memoria y tiempo de ejecución.
* Malo, porque al agregar complejidad al código, se puede llegar a dificultar su comprensión.
   
### Confirmation
Este item es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo tras la implementación de este patrón de diseño se sugiere la revision del funcionamiento, por medio de pruebas tales cómo:

- Pruebas unitarias (garantizar creación y cumplimiento de funciones especificas) 
- Integración
- Rendimiento (situaciones de carga y estrés)
- Usabilidad 
- Seguridad

## Pros and Cons of the Options

### {ABSTRACT FACTORY}

* Bueno, porque evita acoplamiento directo entre productos concretos y el cliente.
* Bueno, porque se puede se pueden introducir variantes de productos de forma sencilla.
* Bueno, porque garantiza compatibilidad entre productos creados.
* Bueno, porque en caso de encapsular la lógica de creación, su mantenimiento puede ser sencillo.
* Neutral, porque al ser un patrón de diseño avanzado la curva de aprendizaje para el manejo de este puede verse afectada, sin embargo una vez que se supera, el sistema fluye con eficiencia y coherencia.
* Malo, por la complejidad en su implementación en caso de que existan múltiples familias de sensores con diferentes comportamientos.
## More Information

PENDIENTE, links relacionados
