# Registro de decisiones - BondiMap

Este documento registra las decisiones técnicas y de producto tomadas durante el desarrollo de BondiMap.

Su objetivo es mantener un historial de las decisiones importantes, explicar los motivos detrás de cada una y facilitar su revisión cuando cambien las necesidades del proyecto.

Las decisiones no deben eliminarse cuando dejan de estar vigentes. En esos casos, se debe registrar una nueva decisión que indique cuál reemplaza y por qué.

## Formato de registro 

Cada decisión debe incluir:

- **Fecha:** día en que se tomó la decisión (indicada en el encabezado de la sección).
- **Decisión:** qué se resolvió.
- **Motivo:** por qué se tomó esa decisión.
- **Consecuencia:** qué implica para el proyecto.
- **Estado:** vigente, reemplazada o descartada.

#### Copy~Paste

### D___ | _____

- **Estado:** 
- **Decisión:**
- **Motivo:**
- **Consecuencia:**

## 2026-11-14 | Día 1

### D001 | Desarrollo progresivo 

- **Estado:** vigente.
- **Decisión:** desarrollar BondiMap por etapas, comenzando con un Producto Mínimo Viable (MVP).
- **Motivo:** el proyecto contempla funcionalidades y desafíos que requieren investigación y desarrollo. Intentar implementar todo desde el comienzo aumentaría la complejidad y dificultaría validar si la solución realmente resuelve el problema.
- **Consecuencia:** priorizar las funcionalidades esenciales y postergar las características complementarias para futuras etapas.

### D002 | Expansión geográfica

- **Estado:** vigente 
- **Decisión:** organizar la expansión del proyecto en tres etapas: pruebas con testers, cobertura del AMBA y posterior expansión a la provincia de Buenos Aires. 
- **Motivo:** ampliar la cobertura requiere incorporar y mantener información de una cantidad creciente de líneas, recorridos y paradas.
- **Consecuencia:** la cobertura inicial será limitada y crecerá progresivamente según la disponibilidad y confiabilidad de los datos.

### D003 | OpenStreetMap como alternativa cartográfica inicial

- **Estado:** vigente 
- **Decisión:** considerar OpenStreetMap como fuente inicial de información geográfica y cartográfica.
- **Motivo:** ofrece información geográfica abierta que puede servir como base para representar recorridos y ubicaciones.
- **Consecuencia:** investigar los servicios disponibles, sus condiciones de uso y las alternativas de integración antes de implementar la funcionalidad de mapas.

### D004 | Diferenciación entre información oficial y colaborativa

- **Estado:** vigente
- **Decisión:** distinguir explícitamente la información proveniente de fuentes oficiales de aquella aportada por los pasajeros.
- **Motivo:** un reporte realizado por un usuario no garantiza que la información sea correcta. Mezclar ambas fuentes podría generar confusión y afectar la confiabilidad de la aplicación.
- **Consecuencia:** registrar el origen y el estado de validación de la información. Los reportes no verificados no deberán presentarse como información oficial.

### D005 | Moderación manual al inicio

- **Estado:** vigente.
- **Decisión:** la moderación de reportes será manual (creador) al inicio, con evolución posterior hacia reglas comunitarias y, solo si existen datos suficientes, técnicas automáticas.
- **Motivo:** sin volumen de reportes ni ejemplos clasificados no hay base para automatizar. La moderación manual permite definir primero las reglas que realmente importan.
- **Consecuencia:** el creador es el único moderador al principio; este cuello de botella debe revisarse cuando crezca la cantidad de reportes.

### D006 | Umbral de alerta temprana

- **Estado:** vigente (simplificación inicial).
- **Decisión:** dos reportes de usuarios distintos, sobre la misma línea y el mismo día, del mismo problema, activan una alerta.
- **Motivo:** la corroboración independiente aporta más confianza que un solo reporte.
- **Consecuencia:** queda pendiente definir cómo se determina que dos reportes hablan del "mismo problema" y manejar la frontera de día (reportes cerca de medianoche). Reevaluar cuando haya más usuarios.

### D007 | Ciclo de vida de los reportes

- **Estado:** vigente.
- **Decisión:** el historial de reportes crudos tendrá una antigüedad máxima de un mes; los estados verificados (cambio confirmado) no expiran con el reporte.
- **Motivo:** un reporte crudo pierde relevancia con el tiempo, pero un cambio verificado sigue vigente hasta que una nueva evidencia lo modifique.
- **Consecuencia:** el diseño de datos debe distinguir entre reporte (temporal) y estado verificado (persistente).

### D008 | Datos de prueba

- **Estado:** vigente.
- **Decisión:** durante el desarrollo se usarán datos falsos o de prueba; nunca se mostrarán a usuarios finales como información real.
- **Motivo:** permite construir la lógica de la aplicación sin depender de fuentes externas aún no verificadas.
- **Consecuencia:** antes de cada entrega a testers deberá comprobarse que los datos reales estén disponibles y sustituidos.

### D009 | Núcleo del producto: red de recorridos

- **Estado:** vigente.
- **Decisión:** la red de recorridos (líneas, recorridos, paradas) es el cimiento del producto; la planificación de viajes A→B se construye sobre esa red.
- **Motivo:** tanto la consulta de línea como la planificación A→B requieren tener la red modelada; construir primero la red evita retrabajo.
- **Consecuencia:** el orden de desarrollo prioriza el modelado de la red; la fecha de incorporación de A→B al producto queda pendiente de definir (ver alcance.md).

### D010 | Framework de interfaz: Flet como candidato principal

- **Estado:** evaluado, decisión final pendiente en la etapa técnica.
- **Decisión:** Flet es el candidato principal para la interfaz móvil; la confirmación se hará con una prueba de concepto antes de comprometerse.
- **Motivo:** permite desarrollar en Python para múltiples plataformas sin aprender Dart ni JavaScript. Contras a verificar: tamaño del paquete, dependencia del SDK de Flutter para compilar y cambios de API entre versiones.
- **Consecuencia:** antes de construir pantallas reales, validar que el entorno de compilación funcione en la máquina de desarrollo.


