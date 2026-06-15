# FisioAI Atlas 3D

Visor anatómico 3D interactivo con modelos clínicos de hombro y cintura escapular, miembro inferior, y tórax/abdomen. Construido con Three.js y modelos GLB con compresión Draco.

## Requisitos

- Navegador moderno (Chrome, Firefox, Edge, Safari)
- Conexión a internet (para cargar Three.js, los decodificadores Draco y las fuentes desde CDN)
- Un servidor HTTP local (ver abajo)

> **Por qué hace falta un servidor local:** los navegadores bloquean la carga de archivos `.glb` desde el sistema de archivos directamente (`file://`) por política de seguridad (CORS). Abrir `viewer.html` haciendo doble clic no funcionará; los modelos 3D no cargarán.

## Archivos

```
viewer.html                    ← aplicación principal
upper-limb.glb                 ← modelo de hombro y miembro superior
lower-limb.glb                 ← modelo de miembro inferior
muscles-thorax-abdomen.glb     ← modelo de tórax y abdomen
overview-skull.glb             ← modelo de la pantalla de inicio
```

## Cómo abrirlo

Elige una de las siguientes opciones según lo que tengas instalado.

### Opción A — Python (sin instalar nada extra)

Abre una terminal en la carpeta del proyecto y ejecuta:

```bash
# Python 3
python -m http.server 8000

# Python 2 (si no tienes Python 3)
python -m SimpleHTTPServer 8000
```

Luego abre en el navegador: `http://localhost:8000/viewer.html`

### Opción B — VS Code con Live Server

1. Instala la extensión **Live Server** (ritwickdey.LiveServer) desde el marketplace de VS Code.
2. Abre la carpeta del proyecto en VS Code.
3. Haz clic derecho sobre `viewer.html` → **Open with Live Server**.
4. El navegador se abrirá automáticamente.

### Opción C — Node.js

```bash
npx serve .
```

Luego abre la URL que aparezca en la terminal (normalmente `http://localhost:3000`) y navega a `viewer.html`.

---

## Controles del visor

| Acción | Ratón |
|---|---|
| Rotar | Clic izquierdo + arrastrar |
| Zoom | Rueda del ratón |
| Desplazar | Clic derecho + arrastrar |
| Seleccionar estructura | Clic sobre el modelo |

## Regiones disponibles

- **Hombro y cintura escapular** — articulaciones, músculos, ligamentos, nervios y vasos del hombro
- **Miembro inferior** — estructuras de la rodilla y pierna
- **Tórax y abdomen** — musculatura del tronco

Cambia de región con el selector en la pantalla de inicio o desde el menú desplegable de regiones.
