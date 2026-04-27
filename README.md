# Landsat L1 Processing Pipeline
I built this project to understand the end-to-end process of satellite image preprocessing — specifically what happens at the L1 stage before data becomes analysis-ready.

# Why I built this
Most GIS workflows I've worked on start with already-corrected data. I wanted to understand what that correction actually involves at the processing level, so I built this pipeline from scratch using real Landsat 9 data over an Indian scene.

# What I learned
One thing that surprised me — when I checked the metadata after downloading the scene from USGS Earth Explorer, I found the geometric correction was already applied. So the actual work here was focused entirely on atmospheric correction using the 6S radiative transfer model via Py6S.

# What it does
Takes raw Landsat 9 OLI Level-1 data and processes it end-to-end:
- Raw DN → Radiance → TOA Reflectance
- Atmospheric correction using the 6S radiative transfer model (via Py6S)
- Geometric verification and coordinate accuracy check
- Final output: Surface Reflectance GeoTIFF ready for analysis

# Data used
- Sensor: Landsat 9 OLI
- Scene: LC09_L1TP_146040_20260407 (India, UTM Zone 43N)
- Band 4 (Red, 636–673nm)

# Tools
Python · rasterio · NumPy · Py6S · QGIS

# Results
| Stage | Reflectance Range |
|---|---|
| TOA Reflectance | 0.24 – 1.0 |
| Surface Reflectance | 0.21 – 0.94 |
| Atmospheric contribution removed | ~0.03 units |
