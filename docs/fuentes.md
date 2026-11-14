# Inventario de fuentes de información — BondiMap

Este documento registra las fuentes de información identificadas para el desarrollo de BondiMap.

El objetivo es conocer qué información ofrece cada fuente, cuáles son sus limitaciones, qué condiciones de uso tiene y qué tan adecuada resulta para alimentar la aplicación.

El inventario debe mantenerse actualizado a medida que se investiguen nuevas fuentes, se realicen pruebas de integración y se compruebe la calidad de los datos.

**Criterio de evaluación:** encontrar una fuente de información no significa que sus datos sean necesariamente confiables, estén actualizados o puedan utilizarse directamente en producción.

---

## 1. Fuentes oficiales

### 1.1. Buenos Aires Data — GTFS de colectivos de CABA

**Fuente:** [Colectivos: GTFS — Buenos Aires Data](https://data.buenosaires.gob.ar/dataset/colectivos-gtfs)

**Organismo:** Gobierno de la Ciudad Autónoma de Buenos Aires.

**Información ofrecida:**

- Información geográfica de los recorridos.
- Líneas y servicios de colectivos.
- Paradas.
- Información estática del transporte público.
- Cronogramas de servicio.

**Formato:** GTFS estático.

**Licencia:** CC-BY-2.5-AR.

**Frecuencia de actualización declarada:** cada dos años.

**Estado y limitaciones:**

El portal informa que los datasets publicados en formato API y GTFS se encuentran suspendidos, en revisión y corrección. Se comunicará su reanudación cuando vuelvan a estar operativos.

La frecuencia de actualización declarada es insuficiente para garantizar que los recorridos y horarios representen las condiciones actuales del servicio.

**Evaluación para BondiMap:**

Puede servir como referencia para investigar la estructura de los datos de transporte y, si vuelve a estar disponible, como fuente inicial de información estática.

No debe considerarse una fuente confiable de recorridos actuales sin comprobar previamente la fecha y consistencia de sus datos.

**Estado de verificación:** identificado. Disponibilidad operativa pendiente de comprobación.

### 1.2. API Transporte — GCBA

**Fuente:** [API Transporte — Buenos Aires Ciudad](https://buenosaires.gob.ar/movilidad-e-infraestructura/movilidad/api-transporte)

**Documentación:** [Documentación técnica de la API](https://datosabiertos-apis.buenosaires.gob.ar/BA_Root/Documentacion?schema_name=Transporte_3)

**Información ofrecida:**

- Posiciones de vehículos.
- Información GTFS estática y dinámica.
- Alertas del servicio.
- Información de colectivos, subtes y trenes.
- Información relacionada con el tránsito y cortes de calles.

**Formatos:** JSON y XML.

**Acceso:**

La API Transporte tradicional utiliza credenciales de acceso (`client_id` y `client_secret`), que se solicitan mediante un formulario de registro.

Formulario: [Registro API Transporte](https://api-transporte.buenosaires.gob.ar/registro).

El registro permite declarar el proyecto y el uso previsto. La gratuidad de las credenciales y las condiciones actuales de acceso deben confirmarse antes de integrarla.

**Advertencias oficiales:**

El GCBA informa que la versión disponible puede contener información desactualizada o imprecisiones.

También comunica que se encuentra trabajando en una nueva versión, denominada API Transporte 2.0, que busca ofrecer información más precisa y actualizada en tiempo real.

**Verificación:** el 14 de noviembre de 2026 se comprobó que la página institucional responde y reproduce ambas advertencias, y que el formulario de registro de credenciales está operativo.

**Evaluación para BondiMap:**

Es una fuente especialmente interesante por la disponibilidad de posiciones de colectivos y otros datos dinámicos.

Sin embargo, las advertencias oficiales impiden asumir que toda la información proporcionada sea correcta o esté actualizada.

Es necesario realizar pruebas reales, evaluar los distintos endpoints y contrastar los resultados con otras fuentes.

**Estado de verificación:** documentación identificada. Funcionamiento actual de los endpoints y acceso efectivo pendientes de prueba.

**Nota:** no confundir la API Transporte tradicional, que requiere credenciales, con la API pública del catálogo BA Data, que permite consultar metadatos y recursos abiertos sin autenticación.

### 1.3. Datos abiertos de la Secretaría de Transporte — Nación

**Fuente:** [Portal de Datos Abiertos de Transporte](https://datos.transporte.gob.ar/)

**Información identificada:**

- Líneas y empresas de transporte de la Región Metropolitana de Buenos Aires.
- Información agrupada por jurisdicción nacional, provincial y municipal.
- Datos estadísticos relacionados con el transporte.
- Información sobre empresas y servicios.

**Formatos identificados:** principalmente CSV y otros recursos descargables.

**Licencias:** dependen de cada conjunto de datos. Algunos datasets identificados utilizan Creative Commons Attribution 4.0.

**Limitaciones:**

Durante la investigación no se confirmó la disponibilidad de un feed nacional GTFS completo y actualizado de colectivos.

El portal sí ofrece información sobre líneas y empresas, pero eso no equivale a disponer de recorridos geográficos, paradas y horarios actualizados.

**Evaluación para BondiMap:**

Es una fuente complementaria para identificar líneas, empresas y jurisdicciones.

No debe asumirse que proporciona todos los datos necesarios para reconstruir los recorridos de los colectivos.

**Estado de verificación:** portal y datasets identificados. GTFS nacional de colectivos no confirmado.

---

## 2. Fuentes geográficas y estándares

### 2.1. OpenStreetMap

**Fuente:** [OpenStreetMap](https://www.openstreetmap.org/)

**Información ofrecida:**

- Calles y avenidas.
- Caminos y accesos.
- Puntos de interés.
- Paradas de transporte.
- Relaciones y recorridos de transporte público, cuando fueron incorporados por los colaboradores.

**Licencia:** Open Data Commons Open Database License (ODbL).

**Consideraciones legales:**

La licencia ODbL permite utilizar, modificar y distribuir los datos, pero establece obligaciones de atribución y, cuando corresponde, de compartir bases de datos derivadas bajo la misma licencia.

Es importante estudiar las condiciones de uso antes de combinar datos de OpenStreetMap con otras fuentes o distribuir bases de datos derivadas.

La obligación de compartir bajo ODbL no significa automáticamente que toda aplicación que utilice mapas de OpenStreetMap deba publicar su código fuente.

**Calidad y limitaciones:**

La información es mantenida colaborativamente, por lo que su cobertura y nivel de detalle pueden variar según la zona.

Existen datos de transporte público y recorridos de colectivos, pero no se debe asumir que todas las líneas estén representadas ni que la información esté actualizada.

**Evaluación para BondiMap:**

Es una alternativa interesante para la representación cartográfica y como fuente complementaria de información geográfica.

Los recorridos y paradas deberán contrastarse con otras fuentes antes de utilizarlos como información confiable para los pasajeros.

**Estado de verificación:** fuente y licencia identificadas. Cobertura y calidad de las líneas objetivo pendientes de evaluación.

### 2.2. GTFS — General Transit Feed Specification

**Fuente:** [GTFS.org](https://gtfs.org/)

**Tipo:** estándar de datos, no proveedor de información.

GTFS define una estructura común para representar información de transporte público y facilitar su intercambio entre organismos y aplicaciones.

Se divide principalmente en dos componentes:

**GTFS Schedule (estático):**

- Agencias.
- Líneas.
- Recorridos.
- Paradas.
- Horarios.
- Calendarios de servicio.

**GTFS Realtime (dinámico):**

- Posiciones de vehículos.
- Actualizaciones de viajes.
- Demoras y cancelaciones.
- Alertas del servicio.
- Modificaciones temporales.

**Evaluación para BondiMap:**

Es un estándar importante para organizar e intercambiar información de transporte.

Sin embargo, GTFS no proporciona datos por sí mismo. Es necesario encontrar organismos o proveedores que publiquen feeds compatibles.

**Estado de verificación:** estándar y documentación oficial identificados.

---

## 3. Proyectos y referencias existentes

Los siguientes proyectos sirven como referencias para investigar soluciones similares y aprender de sus decisiones técnicas.

No deben considerarse automáticamente fuentes de datos reutilizables ni proveedores oficiales.

### 3.1. Bondi Sonoro

**Referencia:** proyecto Bondi Sonoro.

**Interés para BondiMap:**

Se identifica como una referencia relacionada con la consulta de posiciones en vivo de colectivos.

Puede resultar útil para investigar cómo se presentan las posiciones de vehículos y qué posibilidades existen para obtener información dinámica.

**Pendiente de investigación:**

- Identificar y verificar su fuente de datos.
- Determinar si utiliza información oficial o fuentes alternativas.
- Investigar qué información ofrece además de las posiciones.
- Evaluar si existe documentación o información técnica pública.

**Estado de verificación:** referencia pendiente de investigación técnica.

### 3.2. tango.blue

**Fuente:** [How this map is made — tango.blue](https://tango.blue/en/map/about/)

**Descripción:**

Proyecto que presenta información del transporte público de Buenos Aires mediante posiciones de colectivos, recorridos, paradas y otras capas geográficas.

**Fuentes que declara utilizar:**

- API Transporte del GCBA para posiciones de vehículos.
- Dataset metropolitano del Ministerio de Transporte, edición de abril de 2023, para geometrías de recorridos.
- Registro de paradas de la Ciudad.
- OpenStreetMap para el mapa base.

**Lección técnica importante:**

El proyecto explica que los nombres de servicio proporcionados por la API no siempre coinciden con la realidad y que los horarios estáticos disponibles estaban desactualizados.

Por ese motivo, decidió confiar principalmente en tres elementos de la información dinámica:

- Posición del vehículo.
- Headsign (destino o dirección informada).
- Service ID (identificador del servicio).

El resto de la información se reconstruye mediante el procesamiento de las posiciones y su comparación con otras geometrías.

**Evaluación para BondiMap:**

Esta experiencia demuestra que disponer de una fuente oficial no garantiza que todos sus campos sean confiables.

También muestra que es posible utilizar datos dinámicos como evidencia para reconstruir o contrastar información estática.

**Lección incorporada al proyecto:**

No depender ciegamente de una única fuente, incluso cuando sea oficial. Evaluar la calidad de cada campo por separado, contrastar información y mantener registro del origen de los datos.

**Estado de verificación:** metodología documentada públicamente por el propio proyecto.

---

## 4. Conclusiones preliminares

La investigación inicial permite identificar algunas limitaciones importantes:

1. No se confirmó la disponibilidad de un GTFS nacional completo y actualizado de colectivos.
2. El GTFS de colectivos de CABA declara una frecuencia de actualización de dos años y actualmente presenta un aviso de suspensión.
3. La API Transporte del GCBA ofrece información dinámica interesante, pero advierte oficialmente sobre posibles imprecisiones.
4. OpenStreetMap puede complementar la información geográfica, aunque su cobertura y calidad deben comprobarse por zona.
5. Los proyectos existentes muestran que es necesario contrastar y validar los datos, incluso cuando provienen de fuentes oficiales.

Por lo tanto, BondiMap no debería depender de una única fuente para construir su información.

La estrategia deberá contemplar la combinación de fuentes oficiales, información geográfica y, en etapas posteriores, reportes colaborativos validados.

