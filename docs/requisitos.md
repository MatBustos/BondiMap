# Requisitos de BondiMap

Este documento define qué debe hacer BondiMap y bajo qué condiciones debe funcionar durante su MVP.

Los requisitos describen el comportamiento esperado del sistema, sin depender de las tecnologías utilizadas para implementarlo.

El alcance se limita a una primera versión de prueba con un conjunto reducido de líneas. La expansión a AMBA y posteriormente a la provincia de Buenos Aires se considera una etapa futura.

---

## 1. Requisitos funcionales (RF)

Describen las funcionalidades que debe ofrecer el sistema.

### Consulta de líneas y recorridos

**RF-01:** El usuario puede consultar las líneas de colectivo disponibles en BondiMap.

**RF-02:** El usuario puede seleccionar una línea y consultar información sobre ella.

**RF-03:** El usuario puede consultar el recorrido vigente de una línea y visualizar sus paradas.

**RF-04:** El usuario puede identificar si una línea tiene modificaciones activas en su recorrido habitual.

**RF-05:** El usuario puede consultar información sobre una parada y conocer qué líneas pasan por ella.

*Pendiente de definir:* determinar qué información adicional se mostrará sobre cada línea y parada.

### Alertas y modificaciones

**RF-06:** El usuario puede consultar las alertas activas correspondientes a una línea.

**RF-07:** El usuario puede consultar información sobre desvíos temporales que afecten el recorrido de una línea.

**RF-08:** El usuario puede identificar las paradas que se encuentran temporalmente inhabilitadas.

**RF-09:** El sistema debe dejar de mostrar como activas las modificaciones cuya vigencia haya finalizado.

**RF-22:** El sistema debe generar una alerta cuando dos usuarios distintos reporten el mismo problema sobre la misma línea en el mismo día (ver D006 en decisiones.md).

*Pendiente de definir:* establecer cómo se determinan las fechas de inicio y finalización de cada modificación y qué sucede cuando no se conoce su duración. También, cómo se determina que dos reportes hablan del mismo problema (ver D006 en decisiones.md).

### Registro de reportes

**RF-10:** El usuario puede enviar un reporte sobre un problema o modificación que afecte el servicio de una línea.

**RF-11:** El usuario puede indicar a qué línea corresponde el reporte.

**RF-12:** El usuario puede describir el problema observado y aportar información que ayude a identificarlo.

**RF-13:** El sistema debe registrar la fecha y hora en que se recibe cada reporte.

**RF-14:** El sistema debe distinguir los reportes enviados por pasajeros de las modificaciones confirmadas mediante fuentes oficiales.

**RF-21:** El usuario puede consultar los reportes recientes enviados por pasajeros sobre una línea, junto con su fecha y estado (flujo rápido).

**RF-23:** El sistema debe dejar de mostrar en el historial los reportes crudos con más de un mes de antigüedad (ver D007 en decisiones.md).

*Pendiente de definir:* determinar qué tipos de reportes se podrán enviar, qué información será obligatoria y si se permitirá adjuntar imágenes o ubicaciones. También, si los reportes vencidos desaparecen del todo o quedan archivados de forma no visible.

### Gestión administrativa

**RF-15:** Un administrador puede consultar los reportes recibidos.

**RF-16:** Un administrador puede revisar un reporte y decidir si corresponde aceptarlo, rechazarlo o dejarlo pendiente.

**RF-17:** Un administrador puede registrar modificaciones en los recorridos de las líneas.

**RF-18:** Un administrador puede registrar desvíos temporales y paradas inhabilitadas.

**RF-19:** Un administrador puede establecer la vigencia de una modificación.

**RF-20:** El sistema debe permitir identificar el origen de la información utilizada para registrar una modificación.

*Pendiente de definir:* establecer qué acciones administrativas estarán disponibles y cómo se identificarán los administradores.

---

## 2. Requisitos no funcionales (RFN)

Describen las condiciones de funcionamiento y las características de calidad que debe cumplir el sistema.

### Actualización y confiabilidad de la información

**RFN-01:** El sistema debe mostrar cuándo fue actualizada por última vez la información de una línea o modificación.

**RFN-03:** El sistema no debe presentar un reporte de un pasajero como una modificación confirmada sin una revisión previa.

### Usabilidad

**RFN-05:** Las funcionalidades principales deben poder utilizarse desde un dispositivo móvil.

**RFN-06:** El usuario debe poder consultar la información principal de una línea con pocos pasos, teniendo en cuenta que puede encontrarse esperando en una parada.

**RFN-07:** El formulario para enviar un reporte debe ser breve y permitir completar la operación sin pasos innecesarios.

