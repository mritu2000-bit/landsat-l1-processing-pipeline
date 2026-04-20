# Landsat L1 Processing Pipeline

End-to-end radiometric and geometric correction pipeline for Landsat 8/9 Collection 2 Level-1 data.

## What this pipeline does
- Converts raw DN values to Radiance
- Converts Radiance to TOA Reflectance
- Applies atmospheric correction using 6S radiative transfer model parameters
- Verifies geometric correction and coordinate system accuracy
- Outputs analysis-ready Surface Reflectance GeoTIFF

## Data
- Sensor: Landsat 9 OLI
- Scene: LC09_L1TP_146040_20260407
- Band processed: Band 4 (Red, 636-673nm)
- Location: UTM Zone 43N (India)

## Tools used
- Python, rasterio, numpy, Py6S, QGIS

## Results
TOA Reflectance range: 0.24 - 1.0
Surface Reflectance range: 0.21 - 0.94
Atmospheric contribution removed: ~0.03 units mean reduction# landsat-l1-processing-pipeline
