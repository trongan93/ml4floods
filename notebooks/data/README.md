# Demo Notebooks for Data Ingestion

---
## 1.0 - Geographic Index Demo

In this demo notebook, we demonstrate how to initialize a mini-database based on a query of coordinates. This will showcase how we can get a class which contains the filepaths and associated meta-data.

**Notebook**: [Source](./geographic_index_demo.ipynb)

---
## 2.0 - Creating Dataclasses

This demo notebook demonstrates how we can create a dataclass given an image and the associated metadata. The dataclass contains all of the relevant information necessary to load the file when needed as well as the relevant metadata.

**Notebook**: [Source](./dataclasses/outgest/creating_dataclasses.ipynb)

---
## 3.0 - Query to DataClass Pipeline

In this short demo notebook, we showcase a simple query followed by constructing a dataclass.

**Notebook**: [Source](./dataclasses/ingest/query_2_dataclass.ipynb)


# Notebook for Data Retrieval

**Notebook**: [Source](./full_data_ingest.ipynb)

## 1. Webscraping the Copernicus Emergency Management System's Rapid (EMSR) Activations
In this notebook we go over how to get started webscraping EMSR codes for flood events in order to
retrieve zip files that contain the following Copernicus Rapid Mapping Products:
- Source Data
- Area of Interest
- Observed Events
- Hydrography
We then download and unzip the files.

**Source**:[`activations.py`](src/data/copernicusEMS/activations.py)

## 2. Generating Flood Maps with Copernicus Rapid Mapping Products
In this notebook we go over how to retrieve the associated Rapid Mapping Products
introduced in (1) and store them as a Copernicus EMS metadata dictionary for individual
EMS alert codes. Furthermore, we take the shapefiles/polygons retrieved from the
Rapid Mapping Products and concatenate them over an area of interest to form multipolygons to
be used as a single floodmap layer as opposed to having separate layers for each activation
mapping.

## 3. Sentinel-2 Images from Google Earth Engine
Using the Area of Interest derived from the Rapid Mapping Products for a flood event we then
use the Google Earth Engine Python API to interact with a map and to download intersecting
Sentinel-2 imagery and to superimpose the floodmap derived in (2) for comparison.

**Source**:[`src/data/ee_download.py`](src/data/ee_download.py)

## 4. Generate Ground Truth Images
This notebook generates flood labeled images for use in a supervised machine learning pipeline.

**Source**:[`src/data/create_gt.py`](src/data/create_gt.py)
