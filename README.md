# Tuppers del mes

App instalable con las cenas del mes, la compra y el congelador, día a día.

- **Instalarla en el iPhone:** abre la web en Safari › Compartir › «Añadir a pantalla de inicio».
- **Sin conexión:** funciona igual; lo que marques se sube al volver la conexión.
- **Sincronización:** lo que marcas (tareas, compra y sesión) se guarda en Supabase con un código propio de cada instalación. Para ver lo mismo en otro dispositivo, abre la nube de la cabecera › «Copiar enlace» y ábrelo allí.

## Cómo está hecha

- `index.html`: toda la app (datos del mes, pantallas y estilos).
- `sw.js`: copia para usarla sin conexión. Al cambiar algo importante, sube `VERSION`.
- `manifest.webmanifest` e `icons/`: nombre, icono y modo a pantalla completa.
- Supabase, proyecto «Plan nutricional»: tabla `progreso` sin acceso directo; solo se lee y escribe con las funciones `leer_progreso` y `guardar_progreso`, que exigen el código.

## Cambiar de mes

Los datos del mes están al principio del `<script>` de `index.html`: `PLATOS`, `PLAN`, `CANT`, el congelador (`bolsa(...)`), `SESION`, `EXTRA`, `COMPRAS`, `TICKET` y el año y mes (`Y`, `M`). Al empezar un mes nuevo cambia también `KEY` para que las marcas empiecen de cero.
