# Calculadora de Liquidaciones - Aceites Tapia
## Guía de instalación y despliegue

---

## ¿Qué contiene este paquete?

```
liquidaciones-pwa/
├── index.html          ← La aplicación completa (HTML + CSS + JS en un solo archivo)
├── manifest.json       ← Configuración PWA (nombre, iconos, colores)
├── sw.js               ← Service Worker (permite funcionar sin conexión)
├── icons/
│   ├── icon-192x192.png
│   ├── icon-512x512.png
│   └── apple-touch-icon.png
└── INSTRUCCIONES.md    ← Este archivo
```

---

## OPCIÓN A: Subir a GitHub Pages (GRATIS, recomendado)

### Paso 1: Crear cuenta en GitHub
1. Ve a **https://github.com** y crea una cuenta gratuita (si no tienes una).
2. Confirma tu email.

### Paso 2: Crear un repositorio
1. Una vez dentro, pulsa el botón verde **"New"** (o ve a https://github.com/new).
2. Nombre del repositorio: `calculadora-liquidaciones`
3. Marca **"Public"**.
4. **NO** marques "Add a README file".
5. Pulsa **"Create repository"**.

### Paso 3: Subir los archivos
1. En la página del repositorio vacío, verás un enlace que dice **"uploading an existing file"**. Púlsalo.
2. Arrastra TODOS los archivos y la carpeta `icons/` de este paquete.
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icons/icon-192x192.png`
   - `icons/icon-512x512.png`
   - `icons/apple-touch-icon.png`
3. Pulsa **"Commit changes"**.

### Paso 4: Activar GitHub Pages
1. Ve a **Settings** (pestaña en tu repositorio).
2. En el menú lateral izquierdo, busca **"Pages"**.
3. En "Source", selecciona **"Deploy from a branch"**.
4. En "Branch", selecciona **"main"** y carpeta **"/ (root)"**.
5. Pulsa **"Save"**.
6. Espera 1-2 minutos. Tu app estará disponible en:

```
https://TU-USUARIO.github.io/calculadora-liquidaciones/
```

### Paso 5: ¡Listo!
Comparte esa URL con quien quieras. Al abrir el enlace en el móvil, podrán
pulsar "Añadir a pantalla de inicio" y tener la app como una aplicación nativa.

---

## OPCIÓN B: Subir a vuestro dominio (aceitestapia.com)

Si preferís que la app esté en vuestro propio dominio, por ejemplo:
`https://www.aceitestapia.com/calculadora/`

### Paso 1: Acceder al hosting
Accede al panel de control de vuestro hosting web (donde tenéis alojada la web de aceitestapia.com).
Esto suele ser cPanel, Plesk, o un acceso FTP.

### Paso 2: Crear la carpeta
1. Dentro del directorio público (normalmente `public_html` o `www`), crea una carpeta llamada `calculadora`.
2. Sube dentro de esa carpeta TODOS los archivos de este paquete, manteniendo la estructura:
   ```
   public_html/
   └── calculadora/
       ├── index.html
       ├── manifest.json
       ├── sw.js
       └── icons/
           ├── icon-192x192.png
           ├── icon-512x512.png
           └── apple-touch-icon.png
   ```

### Paso 3: Verificar
Accede a `https://www.aceitestapia.com/calculadora/` desde el navegador.

### IMPORTANTE: HTTPS
La PWA **requiere HTTPS** (conexión segura) para funcionar correctamente.
La mayoría de hostings ya incluyen certificado SSL gratuito con Let's Encrypt.
Si tu web no tiene HTTPS, contacta con tu proveedor de hosting para activarlo.

---

## Cómo instalar la app en el móvil

### En Android (Chrome):
1. Abre la URL de la calculadora en Chrome.
2. Chrome mostrará automáticamente un banner de "Añadir a pantalla de inicio".
   - Si no aparece: pulsa los **tres puntos** (⋮) arriba a la derecha → **"Añadir a pantalla de inicio"** o **"Instalar aplicación"**.
3. Confirma y ya tendrás el icono en tu teléfono.

### En iPhone (Safari):
1. Abre la URL de la calculadora en **Safari** (obligatorio, no funciona desde Chrome en iOS).
2. Pulsa el botón de **compartir** (□↑) en la barra inferior.
3. Desplázate hacia abajo y pulsa **"Añadir a pantalla de inicio"**.
4. Confirma el nombre y pulsa **"Añadir"**.

---

## Configuración del PIN de administrador

El PIN por defecto es **1993**. Para cambiarlo, abre el archivo `index.html` con
cualquier editor de texto (Bloc de notas, TextEdit, etc.) y busca esta línea:

```javascript
const ADMIN_PIN = '1993';
```

Cámbiala por el PIN que prefieras, por ejemplo:

```javascript
const ADMIN_PIN = '7742';
```

Guarda el archivo y vuelve a subirlo.

---

## Actualizar la aplicación

Si en el futuro necesitas actualizar la calculadora:

1. Modifica los archivos necesarios.
2. En el archivo `sw.js`, cambia la versión del caché:
   ```javascript
   const CACHE_NAME = 'liquidaciones-v2';  // Cambia v1 por v2, v3, etc.
   ```
3. Sube los archivos actualizados.
4. Los usuarios verán la nueva versión la próxima vez que abran la app con conexión a internet.

---

## Notas técnicas

- **Sin conexión**: Una vez instalada, la app funciona completamente offline.
- **Almacenamiento**: Los parámetros de administrador (maquila y descuento) se guardan
  en el almacenamiento local del navegador de cada dispositivo.
- **Compatibilidad**: Funciona en cualquier navegador moderno (Chrome, Safari, Firefox, Edge).
- **Sin dependencias**: No usa React, Angular, ni ningún framework. Es HTML + CSS + JavaScript puro.
  Eso la hace ligera (~15KB total), rápida y sin necesidad de compilación.

---

*Aceites Tapia · Villanueva de Tapia · desde 1993*