### Disponibilidad y conectividad

**RFN-08:** El sistema debe informar al usuario cuando no pueda obtener información actualizada.

**RFN-09:** El sistema debe evitar presentar información almacenada anteriormente como si fuera información actualizada.

*Pendiente de definir:* determinar si el MVP funcionará exclusivamente con conexión a Internet o si permitirá consultar información previamente almacenada cuando no haya conexión.

### Seguridad y privacidad

**RFN-10:** Las funciones administrativas deben estar restringidas a usuarios autorizados.

**RFN-11:** El sistema debe proteger la información que permita identificar a los usuarios que envían reportes.

*Pendiente de definir:* determinar si los reportes serán anónimos, si requerirán una cuenta y qué datos personales será necesario almacenar.

### Rendimiento

**RFN-12:** Las consultas principales deben responder en un tiempo que permita utilizar la aplicación de manera práctica mientras el usuario espera el colectivo.

*Pendiente de definir:* establecer tiempos máximos aceptables para cargar una línea, consultar sus paradas y enviar un reporte.

---

## 3. Riesgos

Se identifican situaciones que podrían impedir el desarrollo del MVP o afectar su funcionamiento.

| Riesgo | Impacto | Mitigación |
|---|---|---|
| Las fuentes oficiales se encuentran suspendidas o contienen información desactualizada. | No sería posible ofrecer recorridos y modificaciones confiables. | Investigar fuentes alternativas, comprobar periódicamente su disponibilidad y registrar la fecha y procedencia de los datos. |
| No está completamente definida la jurisdicción que cubrirá el primer MVP. | Podrían seleccionarse líneas o fuentes de datos que no correspondan al alcance inicial. | Definir las líneas de prueba y verificar a qué jurisdicción pertenece cada una antes de integrarlas. |
| Dependencia de una sola persona para revisar los reportes. | La moderación podría acumular demoras o interrumpirse si esa persona no está disponible. | Mantener un procedimiento de moderación sencillo y evaluar la posibilidad de incorporar otros administradores. |
| La compilación y ejecución de la aplicación en dispositivos móviles no están validadas. | Podrían aparecer problemas técnicos al distribuir o utilizar la aplicación. | Realizar pruebas de compilación e instalación en dispositivos reales antes de avanzar con funcionalidades más complejas. |
| Hay pocos testers durante las primeras pruebas. | Los errores y problemas de usabilidad podrían pasar inadvertidos. | Comenzar con un grupo reducido, recopilar devoluciones y ampliar las pruebas progresivamente. |
| La información disponible no permite reconstruir correctamente todos los recorridos. | Algunas líneas podrían mostrarse incompletas o con paradas incorrectas. | Verificar los datos antes de publicarlos y limitar inicialmente la cantidad de líneas disponibles. |
| Los reportes de pasajeros contienen información incorrecta o engañosa. | Los usuarios podrían recibir información equivocada sobre el servicio. | Mantener la revisión manual y diferenciar los reportes pendientes de las modificaciones confirmadas. |
| Una modificación temporal no tiene una fecha de finalización conocida. | El sistema podría mostrar un desvío vencido o mantenerlo activo más tiempo del necesario. | Definir un procedimiento para revisar las modificaciones sin fecha de finalización y evitar asumir que siguen vigentes indefinidamente. |

---

## 4. Cuestiones pendientes de definición

Los siguientes puntos requieren decisiones antes de cerrar los requisitos del MVP:

- Seleccionar las líneas que estarán disponibles durante las primeras pruebas.
- Confirmar la jurisdicción y las fuentes de datos correspondientes a esas líneas.
- Definir qué información se mostrará en el detalle de una línea y de una parada.
- Determinar los tipos de reportes que podrán enviar los pasajeros.
- Definir si los usuarios necesitarán una cuenta para enviar reportes.
- Establecer cómo se identificarán los administradores.
- Definir qué sucede con las modificaciones cuya vigencia es desconocida.
- Establecer los tiempos máximos de respuesta aceptables.
- Decidir si se permitirá consultar información sin conexión.
- Definir si la planificación de viajes A→B forma parte del MVP o de una etapa posterior (ver D009 en decisiones.md). Es la decisión de alcance que queda abierta y condiciona el tamaño total de la primera versión.

---

## 5. Criterio de evolución

Estos requisitos corresponden exclusivamente al MVP. No representan necesariamente el alcance definitivo de BondiMap.

A medida que se realicen pruebas y se obtenga experiencia de uso, los requisitos podrán modificarse, dividirse o reemplazarse.

Las funcionalidades que se incorporen en etapas posteriores deberán documentarse sin ampliar artificialmente el alcance de la primera versión.
