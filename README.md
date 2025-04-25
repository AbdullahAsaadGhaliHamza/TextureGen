# TextureGen User Guide

## Introduction

**TextureGen** is a powerful tool that generates a complete set of **PBR (Physically Based Rendering)** texture maps from a single diffuse texture. This guide will walk you through installation, features, and usage to help you create high-quality PBR materials quickly and efficiently.

---

## Installation

### System Requirements

- Windows 7, 8, 10, or 11  
- Python 3.8 or higher (if running from source)  
- 4GB RAM recommended  
- 200MB free disk space  

### Option 1: Run Directly

1. Download the TextureGen package  
2. Extract the ZIP file  
3. Double-click `run_app.bat` to start the application  

### Option 2: Build an Executable

1. Download and extract the TextureGen package  
2. Double-click `build_app.bat` to create an executable  
3. The app will be in `dist/TextureGen`  
4. Launch via `TextureGen.exe`  

---

## Interface Overview

- **Preview Panel (Left):** Displays the texture and generated maps  
- **Settings Panel (Right):** Adjust generation parameters  
- **Menu Bar:** Access file operations and features  

---

## Using TextureGen

### Getting Started

#### Open a Diffuse Texture
- File → **Open Diffuse Texture...** or `Ctrl+O`  
- Or drag & drop an image into the app  
- Supported formats: `.png`, `.jpg`, `.jpeg`, `.bmp`, `.tga`

#### View Generated Maps
Maps are generated automatically. Use the dropdown in the preview panel to view:

- Diffuse Texture  
- Normal Map  
- Ambient Occlusion Map  
- Metallic Map  
- Roughness Map  
- Height Map  

#### Adjust Settings
- Modify the right panel’s parameters  
- Click **Process Texture** to regenerate maps  

#### Export Maps
- File → **Export All Maps...** or `Ctrl+E`  
- Choose a folder  
- Maps are saved as PNGs with appropriate suffixes  

---

## Adjusting Map Settings

### Normal Map
- **Strength:** 0.1–10.0  
- **Detail Scale:** 1–100  
- **Invert Y:** For DirectX-style normals  

### Ambient Occlusion
- **Strength:** 0.1–5.0  
- **Radius:** 1–100  

### Metallic Map
- **Threshold:** 0.0–1.0  
- **Detection Method:**  
  - Brightness  
  - Color  
  - Pattern Recognition  

### Roughness Map
- **Base Level:** 0.0–1.0  
- **Generate from Surface Detail**  
- **Invert:** Bright = smooth  

### Height Map
- **Strength:** 0.1–5.0  
- **Generate from Luminance:** Uses brightness over edge detection  

---

## Tips for Best Results

- **Use high-quality diffuse textures:** Clean, high-res inputs yield better outputs  
- **Adjust normal map first:** It defines perceived surface detail  
- **Tailor to material type:** Different materials need different map settings  
- **Verify in your 3D engine:** Each engine may interpret maps differently  

---

## Troubleshooting

### App Won’t Start
- Ensure Python is installed  
- Try: `python main.py`  
- Check the command line for errors  

### Import Errors
Install dependencies:
```bash
pip install numpy scipy opencv-python pillow pyqt5
```
Make sure Python 3.8+ is used.

### Texture Won’t Load
- Check file integrity and format  
- Try another supported image  

### Incorrect Map Output
- Reset settings  
- Ensure good contrast/detail in the input  
- Adjust settings incrementally  

---

## Technical Details

TextureGen uses advanced image analysis:

- **Normal Maps:** Gradient + Sobel edge detection  
- **Height Maps:** Luminance or edge detection  
- **AO Maps:** Height variation and surface detail  
- **Metallic Maps:** Color + pattern detection  
- **Roughness Maps:** Surface variance and detail edges  

---

## Credits

TextureGen was created by **TLD_Productions**.  
Thank you for using TextureGen — we hope it streamlines your PBR workflow!
