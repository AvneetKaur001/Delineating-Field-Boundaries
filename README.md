# Delineating-Field-Boundaries

**Author:** Avneet Kaur

Delineating agricultural field boundaries from Sentinel-2 satellite imagery. The
pipeline rasterises reference field geometries into boundary and extent masks,
derives distance-to-boundary targets, builds median composites across acquisition
dates, and trains a U-Net segmentation model (TensorFlow/Keras) to predict field
boundaries on unseen tiles.

## Repository overview

| Directory | Contents |
| --- | --- |
| `Preprocessing/` | Data retrieval from S3, extraction of boundary/extent masks from vector field geometries, distance-to-boundary rasters, and median compositing of Sentinel-2 scenes. |
| `Training/` | Notebook for training the U-Net boundary-segmentation model. |
| `Predictions/` | Notebook for running inference and generating boundary predictions. |

## Requirements

Python 3 with `geopandas`, `rasterio`, `fiona`, `shapely`, `numpy`, `pandas`,
`matplotlib`, and `boto3` (for pulling imagery from S3). Training and prediction
notebooks use TensorFlow/Keras and were run on GPU in Colab.
