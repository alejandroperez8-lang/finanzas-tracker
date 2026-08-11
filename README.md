# Finanzas Tracker — PWA

Aplicación web de finanzas personales preparada para GitHub Pages.

## Estructura

- `index.html` — aplicación
- `manifest.json` — configuración PWA
- `service-worker.js` — caché/offline
- `icons/` — iconos 192x192 y 512x512

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub.
2. Sube todos los archivos de esta carpeta a la raíz del repositorio.
3. Ve a **Settings → Pages**.
4. En **Build and deployment**, selecciona **Deploy from a branch**.
5. Selecciona la rama `main` y la carpeta `/ (root)`.
6. Guarda y espera el despliegue.
7. Abre la URL HTTPS que te entregue GitHub Pages.

## Instalación en Android

Abre la URL con Chrome/Edge. Cuando el navegador reconozca la PWA aparecerá la opción de instalarla. También puedes usar el menú del navegador y seleccionar **Instalar app**.

## Importante sobre los datos

La aplicación original utiliza `window.storage` para persistencia. Ese mecanismo pertenece al entorno donde fue creada y **no es una API estándar de navegador**. Antes de usar GitHub Pages como versión definitiva, conviene migrar la persistencia a `localStorage` o, mejor aún, a `IndexedDB`.

El Service Worker permite cachear la aplicación y abrirla sin conexión, pero no sustituye el sistema de almacenamiento de datos.

## Actualizaciones

Cuando cambies archivos estáticos, incrementa `CACHE_NAME` en `service-worker.js`, por ejemplo de `v1` a `v2`, para forzar una nueva caché.
