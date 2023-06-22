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

# Selección de primer patrón de diseño (Chain of Responsability)

## Context and Problem Statement
De acuerdo a un sistema planteado para una factoría inteligente 4.0 se necesita definir el patrón arquitectónico para satisfacer los requerimientos funcionales identificados. El sistema consta de 3 líneas de producción y cuenta con más de 10 sensores IoT que se encargan de recopilar la información sobre el estado de los dispositivos físicos relacionados.
Para comunuicar los diferentes sensores entre sí y notificar a los componentes que se encuentren suscritos a estos. 

## Decision Drivers
*RF6 – 6.2: Identificación de los sensores del sistema: Es importante poder pasar las peticiones a lo largo de la cadena de sensores, donde cada uno procesa la información y la envía al siguiente manejador o sensor. 

## Considered Options

* Patrón de diseño (Chain of Responsability)
* Patrón de diseño (Observer)
* Patrón de diseño (Publish-Subscribe)
## Decision Outcome
Opcion planteada: "Patrón de diseño (Chain of Responsability)". Este patrón permite el flujo de comunicación a través de los sensores, en la que cada uno tiene una responsabilidad y cada uno añade información o datos al mensaje final que se envía.

### Consequences
* Bueno, porque se garantiza una actualización en tiempo real de los estados de los sensores y sus datos asociados.
*Bueno, permite generar una cadena en donde cada sensor tiene una responsabilidad definida.
*Bueno, cada sensor es capaz de enviar, procesar y recibir información. 
*Bueno, permite saber cuáles son los componentes del sistema y cómo son sus conexiones. 
*Bueno, porque el resultado que se obtiene al final de la cadena puede ser utilizado por otros componentes, teniendo así que se puedan generar gráficas en tiempo real
*Malo, si uno de los sensores falla, esto se propaga a través de la cadena. 
* Malo, porque se puede presentar un rendimiento deficiente en caso de no contar con la infraestructura necesaria.
* Malo, porque al ser un flujo dependiente de varios componentes, su depuración no es fácil.
* Malo, la comunicación se puede volver complicada debido a la cantidad de elementos. 
   
### Confirmation
Este item es muy dependiente de la infraestructura con la que cuenta el cliente, sin embargo, tras la implementación de este patrón de diseño se sugiere la revisión del funcionamiento, por medio de pruebas tales cómo:

Integración
Rendimiento (cantidad de notificaciones)
Consumo de recursos
Actualización en tiempo real

## Pros and Cons of the Options

### { Chain of Responsability }

* Bueno, porque se garantiza comunicación eficiente entre los elementos relacionados (estado del proceso productivo y órdenes de trabajo, con la visualización de las gráficas y los datos presentados).
* Bueno, porque permite presentar siempre información actualizada.
* Bueno, porque se continúa garantizando la arquitectura flexible y desacoplada.
* Neutral, porque la gestión del sistema (notificaciones y actualizaciones) puede generar una complejidad adicional.
*Malo, ya que aumenta los puntos críticos del sistema. 
## More Information
Los siguientes requerimientos también se tienen en cuenta ya que son dependientes del sistema de los sensores:
* RF1 - Visualización de analíticas (proceso productivo y órdenes de trabajo): Se debe garantizar una visualización en tiempo real de las analíticas del sistema. Por lo que es importante que el estado de las diferentes etapas del proceso vaya siendo presentado en los gráficos correspondientes, lo cuál debe verse reflejado en el porcentaje del personal y de los recursos asignados.
* RF4 - Visualizar las analíticas de los sensores IoT: Es importante conocer en tiempo real el envío de mensajes entre los sensores, la recepción de los datos y el estado de sus conexiones.

[ADR1 - Observer](https://github.com/luccasrojas/ANT_Taller1/blob/Senior-Iteracion1/Iteracion2_ADR_2.md)
[ADR1 – Publish-Subscribe](https://github.com/luccasrojas/ANT_Taller1/blob/Senior-Iteracion1/iteraci%C3%B3n2_ADR_2_A1.md)

