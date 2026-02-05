# NDVI_Drone_Imagery

This repository contains a Jupyter Notebook that demonstrates how to load
high‑resolution multispectral drone imagery and calculate NDVI to assess
crop canopy health.

## Contents

- `ndvi_avocado_analysis.ipynb`  
  - Explains NDVI concepts and example values  
  - Loads a multispectral orthomosaic and DEM  
  - Computes NDVI and health classes  
  - Produces presentation‑ready NDVI maps and summary statistics

## Example dataset

The notebook uses DroneMapper’s CropAnalysis sample dataset
(MicaSense Altum multispectral orthomosaic and elevation models).

Imagery is **not** included in this repository.  
To run the notebook:

1. Download the sample data from DroneMapper:  
   https://dronemapper.com/software/DroneMapper_CropAnalysis_Data.zip
2. Extract the `.tif` files into the same folder as the notebook.

Imagery © DroneMapper; used for educational and demonstration purposes.

## Running the notebook

1. Open Anaconda Navigator and launch Jupyter Notebook.  
2. Navigate to the project folder and open `ndvi_avocado_analysis.ipynb`.  
3. Run the cells from top to bottom.
