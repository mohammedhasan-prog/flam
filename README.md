# ✨ 3D Interactive Bézier Curve Playground

An interactive, real-time 3D Bézier curve visualization built with **Three.js**. Control curves using mouse, touch, or device motion sensors with smooth physics-based animations.

![Demo](https://img.shields.io/badge/Demo-Live-brightgreen) ![Three.js](https://img.shields.io/badge/Three.js-r134-blue) ![License](https://img.shields.io/badge/License-MIT-yellow)

## 🎯 Features

### 🖱️ Multiple Input Methods
- **Mouse/Touch**: Drag to rotate view, scroll/pinch to zoom
- **Device Tilt**: Control the curve using your phone's gyroscope
- **Device Acceleration**: Use accelerometer for dynamic control

### 📐 Curve Types
- **Cubic Bézier**: 4 control points (P0, P1, P2, P3)
- **Quadratic Bézier**: 3 control points (P0, P2, P3)

### 🎨 Visual Effects
- **3D Tube Rendering**: Beautiful volumetric curve display
- **Particle Trail**: Colorful particles follow the animated dot
- **Glowing Control Points**: Emissive materials with adjustable intensity
- **Starfield Background**: Atmospheric space-like environment
- **Grid & Ground Plane**: Visual reference for 3D space

### ⚡ Physics System
- **Mass-Spring-Damper**: Realistic physics for control point P2
- **Parameters**:
  - Mass: 1.0
  - Stiffness: 120.0
  - Damping: 15.0
- **Semi-implicit Euler Integration**: Stable and smooth motion

### 💾 Presets System
- Save your favorite curve configurations
- Load presets instantly
- Stored in browser's localStorage
- Persistent across sessions

### 📸 Export
- Export current view as **PNG image**
- High-quality screenshot with transparency support

## 🚀 Getting Started

### Option 1: Direct File
Simply open `index.html` in any modern web browser.

### Option 2: Local Server
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```
Then open `http://localhost:8000` in your browser.

## 🎮 Controls

### Desktop
| Action | Control |
|--------|---------|
| Rotate View | Click & Drag |
| Zoom | Scroll Wheel |
| Move P2 | Drag the green sphere |
| Place P2 | Click on grid |
| Toggle Animation | `Space` |
| Reset Scene | `R` |
| Export Screenshot | `S` |

### Mobile
| Action | Control |
|--------|---------|
| Rotate View | 1-finger drag |
| Zoom | 2-finger pinch |
| Move P2 | Drag the green sphere |
| Place P2 | Tap on grid |
| Sensor Control | Enable in settings |

## 🔧 Configuration Options

### Input Mode
- **Touch/Mouse**: Direct manipulation
- **Device Tilt**: Gyroscope-based control (gamma/beta angles)
- **Device Acceleration**: Accelerometer-based control

### Curve Settings
- **Curve Type**: Switch between cubic and quadratic
- **Show Control Handles**: Toggle handle lines visibility
- **Show Grid**: Toggle ground grid
- **3D Tube Mode**: Switch between tube and line rendering

### Visual Effects
- **Particle Trail**: Enable/disable particle effects
- **Glow Intensity**: Adjust emissive material brightness (0-2)

### Animation
- **Auto Animate**: Animate a dot along the curve
- **Auto Rotate**: Slowly rotate the camera view
- **Animation Speed**: Control playback speed (0.1x - 3x)

## 📁 Project Structure

```
flam/
├── index.html      # Single-file application (HTML + CSS + JS)
└── README.md       # This file
```

## 🛠️ Technical Details

### Dependencies
- **Three.js r134** (loaded via CDN)
- No build tools required
- No npm/node dependencies

### Browser Support
- ✅ Chrome (Desktop & Mobile)
- ✅ Firefox (Desktop & Mobile)
- ✅ Safari (Desktop & iOS)
- ✅ Edge
- ✅ Opera

### Sensor APIs Used
- `DeviceOrientationEvent` - For tilt control
- `DeviceMotionEvent` - For acceleration control
- iOS 13+ permission flow supported

## 🧮 Mathematical Background

### Cubic Bézier Curve
```
B(t) = (1-t)³P₀ + 3(1-t)²tP₁ + 3(1-t)t²P₂ + t³P₃
```
Where `t ∈ [0, 1]`

### Quadratic Bézier Curve
```
B(t) = (1-t)²P₀ + 2(1-t)tP₁ + t²P₂
```

### Mass-Spring-Damper Physics
```
F = -k(x - x_target) - c·v
a = F / m
v += a · dt
x += v · dt
```
Where:
- `k` = stiffness (120)
- `c` = damping (15)
- `m` = mass (1)

## 📱 Mobile Considerations

- Touch events are handled with `passive: false` for smooth interaction
- `user-scalable=no` prevents unwanted page zoom
- Sensor permissions are requested on iOS 13+
- Pixel ratio is capped at 2 for performance

## 🎨 Color Palette

| Element | Color | Hex |
|---------|-------|-----|
| P0 (Start) | Blue | `#3b82f6` |
| P1 (Handle) | Purple | `#8b5cf6` |
| P2 (Controlled) | Green | `#10b981` |
| P3 (End) | Orange | `#f59e0b` |
| Curve | Indigo | `#667eea` |
| Animated Dot | Red | `#ef4444` |

## 📄 License

MIT License - Feel free to use, modify, and distribute.

## 🙏 Acknowledgments

- [Three.js](https://threejs.org/) - 3D rendering library
- Bézier curve mathematics by Pierre Bézier

---

Made with ❤️ for creative coding enthusiasts
