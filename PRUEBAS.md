# Informe de comprobaciones de ASTR4

Fecha: 22 de noviembre de 2026

## Comprobado

- Sintaxis JavaScript de `app.js`, `data.js`, `curriculum.js` y `sw.js` mediante `node --check`: correcta.
- Existencia de los archivos de entrada, estilos, datos, manifiesto, service worker e iconos: correcta.
- Inventario de materiales originales: 5 PDF, 11 HTML y 52 MIDI; todos están presentes.
- Índice MIDI: 52 entradas y ninguna ruta apunta a un archivo inexistente.
- Servidor HTTP local: los archivos principales responden correctamente.
- Enlaces con espacios y caracteres acentuados en los recursos originales: verificados mediante URL codificada.

## No comprobado en esta ejecución

- No se completó una prueba automatizada de interacción en navegador real. El proceso Chromium headless del entorno no llegó a arrancar de forma estable.
- No se ha probado la instalación final en un iPhone físico ni la publicación efectiva en una cuenta de GitHub.
- No se ha comprobado la entrada de micrófono en un dispositivo real; el afinador requiere HTTPS/localhost y permiso del usuario.
- La reproducción Web Audio y la importación de copias de seguridad están implementadas, pero deben probarse en Safari/iOS y Chrome/Android después de publicar.

Por tanto, no se afirma que se hayan validado todos los comportamientos en dispositivos físicos. Las comprobaciones anteriores son las que sí se han realizado.


## Ampliación a 500 lecciones por academia

- Teoría musical y piano: 500 lecciones (20 iniciales + 480 ampliadas).
- Producción musical: 500 lecciones (20 iniciales + 480 ampliadas).
- Organización: 25 unidades de 20 lecciones por academia.
- Conteo ejecutado sobre los datos cargados: 500 elementos en cada ruta y 20 elementos en cada una de las 25 unidades.
- Navegación: unidades desplegables y buscador de lecciones.
- IDs originales p0–p19 y m0–m19 conservados para no perder el progreso anterior.
