# Sorteos al azar

Aplicación web para hacer sorteos: lanzamiento de monedas (águila o sol), dados, reparto de elementos en partes iguales, selección de ganadores, formación de equipos, números aleatorios, orden aleatorio e intercambio (amigo secreto).

- Funciona en cualquier navegador, en computadora o celular.
- Se puede instalar como aplicación y usar sin conexión.
- Los resultados usan `crypto.getRandomValues`, el generador aleatorio criptográfico del navegador.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La aplicación completa (HTML, CSS y JavaScript). |
| `manifest.webmanifest` | Nombre, colores e íconos que usa el sistema al instalarla. |
| `sw.js` | *Service worker*: guarda los archivos para que funcione sin conexión. |
| `icons/` | Íconos de la aplicación. |
| `.nojekyll` | Indica a GitHub Pages que publique los archivos tal cual. |

## Publicar en GitHub Pages

1. En GitHub, crea un repositorio nuevo **público** (por ejemplo `sorteos`).
2. Sube todos los archivos de esta carpeta respetando la carpeta `icons/`:
   - Desde la web: **Add file → Upload files**, arrastra el contenido de la carpeta y confirma con **Commit changes**.
   - Desde la terminal:
     ```bash
     git init
     git add .
     git commit -m "Primera versión"
     git branch -M main
     git remote add origin https://github.com/USUARIO/sorteos.git
     git push -u origin main
     ```
3. En el repositorio: **Settings → Pages**. En *Source* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)` y guarda.
4. En uno o dos minutos la aplicación queda en `https://USUARIO.github.io/sorteos/`.

## Instalar en un dispositivo

Abre la dirección de GitHub Pages y:

- **Chrome o Edge (Windows, Mac, Linux, Android):** usa el botón **Instalar** que aparece al final de la página, o el ícono de instalación en la barra de direcciones.
- **iPhone o iPad (Safari):** toca **Compartir → Agregar a pantalla de inicio**.

Una vez abierta por primera vez, funciona sin internet.

## Actualizar la aplicación

1. Modifica `index.html` (o el archivo que corresponda).
2. En `sw.js`, cambia la versión, por ejemplo de `sorteos-v1` a `sorteos-v2`.
3. Sube los cambios. Los dispositivos que la tengan instalada reciben la versión nueva la siguiente vez que la abran con conexión.

## Probar en la computadora sin publicar

El *service worker* no funciona si abres `index.html` con doble clic. Para probarlo completo, levanta un servidor local en la carpeta:

```bash
python -m http.server 8000
```

y abre `http://localhost:8000`.
