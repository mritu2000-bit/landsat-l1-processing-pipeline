# Landsat L1 Processing Pipeline

I built this to understand what actually happens between a raw satellite image and an analysis-ready product — the step most GIS workflows skip over.
What it does
Takes raw Landsat 9 OLI Level-1 data and processes it end-to-end:

Raw DN → Radiance → TOA Reflectance
Atmospheric correction using the 6S radiative transfer model (via Py6S)
Geometric verification and coordinate accuracy check
Final output: Surface Reflectance GeoTIFF ready for analysis

Data used

Sensor: Landsat 9 OLI
Scene: LC09_L1TP_146040_20260407 (India, UTM Zone 43N)
Band 4 (Red, 636–673nm)

Tools
Python · rasterio · NumPy · Py6S · QGIS
Results
StageReflectance RangeTOA Reflectance0.24 – 1.0Surface Reflectance0.21 – 0.94Atmospheric contribution removed~0.03 units
Why this matters
Most EO analytics pipelines assume the data is already corrected. This project gave me hands-on understanding of what that correction actually involves — and where it can go wrong.
