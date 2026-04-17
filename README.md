# 🌊 Botella al Mar - Widgets para ArcGIS Experience Builder

Colección de componentes web personalizados diseñados para integrarse en ArcGIS Experience Builder, parte del proyecto interactivo "Botella al Mar".

---

## 📋 Contenido del Proyecto

### 🎵 Componentes de Audio

#### `alas.html`
Widget de reproductor de audio con controles personalizados.
- **Canción**: "Menos Dos Alas" (menosdosalas.mp3)
- **Características**:
  - Botón de replay personalizado con icono turquesa
  - Controles nativos del navegador con estilo transparente
  - Reproducción en loop automático
  - Diseño responsive adaptable a Experience Builder

#### `audio2.html`
Segundo reproductor de audio con funcionalidad idéntica.
- **Canción**: "Quién Fuera" (quienfuera.mp3)
- **Características**: Mismas que `alas.html`
- **Uso**: Permite tener múltiples reproductores independientes en la misma experiencia

#### `musica.html`
Control simplificado de música con botón toggle.
- **Funcionalidad**: Botón azul que alterna entre reproducir/pausar
- **Indicador visual**: El texto del botón cambia (▶️ Reproducir / ⏸️ Pausar)
- **Canción**: "Quién Fuera" (desde GitHub Pages)
- **Diseño**: Botón redondeado con efecto hover

---

### 📅 Widget de Fecha

#### `fecha.html`
Muestra la fecha actual dinámica en español.
- **Formato**: `17 de abril de 2026`
- **Fuente**: Montserrat Bold (Google Fonts)
- **Color**: Azul oscuro (#003b56) - compatible con la paleta del proyecto
- **Actualización**: JavaScript automático al cargar la página

---

## 🎨 Recursos Multimedia

### Archivos de Audio
| Archivo | Descripción | Tamaño |
|---------|-------------|--------|
| `menosdosalas.mp3` | Canción "Menos Dos Alas" | Audio MP3 |
| `quienfuera.mp3` | Canción "Quién Fuera" | Audio MP3 |

### Imágenes
| Archivo | Uso | Descripción |
|---------|-----|-------------|
| `replay_icon.png` | Botón de replay en widgets de audio | Icono circular turquesa con símbolo play + flecha circular |
| `boton_repetir.jpg` | Icono alternativo | Icono gris oscuro con símbolo de repetir |
| `prueba21.jpg` | Recurso visual | Paisaje: carretera con montañas y lago al atardecer |

---

## 🔧 Características Técnicas

### Diseño Transparente
Todos los componentes HTML están optimizados para:
- **Fondo transparente**: Se integran perfectamente en cualquier diseño de Experience Builder
- **Color scheme forzado a `light`**: Asegura que los controles del reproductor sean visibles (iconos negros)
- **Sin box-shadow ni bordes**: Estética limpia y minimalista

### Compatibilidad
- ✅ ArcGIS Experience Builder
- ✅ Navegadores modernos (Chrome, Firefox, Safari, Edge)
- ✅ Responsive design
- ✅ Reproducción en dispositivos móviles

### Rutas de Recursos
Los archivos de audio se cargan desde:
- **Local**: Archivos .mp3 en el mismo directorio
- **GitHub**: `https://raw.githubusercontent.com/Sphirox/ESRI-Botella/main/`
- **GitHub Pages**: `https://sphirox.github.io/ESRI-Botella/`

---

## 📦 Estructura de Archivos

```
botella-al-mar/
│
├── alas.html              # Widget reproductor 1
├── audio2.html            # Widget reproductor 2
├── musica.html            # Botón control música
├── fecha.html             # Widget de fecha
│
├── menosdosalas.mp3       # Audio 1
├── quienfuera.mp3         # Audio 2
│
├── replay_icon.png        # Icono replay (principal)
├── boton_repetir.jpg      # Icono alternativo
└── prueba21.jpg           # Recurso visual
```

---

## 🚀 Cómo Usar

### En ArcGIS Experience Builder

1. **Agregar widget de código HTML/Iframe**:
   - En Experience Builder, arrastra un widget "Embed" o "Custom Code"
   
2. **Copiar el código HTML**:
   - Abre cualquiera de los archivos `.html` en un editor
   - Copia todo el contenido
   
3. **Pegar en el widget**:
   - Pega el código en el área de código del widget
   - Asegúrate de que las rutas de los recursos sean accesibles

4. **Subir recursos**:
   - Sube `replay_icon.png` al servidor o repositorio
   - Actualiza las rutas en el código si es necesario

### Prueba Local

**Servidor HTTP simple**:
```bash
# Python 3
python -m http.server 8000

# Navegar a:
# http://localhost:8000/alas.html
# http://localhost:8000/audio2.html
# http://localhost:8000/fecha.html
```
---

## 🎯 Casos de Uso

### Widget de Audio (`alas.html` / `audio2.html`)
- **Storytelling geográfico**: Acompaña mapas con narrativa musical
- **Experiencias inmersivas**: Crea atmósfera en recorridos virtuales
- **Presentaciones interactivas**: Añade contexto emocional a datos

### Widget de Fecha (`fecha.html`)
- **Timestamps dinámicos**: Muestra la fecha de visita del usuario
- **Eventos programados**: Indica cuándo se publicó la experiencia
- **Contexto temporal**: Complementa datos históricos o proyecciones

### Botón de Música (`musica.html`)
- **Control del usuario**: Permite pausar/reanudar música de fondo
- **Accesibilidad**: Respeta preferencias de usuarios que no quieren audio automático

---

## 🎨 Paleta de Colores del Proyecto

- **Azul oscuro principal**: `#003b56` (texto fecha)
- **Azul botón**: `#0078d4` (botón música)
- **Hover oscuro**: `#002231` (estado hover)
- **Turquesa icono**: Visible en `replay_icon.png`

---

## 🔄 Flujo de Interacción

```
Usuario carga Experience Builder
    ↓
Widget de fecha muestra fecha actual en español
    ↓
Usuario hace clic en botón replay (icono turquesa)
    ↓
Audio se reinicia desde el principio y reproduce
    ↓
Audio continúa en loop automático
    ↓
Usuario puede pausar/reproducir con controles nativos
```

---

## 📝 Notas Técnicas

### Transparencia Forzada
```css
background: transparent !important;
box-shadow: none !important;
```
Esto asegura que los componentes no interfieran con el diseño de Experience Builder.

### Color Scheme Light
```css
:root { 
  color-scheme: light;
}
```
Previene que los controles del reproductor se vuelvan invisibles en fondos claros.

### Event Listeners
Los botones de replay usan JavaScript vanilla puro:
```javascript
boton.addEventListener("click", function() {
  audio.currentTime = 0;  // Reinicia
  audio.play();           // Reproduce
});
```

---

## 🌐 Enlaces Externos

- **Repositorio GitHub**: `https://github.com/Sphirox/ESRI-Botella`
- **GitHub Pages**: `https://sphirox.github.io/ESRI-Botella/`
- **Fuente Montserrat**: Google Fonts

