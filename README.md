# ASTR4 · Music Academy

Aplicación web progresiva (PWA) en castellano para estudiar teoría musical, piano y producción. Está construida con HTML, CSS y JavaScript sin dependencias externas de ejecución.

## Contenido incluido

- Ruta de teoría musical y piano: 500 lecciones organizadas en 25 unidades de 20 lecciones.
- Ruta de producción musical: 500 lecciones organizadas en 25 unidades de 20 lecciones.
- Biblioteca de apuntes visuales y diccionario musical.
- Laboratorio de acordes, escalas, progresiones y teclado con sonido generado por Web Audio.
- Entrenamiento auditivo básico de intervalos.
- Herramientas: metrónomo, afinador mediante micrófono y generador de archivo MIDI de acordes.
- Cuaderno personal, favoritos, seguimiento y copia de seguridad/restauración JSON.
- Recursos originales del usuario conservados en `assets/originales/`: 5 PDF, 11 HTML y 52 archivos MIDI.
- PWA y caché offline para los archivos de la aplicación que se hayan descargado.

## Ejecutar localmente

No hace falta instalar paquetes. Abre una terminal en la carpeta y ejecuta un servidor estático, por ejemplo:

```bash
python -m http.server 8000
```

Después abre `http://localhost:8000`. Para probar PWA, service worker, micrófono e instalación se necesita `localhost` o un sitio HTTPS.

## Publicar gratis en GitHub Pages

1. Crea un repositorio público en GitHub, por ejemplo `ASTR4`.
2. Descomprime este ZIP y sube **el contenido** de la carpeta `ASTR4` a la raíz del repositorio (deben quedar `index.html`, `app.js`, `styles.css`, etc. en la raíz).
3. En GitHub, abre **Settings → Pages**.
4. En **Build and deployment**, elige **Deploy from a branch**.
5. Selecciona la rama `main` y la carpeta `/ (root)`, y guarda.
6. Espera a que GitHub Pages publique la dirección que aparece en esa misma pantalla.

La aplicación utiliza rutas relativas, por lo que funciona también en un repositorio de proyecto, no solo en el dominio raíz.

## Instalar en iPhone

1. Publica primero la aplicación en GitHub Pages y abre su dirección HTTPS en Safari.
2. Pulsa el botón **Compartir**.
3. Selecciona **Añadir a pantalla de inicio**.
4. Confirma el nombre ASTR4 y pulsa **Añadir**.

La orientación vertical se prioriza en el diseño y se muestra un aviso si la pantalla está en horizontal. iOS no garantiza el bloqueo físico de orientación para todas las PWAs.

## Datos y copias de seguridad

El progreso, favoritos y notas personales se guardan en `localStorage` del navegador. Permanecen tras cerrar y volver a abrir la app en el mismo navegador, pero no se sincronizan entre dispositivos y pueden perderse si se borran los datos del sitio, se cambia de navegador o se restablece el dispositivo.

En **Progreso → Exportar copia** se descarga un archivo JSON. Para recuperar los datos, usa **Restaurar copia** y selecciona ese archivo. Haz copias periódicas y antes de limpiar datos del navegador. No elimines los datos del sitio si no tienes una copia reciente.

Los archivos originales están empaquetados dentro de la aplicación. La caché offline guarda la app y los recursos a medida que se visitan/descargan; no se fuerza la descarga automática de todos los PDF/HTML/MIDI para evitar consumo de datos y espacio.

## Limitaciones conocidas

