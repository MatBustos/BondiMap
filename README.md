# BondiMap

**Chiflame cuando te bajes.**

## Descripción

BondiMap es un proyecto personal que busca desarrollar una aplicación móvil para consultar información actualizada sobre el transporte público de colectivos en Argentina.

La idea principal es ayudar a los pasajeros a mantenerse informados sobre los recorridos habituales de las líneas, sus modificaciones permanentes y los desvíos temporales ocasionados por cortes de calles, obras, accidentes u otras situaciones.

El objetivo de la aplicación es mantener al usuario alertado ante posibles cambios de recorrido de una línea y ofrecer un conjunto de caminos posibles cuando quiere viajar del punto A al punto B.

Actualmente, los servicios de mapas pueden presentar información desactualizada cuando una línea modifica su recorrido o se ve afectada por un inconveniente temporal. Esto puede provocar que los pasajeros esperen en paradas donde el colectivo ya no circula.

BondiMap busca centralizar esta información y ofrecer herramientas para que los usuarios puedan anticiparse a estos cambios.

> **Aviso sobre los datos:** durante el desarrollo se utilizarán datos de prueba que no representan información oficial. Ninguna información será presentada a usuarios finales sin verificar su fuente.

## Objetivos

- Consultar recorridos y paradas de las líneas de colectivos.
- Informar sobre modificaciones permanentes y desvíos temporales.
- Notificar interrupciones del servicio, cortes de calles y paradas inhabilitadas.
- Permitir que los usuarios guarden sus líneas favoritas.
- Ofrecer alertas y noticias relacionadas con las líneas seleccionadas.
- Facilitar la consulta de alternativas de viaje.
- Incorporar un sistema colaborativo para que los pasajeros puedan informar inconvenientes y compartir novedades.
- Mostrar un conjunto de los mejores caminos posibles desde un punto a otro.

Esta lista representa el alcance completo a largo plazo. El alcance de la primera versión (MVP) está definido en [docs/alcance.md](docs/alcance.md).

## Funcionalidades previstas

| Funcionalidad | Descripción |
|---|---|
| Consulta de líneas | Visualizar información de las líneas de colectivos disponibles. |
| Recorridos | Consultar los recorridos habituales y sus respectivas paradas. |
| Modificaciones | Informar cambios permanentes en los recorridos. |
| Desvíos temporales | Mostrar modificaciones ocasionadas por cortes, obras o accidentes. |
| Paradas inhabilitadas | Informar cuando una parada deja de estar disponible temporalmente. |
| Líneas favoritas | Permitir que cada usuario guarde las líneas que utiliza habitualmente. |
| Notificaciones | Enviar alertas sobre cambios e inconvenientes en las líneas favoritas. |
| Noticias | Consultar novedades relacionadas con el servicio y las líneas. |
| Reportes colaborativos | Permitir que los pasajeros informen situaciones que afecten al servicio. |
| Alternativas de viaje | Facilitar la búsqueda de otras opciones cuando un recorrido se encuentra afectado. |

Las funcionalidades mencionadas forman parte de la planificación inicial y pueden modificarse a medida que avance el desarrollo.

## Tecnologías previstas

| Tecnología | Uso |
|---|---|
| Python | Lenguaje principal del proyecto. |
| Flet | Desarrollo de la interfaz de la aplicación móvil. |
| FastAPI | Desarrollo del backend y la API. |
| SQLite | Base de datos inicial. |
| PostgreSQL | Posible motor de base de datos para futuras etapas. |
| OpenStreetMap | Información geográfica y mapas. |
| GTFS | Estándar para representar información del transporte público. |
| Git y GitHub | Control de versiones y alojamiento del proyecto. |

Estas tecnologías son una selección inicial y podrán modificarse según las necesidades y limitaciones que surjan durante el desarrollo.

## Arquitectura prevista

La aplicación se plantea inicialmente con una arquitectura cliente-servidor, separando la interfaz móvil de la lógica de negocio y el almacenamiento de datos.

                 BondiMap
                     |
          +----------+----------+
          |                     |
     Aplicación móvil       Backend
         (Flet)            (FastAPI)
                                |
                     +----------+----------+
                     |                     |
                 Base de datos       Fuentes externas
                 (SQLite)             (GTFS / OSM)

## Estado actual

El proyecto se encuentra en fase de análisis y diseño: se continúan definiendo los requisitos y funcionalidades, y aún no se ha desarrollado código.

## Documentación

- [docs/alcance.md](docs/alcance.md) — objetivo general, problema, usuarios, alcance por etapas y MVP.
- [docs/decisiones.md](docs/decisiones.md) — registro de decisiones técnicas y de producto.
- [docs/fuentes.md](docs/fuentes.md) — inventario de fuentes de información y sus limitaciones.
- [docs/mockups/](docs/mockups/) — referencias visuales de pantallas.

## Distribución prevista

Al ser una aplicación móvil, el objetivo es publicarla en Google Play y App Store, ya que Flet permite compilar para ambas plataformas.

