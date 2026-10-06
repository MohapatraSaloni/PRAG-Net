# PRAG-Net
PRAG-Net: UAV-Based Rural Cadastral Mapping Framework

PRAG-Net is a geospatial deep learning pipeline for automated extraction of
rural cadastral features from high-resolution UAV imagery.

The framework combines semantic segmentation, attribute classification,
geospatial post-processing, and GIS conversion to produce structured
geospatial outputs suitable for rural mapping and planning workflows.

---

## Key Features

- Building footprint extraction
- Road extraction
- Waterbody extraction
- Roof-type attribute classification
- Utility candidate extraction and classification
- Geospatial quality assurance and CRS validation
- Rasterized ML-ready label generation
- Tile-based model training and inference
- Spatial post-processing
- Raster-to-vector conversion
- Cloud Optimized GeoTIFF (COG) outputs
- GeoPackage (GPKG) GIS outputs
- Confidence-aware Human-in-the-Loop (HITL) validation

---

## System Architecture

```text
                 UAV Orthophoto
                       |
                       v
           Geospatial QA & Alignment
                       |
                       v
             ML-ready Label Creation
                       |
                       v
                 Image Tiling
                       |
                       v
            U-Net++ + ResNet-34
                       |
          +------------+-------------+
          |            |              |
          v            v              v
      Buildings      Roads       Waterbodies
          |            |              |
          +------------+--------------+
                       |
                       v
            Spatial Post-processing
                       |
                       v
                GIS Vectorization
                       |
             +---------+---------+
             |                   |
             v                   v
       Roof Classification   Utility Branch
             |                   |
             +---------+---------+
                       |
                       v
                 GIS Outputs
                 COG / GPKG
                       |
                       v
              HITL Verification