- Cada academia contiene exactamente 500 fichas didácticas. Las primeras 20 de cada ruta proceden de la edición inicial; las 480 restantes se organizan en 24 unidades adicionales con objetivos, explicaciones, ejemplos de aplicación y ejercicios específicos por tema. Las fichas ampliadas son lecciones introductorias de práctica guiada; conviene enriquecer progresivamente los temas avanzados con ejemplos sonoros y ejercicios evaluables adicionales.
- El entrenamiento auditivo inicial evalúa cuatro intervalos; se puede ampliar a más intervalos y tipos de reconocimiento.
- El afinador necesita permiso de micrófono y HTTPS/localhost. La detección es orientativa y puede verse afectada por ruido o acordes simultáneos.
- El sonido del piano y de los ejercicios se sintetiza con Web Audio; no es una librería de piano acústico.
- La sincronización entre dispositivos requeriría un servicio externo/backend, que no se incluye.
- GitHub Pages sirve archivos estáticos; no ofrece cuentas, sincronización ni notificaciones push de servidor por sí solo.

## Estructura

- `index.html`: punto de entrada.
- `styles.css`: diseño responsive vertical.
- `data.js`: primeras lecciones, apuntes y glosario.
- `curriculum.js`: ampliación curricular hasta 500 lecciones en cada academia.
- `app.js`: navegación, herramientas, sonido y almacenamiento.
- `manifest.webmanifest` y `sw.js`: PWA y funcionamiento offline.
- `assets/originales/`: materiales de la carpeta fuente.


## Actualización visual ASTR4
- Identidad futurista negra y violeta basada en la onda de partículas suministrada.
- 999 lecciones por academia (1.998 en total), con buscador y progreso.
- Biblioteca de apuntes con enlaces directos a los cinco PDF originales.
- Apartado independiente de actividades que abre las herramientas HTML originales.
- Piano adaptable al ancho móvil y audio activado mediante eventos táctiles compatibles con Safari/Web Audio.
- Navegación de seis secciones y ajustes de áreas seguras de iOS.


## Actividades interactivas (actualización)
Las diez actividades se abren dentro de ASTR4 mediante un visor integrado. También tienen un enlace «Abrir aparte». El service worker precarga las diez páginas y ya no sustituye errores de recursos por index.html. Si se publica una actualización, la caché cambia a `astr4-v5-activity-launcher`.


## ASTR4 ULTIMATE — espacio de artista-productor
- Nuevo apartado «Mi estudio» para organizar canciones con nombre, estilo, ambiente, tonalidad, BPM y notas.
- Rutina diaria con seguimiento de piano, oído, composición, producción y escucha crítica.
- Registro local de minutos de práctica y sesiones.
- Guía de flujo de trabajo en Ableton Live y ruta de aprendizaje hasta publicar música.
- Los nuevos datos se guardan en `astr4-data`, ampliando el esquema sin borrar progreso, favoritos ni notas existentes.
- Los datos permanecen en el navegador/dispositivo; no hay sincronización automática entre dispositivos.


## Actualización mayor v8 — Suite creativa

- Cuaderno creativo para registrar canciones, letras, conceptos, estructuras, tonalidad, BPM, estilo, estado y notas de producción.
- Planificador semanal con bloques de piano, oído, composición, Ableton y escucha crítica.
- Retos creativos con seguimiento local para convertir el estudio en loops, letras, arreglos y demos terminadas.
- Accesos directos desde inicio y navegación inferior a Mi estudio y planificación.
- Los datos se guardan localmente en el navegador y se incluyen en las copias de seguridad ASTR4.
- Caché de PWA actualizada a astr4-major-v8 para forzar la renovación de archivos en GitHub Pages.

## ASTR4 v9 — Sala de producción

Se incorpora una Sala de producción con cinco etapas de control: preproducción, grabación vocal, mezcla, entrega y lanzamiento. Incluye listas de comprobación persistentes, selector de procesos para una cadena vocal orientativa, bitácora de decisiones de mezcla, ficha de lanzamiento y exportación de un informe `.txt`. Los nuevos datos se guardan en `astr4-data` y se incluyen en la copia JSON general.

La cadena vocal es una guía de trabajo, no una receta universal. El orden y los procesos deben decidirse escuchando la toma y el contexto de la canción. Las recomendaciones de entrega evitan imponer un único objetivo de sonoridad válido para todas las plataformas.
