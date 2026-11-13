<div align="center">

# 🎄 Árbol de Navidad 3D

### *Miles de partículas de luz, un solo archivo HTML*

<br>

![Three.js](https://img.shields.io/badge/Three.js-r160-000000?style=for-the-badge&logo=threedotjs&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES_Modules-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![WebGL](https://img.shields.io/badge/WebGL-Shaders_GLSL-990000?style=for-the-badge&logo=webgl&logoColor=white)
![Web Audio](https://img.shields.io/badge/Web_Audio-Música_sintetizada-8A2BE2?style=for-the-badge)

<br>

**Un árbol navideño interactivo en 3D** con luces que bailan al ritmo de la música,
fuegos artificiales, aurora boreal, nieve que se acumula y un trineo cruzando el cielo.

<br>

[✨ Características](#-características) ·
[🎮 Controles](#-controles) ·
[🚀 Cómo usarlo](#-cómo-usarlo) ·
[🎨 Personalizar](#-personalizar) ·
[🛠️ Cómo funciona](#️-cómo-funciona)

</div>

---

## ✨ Características

<table>
<tr>
<td width="50%" valign="top">

### 🌟 El árbol
- **~16 000 partículas** que forman las ramas en 7 pisos
- **Guirnaldas** de luces en doble espiral con brillo real (bloom)
- **Esferas metálicas** con reflejos del entorno
- **Estrella dorada** giratoria con halo de luz
- **Efecto armar / dispersar**: el árbol explota en una nube y se vuelve a formar

</td>
<td width="50%" valign="top">

### 🎆 La escena
- **Aurora boreal** animada con shaders
- **Fuegos artificiales** de 4 tipos con sonido
- **Trineo con renos** que cruza el cielo dejando estela
- **Paisaje**: pinos nevados, cabaña iluminada, faroles y muñeco de nieve
- **Nieve que se acumula** en el suelo, los regalos y las puntas del árbol

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 💫 Interacción
- **Toca una esfera** → rebota, suelta chispas y muestra un mensaje navideño
- **Pide un deseo** → sube como una luz y orbita el árbol
- **Decora tú mismo** → 9 adornos con vista previa antes de colgarlos
- **Música** → *Jingle Bells* sintetizada; las luces laten con cada nota

</td>
<td width="50%" valign="top">

### 🎨 Personalización
- **4 temas**: Clásico, Invierno, Elegante y 🇬🇹 Guatemala
- **3 formas**: Clásico, Espiral y Solo luces (con transición animada)
- **Dedicatoria con enlace**: *"Feliz Navidad, Andrea"* + mensaje
- **Modo cine** para proyectar en pantalla
- **Desenfoque tipo foto** (bokeh) y **calidad automática** según los FPS

</td>
</tr>
</table>

---

## 🎮 Controles

| Acción | Cómo |
|:--|:--|
| 🔄 Girar la cámara | Arrastrar con el mouse o el dedo |
| 🔍 Acercar / alejar | Rueda del mouse o pellizcar |
| 💥 Armar / dispersar | Botón **Dispersar** |
| 💡 Estilo de luces | Botón **Luces** → Cálidas · Multicolor · Secuencia |
| 🎵 Música | Botón **Música** |
| 🎆 Fuegos artificiales | Botón **Fuegos** |
| 🌠 Pedir un deseo | Botón **Deseo** (escribe y presiona *Enter*) |
| 🎀 Decorar | Botón **Decorar** → elige un adorno → toca el árbol |
| 🎁 Dedicatoria | Ícono de regalo (arriba a la derecha) |
| 🎬 Modo cine | Ícono de pantalla (arriba a la derecha) |
| ⚙️ Ajustes | Ícono de controles (arriba a la derecha) |
| ⎋ Salir de cualquier modo | Tecla **Esc** |

> 💡 **Tip:** en Nochebuena (desde las 8 p. m.) y el 25 de diciembre, los fuegos artificiales se lanzan solos. 🎇

---

## 🚀 Cómo usarlo

El proyecto es **un solo archivo**: `arbol-navidad.html`. No necesita instalar nada.

> ⚠️ Usa un **servidor local**. Si abres el archivo con doble clic, el navegador bloquea los módulos ES de Three.js.

**Con Python**
```bash
python -m http.server 8000
```

**Con Node.js**
```bash
npx serve .
```

**Con VS Code**
Instala la extensión *Live Server* → clic derecho en el archivo → **Open with Live Server**.

Luego abre 👉 `http://localhost:8000/arbol-navidad.html`

### 🌐 Publicarlo en GitHub Pages

1. Renombra el archivo a `index.html`
2. Súbelo a un repositorio
3. Ve a **Settings → Pages → Branch: main** → *Save*
4. Listo: `https://<tu-usuario>.github.io/<tu-repo>/`

### 📋 Requisitos

- Navegador moderno con **WebGL**: Chrome, Edge, Firefox o Safari
- Conexión a internet (Three.js, Tailwind y las fuentes se cargan por CDN)
- ❌ No funciona en **Internet Explorer** ni en Edge con **modo IE**

---

## 🎨 Personalizar

Todo se ajusta desde el bloque `CONFIGURACIÓN` al inicio del `<script type="module">`.

### 🌲 Tamaño del árbol
```js
const H = 8;        // altura del follaje
const R = 3.2;      // radio de la base
const TIERS = 7;    // pisos de ramas
```

### ✨ Cantidad de partículas
```js
const MAX = { foliage: 16000, garland: 760, ornaments: 130, snow: 3000, ... };
```

### 🎨 Crear tu propio tema
Agrega una entrada al objeto `THEMES` y aparecerá sola en el panel de ajustes:
```js
navidadNeon: {
  name: 'Neón', swatch: ['#ff00aa', '#00e5ff', '#7cff00'],
  dark: '#0b2a1a', light: '#2fd47a', sparkle: '#ff9ef0', warm: '#ffb3f0',
  lights: ['#ff00aa', '#00e5ff', '#7cff00', '#ffe600'],
  orn: ['#ff00aa', '#00e5ff', '#7cff00', '#ffffff'], star: '#ff66cc'
}
```

### 💌 Mensajes de las esferas
Edita el arreglo `BLESSINGS` con tus propias frases.

### 🔗 Enlace de la dedicatoria
Si lo publicas en tu propio sitio, cambia esta línea por tu dirección:
```js
const ARTIFACT_URL = 'https://tu-sitio.com/arbol-navidad.html';
```

---

## 🛠️ Cómo funciona

<details>
<summary><b>🌲 Árbol de partículas con morphing</b></summary>
<br>

Cada partícula guarda **cuatro posiciones**: cono, espiral, solo luces y una posición dispersa en el aire. El *vertex shader* mezcla entre ellas con los uniforms `uW` (forma) y `uMix` (armado). Así el cambio de forma corre completo en la GPU, sin tocar los buffers.

</details>

<details>
<summary><b>💡 Brillo, bokeh y postprocesado</b></summary>
<br>

- `UnrealBloomPass` hace brillar todo lo que pasa de cierto umbral (luces, estrella y ventanas)
- El desenfoque se calcula **por partícula**: según la distancia al foco crece el tamaño del punto y baja su opacidad, como el bokeh de una cámara real
- Tone mapping **ACES Filmic** para un color cinematográfico

</details>

<details>
<summary><b>🎵 Música sincronizada</b></summary>
<br>

*Jingle Bells* (dominio público, 1857) se sintetiza con **Web Audio API**: melodía con timbre de campana, bajo y cascabeles. Cada nota guarda su momento exacto, y el bucle de animación lo compara con `audioContext.currentTime` para disparar un pulso de luz.

</details>

<details>
<summary><b>🎆 Fuegos artificiales y estelas</b></summary>
<br>

Un único buffer de **8 000 partículas** funciona como anillo circular: cohetes, explosiones, chispas de las esferas, estela del trineo y de los deseos. Cada partícula tiene su propia velocidad, gravedad, fricción y vida.

</details>

<details>
<summary><b>❄️ Nieve que se acumula</b></summary>
<br>

Una textura de ruido sirve como `alphaMap` y su `alphaTest` baja poco a poco. Por eso la nieve aparece **en manchas** que crecen hasta cubrir el suelo. Las puntas del árbol y los regalos también se blanquean con el tiempo.

</details>

<details>
<summary><b>⚡ Calidad automática</b></summary>
<br>

Cada 2 segundos se miden los FPS. Si bajan de 38, se reduce la resolución y la cantidad de partículas (`setDrawRange`). Si se mantienen arriba de 57, se vuelve a subir.

</details>

<details>
<summary><b>💾 Qué se guarda y dónde</b></summary>
<br>

| Dato | Dónde |
|:--|:--|
| Adornos colocados | `localStorage` (solo en tu navegador) |
| Deseos | `localStorage` (solo en tu navegador) |
| Dedicatoria, tema y forma | En el enlace: `#d-<tema><forma>-<nombre>-<mensaje>` (en hexadecimal) |

</details>

---

## 🧰 Tecnologías

| | |
|:--|:--|
| **Three.js r160** | Escena 3D, OrbitControls, EffectComposer, UnrealBloomPass |
| **GLSL** | Shaders propios: follaje, guirnaldas, nieve, aurora y partículas |
| **Tailwind CSS** | Interfaz con efecto de vidrio esmerilado |
| **Web Audio API** | Música y efectos de sonido sin archivos de audio |
| **Google Fonts** | *Great Vibes* para el título, *Inter* para la interfaz |

---

<div align="center">

### 🎅 Hecho con cariño para esta Navidad

**Gerson Batún** · [@GersonCode-prog](https://github.com/GersonCode-prog)

<br>

*Si te gustó, deja una ⭐ en el repo*

<br>

🎄 ✨ 🎁 ✨ 🎄

</div>
