# ASTR4 — actualización de espaciado y apuntes visuales

## Cambios realizados
- Se corrigió la separación entre el panel principal y el encabezado «Explora ASTR4» mediante márgenes específicos para el bloque de cabecera.
- Se convirtió la biblioteca de apuntes en tarjetas visuales con esquemas para notas cromáticas, fórmulas de tríadas, acordes diatónicos, progresiones, funciones armónicas, compás, acordes de séptima y flujo de producción.
- Se redujo la densidad de texto en las tarjetas y se separaron visualmente los consejos.
- Se mejoró la presentación de los cinco documentos PDF originales con tarjetas de acceso directo.
- Se ajustaron las cuadrículas y el tamaño de los elementos para móvil y escritorio.
- Se mantuvieron el currículo, las funciones existentes, los archivos MIDI y los recursos originales.

## Comprobaciones realizadas
- `node --check app.js`: correcto.
- `node --check data.js`: correcto.
- `node --check curriculum.js`: correcto.
- Recuento de contenido base: 500 lecciones en cada academia; la aplicación añade 499 fichas adicionales por academia, para un total previsto de 999 por academia.
- Se comprobaron los cinco PDF enlazados y la existencia de sus archivos locales.
- Se comprobó la integridad del ZIP generado.

## Limitaciones de las pruebas
- No se pudo completar una captura automatizada de Chromium en este entorno.
- No se ha probado en un iPhone físico ni en Safari real.
- El aspecto final puede variar ligeramente según el navegador, las fuentes disponibles y el tamaño de pantalla.


## Corrección de actividades (v3)
- Se corrigieron las rutas de las diez actividades: antes apuntaban a una carpeta con nombre codificado incorrectamente en el ZIP (Pr├íctica), por lo que GitHub Pages no encontraba los archivos.
- Ahora se sirven desde `assets/originales/actividades/` con nombres ASCII estables.
- Se actualizó la versión de caché del service worker a `astr4-v3`.
- Se validó que las diez rutas referenciadas existen y que los scripts JavaScript embebidos pasan `node --check`.


## Actualización mayor v8
- Nuevas vistas: `cancionero`, `planificador` y `retos`.
- Nuevos datos persistentes: canciones, planificación semanal y retos completados.
- Los formularios, cambios de estado y casillas están conectados al almacenamiento local.
- Caché de service worker: `astr4-major-v8`.
- Pendiente de validación visual en Safari/iPhone real.
