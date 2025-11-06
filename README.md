## **Project Overview**



This project is part of the JRF Satellite Image Classification Assignment, aimed at mapping land cover types using Sentinel satellite data and ESA World Cover land cover maps.

The workflow involves geospatial data handling, raster processing, and setting up a classification pipeline for land cover prediction.



**Note: To reduce repository size and ensure compatibility with GitHub notebook rendering, the Google Colab has cleared outputs. Interactive maps, large images, and TIFF outputs are not included.**





**All outputs, including maps and processed images, are generated when the notebook is run.**



**The notebook is cleaned for GitHub rendering; running it locally is required to see full interactive outputs.**



**This approach ensures GitHub correctly displays the notebook without metadata errors.**



##### **Project Structure**



**Vaibhavi\_Satellite\_Assignment/**

**│**

**├── data/**

**│   ├── sentinel\_downloads/       # Full dataset (on Google Drive)**

**│   ├── raster/**

**│   │   └── land\_cover.tif        # ESA land cover raster**

**│   ├── shapefile/                # delhi\_airshed.geojson, delhi\_ncr\_region.geojson**

**│   └── testing\_folder/           # Small demo subset (5 sample .tif files)**

**│**

**├── notebooks/**

**│   └── main\_pipeline.ipynb       # End-to-end preprocessing and patch extraction**

**│**

**├── outputs/**

**│   ├── land\_cover\_labels\_clean.csv**

**|   ├──land\_cover\_labels.csv**

**│   ├── train\_labels.csv**

**│   └── test\_labels.csv**

**│**

**└── README.md**



##### **Workflow Summary**



Steps Completed:



1. Tile Metadata Extraction

Parsed Sentinel tile filenames to extract geographic coordinates.



2\. Patch Extraction (128×128)

For each tile, extracted a patch from the ESA land cover raster centered at the tile coordinates.



3\. Edge Case Handling



Skipped patches with >50% no-data pixels.



Removed invalid or out-of-bounds tiles.



4\. ESA Class Code Mapping

Mapped ESA’s raw class codes to 11 standardized global land cover classes.



5\. Train–Test Split

Performed a 60/40 stratified split of the labeled data and saved CSVs.



##### **Next Steps (Work in Progress)**



Train a CNN classifier (e.g., ResNet18) using the extracted patches.



Evaluate the model using:



Custom F1 Score implementation



torchmetrics.F1Score



Generate and explain a confusion matrix.



Visualize correct vs incorrect predictions.



##### **Dataset Access**



Due to large file size, only a small demo dataset is included in the GitHub repo.

The full dataset (used for actual processing) is available here:

[Dataset link](https://drive.google.com/drive/folders/11jYRYfsXrgoMaM3Bu015dMjdUxTcjYsK?usp=sharing)



##### **Code Adaptability**



The notebook automatically detects whether it’s being run on:



Google Drive (full dataset)



Local/GitHub (demo dataset)



##### **Author**



Vaibhavi Tiwari

Project for JRF Application – IIT Gandhinagar

