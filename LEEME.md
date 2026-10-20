# RobloRun: web app instalable

RobloRun es una web app instalable (PWA). Se instala desde el navegador en Android y en iPhone/iPad, queda con su ícono en la pantalla de inicio, abre a pantalla completa y funciona sin internet después de la primera vez.

## Archivos

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | El juego completo |
| `manifest.webmanifest` | Nombre, ícono, colores y modo pantalla completa de la app |
| `sw.js` | Guarda el juego en el teléfono para jugar sin conexión |
| `icon-*.png`, `maskable-512.png`, `apple-touch-icon.png`, `favicon-32.png` | Íconos de la app (Android, iPhone y pestaña del navegador) |

## 1. Publicarlo en internet (obligatorio para instalar)

Los teléfonos solo instalan web apps que se abren desde una dirección `https://`. Si abres `index.html` con doble clic, el juego funciona, pero no se puede instalar. Cualquiera de estas opciones gratuitas sirve.

**Netlify Drop (la más fácil, sin cuenta técnica)**
1. Entra a https://app.netlify.com/drop
2. Arrastra la carpeta `RobloRun` completa a la página.
3. Te da una dirección tipo `https://nombre-al-azar.netlify.app`. Ábrela en el celular.

**GitHub Pages**
1. Crea un repositorio y sube el contenido de esta carpeta (que `index.html` quede en la raíz).
2. En el repositorio: Settings → Pages → Branch: `main` → carpeta `/ (root)` → Save.
3. La dirección será `https://tu-usuario.github.io/nombre-del-repo/`.

## 2. Instalarlo en el celular

**Android (Chrome)**
- En el menú del juego aparece el botón **Instalar en este dispositivo**. Tócalo y confirma.
- Si no aparece: menú ⋮ de Chrome → **Instalar app** (o **Agregar a pantalla principal**).

**iPhone / iPad (Safari)**
- Abre la dirección en **Safari** (en iPhone, Chrome no instala web apps).
- Toca el botón **Compartir** (cuadrado con flecha) → **Agregar a pantalla de inicio** → **Agregar**.

El juego se ve mejor con el teléfono **horizontal**. En Android la app instalada se gira sola. En iPhone hay que tener desactivado el bloqueo de rotación.

## 3. Probarlo en la computadora

Para probar la instalación en tu PC sin publicarlo, abre una terminal en esta carpeta y ejecuta:

```
npx serve .
```

Luego abre `http://localhost:3000` en Chrome o Edge. En la barra de direcciones aparece el ícono de **Instalar**.

## 4. Publicar una actualización

Si cambias `index.html`, sube los archivos de nuevo. Los teléfonos reciben la versión nueva la próxima vez que abren el juego con internet. Si cambias los íconos u otros archivos, cambia también la línea `const VERSION = 'roblorun-v1'` de `sw.js` (por ejemplo a `roblorun-v2`) para que se renueve la copia guardada.

## Controles

| Acción | Teclado | Celular |
| --- | --- | --- |
| Cambiar de carril | ← → | Deslizar a izquierda o derecha |
| Saltar | ↑ o Espacio | Deslizar hacia arriba o tocar |
| Agacharse | ↓ | Deslizar hacia abajo |
| Pausa | P | Botón de pausa |

Los récords y las monedas se guardan en cada teléfono.

## Publicarlo en Google Play o App Store (opcional)

La web app ya se instala sin pasar por las tiendas. Si más adelante quieres que aparezca en Google Play, la herramienta gratuita PWABuilder (https://www.pwabuilder.com) arma el paquete para Android a partir de la dirección publicada. También genera un proyecto para iOS, pero ese hay que compilarlo en una Mac con Xcode y publicarlo con una cuenta de Apple Developer.
