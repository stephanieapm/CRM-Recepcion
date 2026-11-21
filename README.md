# Tareas de Representantes de Operaciones

Herramienta para que el equipo de recepción de The Smile Mission organice y siga sus tareas diarias: tablero por persona, tablero del equipo agrupado por rol, panel con indicadores, plantillas de asignación por hora, catálogo de tareas con su paso a paso y automatizaciones.

Todas las horas están en hora de Miami.

## Archivos

| Archivo | Qué es |
| --- | --- |
| `index.html` | Versión autónoma. Se abre con doble clic o se publica en GitHub Pages. Trae las plantillas y el catálogo adentro y guarda lo que se marca en el navegador (`localStorage`). |
| `claude-artifact/index.html` | Versión que corre como artifact de Claude, con base de datos compartida entre el equipo. Solo funciona publicada en Claude: abierta fuera de ahí muestra "Abrí la herramienta desde su enlace". |
| `data/datos-iniciales.json` | Las plantillas (Actual y Propuesta), el catálogo de tareas y la configuración, en formato legible. Es la misma información que trae `index.html`. |

## Usar la versión autónoma

1. Abrí `index.html` en el navegador.
2. Elegí tu nombre en "Recepcionista".
3. Marcá el estado de cada tarea, la cantidad y una nota.

Lo que se marca queda guardado solo en ese navegador: otra persona, u otra computadora, empieza de cero. El botón **Restablecer datos** borra lo marcado y vuelve a los datos iniciales.

## Publicar en GitHub Pages

1. Subí el repositorio a GitHub.
2. En el repositorio, entrá a **Settings → Pages**.
3. En "Build and deployment", elegí **Deploy from a branch**, la rama `main` y la carpeta `/ (root)`.
4. Guardá. En unos minutos la herramienta queda en `https://<tu-usuario>.github.io/<nombre-del-repo>/`.

Aunque esté publicada, cada persona sigue guardando en su propio navegador. Para que el equipo comparta los datos hay que usar la versión de Claude o conectarla a una base compartida (por ejemplo, Google Sheets con Apps Script).

## Cambiar las plantillas o las tareas

- **Desde la herramienta:** pestaña **Plantilla** para asignar tareas por hora y persona, y pestaña **Tareas** para crear tareas nuevas. Los cambios quedan en el navegador.
- **Para todos los que abran el archivo:** editá los datos que están en la constante `seed`, dentro del primer `<script>` de `index.html`, o reemplazala con el contenido de `data/datos-iniciales.json`. Si cambiás los datos iniciales, cambiá también la clave `tareas-recepcion-local-v1` (por ejemplo, a `-v2`) para que los navegadores carguen los datos nuevos.

## Importante

- No cargar datos de pacientes (nombres, teléfonos, fechas de nacimiento ni tratamientos) en las notas.
- Los links a los manuales apuntan a archivos de Google Drive: solo los ve quien tenga acceso a esos archivos.
