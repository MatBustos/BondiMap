# Alcance

## Objetivo general

Desarrollar una aplicación móvil que permita a los pasajeros consultar información actualizada sobre los recorridos y el estado del servicio de colectivos, con especial atención a las modificaciones que puedan afectar sus viajes habituales, además de mostrar al usuario un conjunto de caminos posibles desde un punto a otro.

BondiMap busca centralizar información sobre recorridos, paradas, desvíos e interrupciones del servicio, para que los pasajeros puedan anticiparse a los cambios y tomar mejores decisiones al momento de viajar.

A largo plazo, el proyecto busca convertirse en una herramienta colaborativa de información sobre el transporte público, combinando fuentes oficiales con reportes de los propios pasajeros, diferenciando claramente el origen y el nivel de confiabilidad de cada dato.

## Problema que busca resolver

Los pasajeros de colectivos necesitan información confiable y actualizada para planificar sus viajes. Sin embargo, los recorridos pueden verse afectados por modificaciones permanentes o situaciones temporales, como:

- Cortes de calles.
- Obras viales.
- Accidentes.
- Desvíos temporales.
- Paradas momentáneamente inhabilitadas.
- Interrupciones o alteraciones del servicio.

Los servicios de mapas y otras herramientas de consulta pueden no reflejar estos cambios con la rapidez necesaria. Como consecuencia, un pasajero puede dirigirse a una parada por la que el colectivo ya no circula o desconocer que su recorrido habitual está afectado.

El problema no se limita a conocer el recorrido habitual de una línea, sino también a saber cuándo ese recorrido deja de cumplirse y qué alternativas existen.

BondiMap busca reducir esa incertidumbre mediante información accesible, contextualizada y actualizada.

## Usuarios destinatarios

### Pasajeros

Son los usuarios principales de la aplicación. Utilizan el transporte público de colectivos y necesitan consultar información para organizar sus desplazamientos.

Sus necesidades principales son:

- Conocer el mejor recorrido.
- Conocer modificaciones en el servicio.
- Identificar desvíos e interrupciones.
- Recibir alertas sobre las líneas que utilizan habitualmente.
- Consultar alternativas cuando un recorrido se encuentra afectado.

### Pasajeros colaboradores

Son usuarios que, además de consultar información, contribuyen comunicando situaciones que afectan al servicio.

Podrán informar, por ejemplo:

- Una parada que se encuentra inhabilitada.
- Un desvío que no aparece registrado.
- Una interrupción del servicio.
- Una modificación observada en el recorrido.

Los reportes colaborativos deberán contar con mecanismos de validación y niveles de confiabilidad. No se considerarán información oficial por el solo hecho de haber sido publicados por un usuario.

El proceso de reportes distingue dos flujos:

- **Flujo rápido:** los reportes se muestran de inmediato a la comunidad con su fecha y su estado, para que cada pasajero saque sus propias conclusiones sin esperar verificación.
- **Flujo lento:** cuando los reportes se acumulan y coinciden, la información pasa por verificación antes de incorporarse como recorrido vigente del sistema.

### Administradores y moderadores (Por ahora solo el creador)

Son responsables de gestionar la información de la plataforma y supervisar los reportes realizados por los pasajeros.

Entre sus responsabilidades se encuentran:

- Gestionar líneas, recorridos y paradas.
- Registrar o actualizar modificaciones del servicio.
- Revisar reportes colaborativos.
- Validar, rechazar o marcar información como no verificada.
- Gestionar alertas y su vigencia.

## Alcance del MVP (versión inicial)

El MVP (Producto Mínimo Viable) será la primera versión funcional de BondiMap y corresponde a la Etapa 1 descripta más abajo.

Su propósito no será ofrecer cobertura completa del transporte público, sino comprobar que la aplicación puede resolver el problema central: permitir que un pasajero consulte un recorrido y conozca las modificaciones que pueden afectar su viaje.

Se propone incluir:

- Consulta de un conjunto reducido de líneas.
- Visualización de recorridos y paradas.
- Registro y consulta de modificaciones permanentes.
- Registro y consulta de desvíos temporales.
- Identificación de paradas inhabilitadas.
- Visualización de alertas asociadas a una línea.
- Gestión inicial de la información mediante un mecanismo administrativo controlado.

El alcance geográfico inicial será reducido y estará determinado por las líneas seleccionadas para las pruebas.

La incorporación de funcionalidades adicionales dependerá de los resultados obtenidos durante esta primera etapa.

## Alcance por etapas

El desarrollo y la disponibilidad de BondiMap se realizarán de manera progresiva. Cada etapa permitirá validar el funcionamiento de la aplicación antes de ampliar su cobertura geográfica y funcional.

### Etapa 1 — Pruebas con usuarios seleccionados

Objetivo: validar el funcionamiento general de la aplicación con un grupo reducido de testers.

El objetivo de esta etapa es comprobar que las funcionalidades principales resuelvan necesidades reales antes de realizar un lanzamiento más amplio.

Alcance previsto:

- Consulta de líneas seleccionadas.
- Visualización de recorridos y paradas.
- Consulta de modificaciones y desvíos registrados.
- Identificación de paradas inhabilitadas.
- Visualización de alertas relacionadas con las líneas disponibles.
- Pruebas de usabilidad y recolección de comentarios.

La cobertura geográfica y la cantidad de líneas serán limitadas. Se priorizará la calidad y consistencia de la información por encima de la cantidad de servicios incorporados.

Los testers permitirán identificar errores, dificultades de uso y necesidades que no hayan sido contempladas durante el análisis inicial.

### Próximas etapas — Expansión de la aplicación

Objetivo: ampliar la disponibilidad de BondiMap y comenzar a ofrecer cobertura a pasajeros de la República Argentina

Alcance previsto:

- Incorporación progresiva de nuevas líneas.
- Ampliación de recorridos y paradas disponibles.
- Mayor cobertura de modificaciones permanentes y desvíos temporales.
- Incorporación progresiva de líneas favoritas.
- Notificaciones sobre novedades que afecten a las líneas seleccionadas.
- Evaluación e incorporación de reportes colaborativos.
- Mejora de los mecanismos de validación y confiabilidad de la información.

La expansión se realizará progresivamente, priorizando la disponibilidad y calidad de los datos. La incorporación de una zona o línea no implicará necesariamente que toda la información de esa zona esté cubierta.

## Criterios generales de alcance y crecimiento

El crecimiento de BondiMap estará guiado por los siguientes criterios:

1. Calidad antes que cantidad: es preferible ofrecer información confiable de pocas líneas que información incompleta de muchas.
2. Expansión progresiva: la cobertura geográfica aumentará a medida que existan datos y recursos para mantenerla.
3. Transparencia de la información: se deberá distinguir entre información oficial, información verificada y reportes pendientes de validación.
4. Vigencia de los datos: las modificaciones temporales deberán contar con fecha de registro y criterios para determinar cuándo dejan de estar vigentes.
5. Validación antes de automatización: los mecanismos automáticos se incorporarán cuando exista una base suficiente para garantizar resultados confiables.
6. Evolución según necesidades reales: las nuevas funcionalidades se priorizarán a partir de pruebas y comentarios de los usuarios.

## Consideraciones y restricciones

El funcionamiento de BondiMap dependerá de la disponibilidad, calidad y actualización de las fuentes de información sobre el transporte público.

La existencia de estándares como GTFS y GTFS Realtime no garantiza que todas las líneas o jurisdicciones publiquen datos completos y actualizados.

Por este motivo, será necesario investigar las fuentes disponibles, evaluar sus limitaciones y definir mecanismos alternativos de carga y actualización de información cuando corresponda.

La cobertura anunciada por la aplicación deberá reflejar únicamente los servicios para los que exista información suficiente.

## Funcionalidades fuera del MVP

- ✗ Integración con sistemas de pago o carga de tarjetas SUBE.
- ✗ Compra de pasajes o gestión de pagos.
- ✗ Chat entre pasajeros.
- ✗ Perfiles sociales o funcionalidades comunitarias que no estén relacionadas directamente con el servicio.
- ✗ Paneles estadísticos avanzados.
- ✗ Aplicación para empresas de transporte o gestión de flotas.
- ✗ Moderación automatizada con machine learning (ver D005 en [decisiones.md](decisiones.md)).
- ✗ Foro o red social para la comunidad (forma pendiente de definir).

## Estado del documento

Este documento representa una primera definición del alcance de BondiMap.

Las funcionalidades, etapas y prioridades podrán modificarse a medida que avance el análisis, se investiguen las fuentes de información y se realicen las primeras pruebas con usuarios.
