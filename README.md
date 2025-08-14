# UK-Pedestrian-Crossings
# Pedestrian Crossing Classification in Northern Ireland

This repository contains a machine learning project that classifies pedestrian crossings across Northern Ireland using real spatial data. The goal is to predict whether a crossing is **signal-controlled** or **uncontrolled**, and visualize predictions on an interactive map to support city planning and road safety initiatives.

---

## Project Overview

Pedestrian crossings are critical for urban safety, but not all crossings are the same. Using AI, we can analyze and classify crossings to uncover patterns that inform decision-making for local authorities. This project demonstrates how machine learning and geospatial visualization can turn raw geographic data into actionable insights.

---

## Dataset

The dataset contains **1,558 pedestrian crossings** with the following columns:

- `ITEM_TYPE_NAME`: Type of crossing (all are pedestrian crossings)  
- `CROSSING_TYPE_NAME`: Target variable — SIGNAL CONTROLLED or UNCONTROLLED  
- `SECTION_NAME`: Road section where the crossing is located  
- `EASTING`, `NORTHING`: Coordinates in Irish Grid (EPSG:29902)  
- `START_DATE`: Date the crossing was logged  

The dataset is slightly imbalanced, with fewer UNCONTROLLED crossings, which is addressed during model training.

---

## Features & Modeling

Key steps in the project:

1. **Data Cleaning & Preprocessing**  
   - Removed missing values and duplicates  
   - Encoded categorical features (`SECTION_NAME`)  
   - Extracted year and month from `START_DATE`  

2. **Handling Class Imbalance**  
   - Applied **SMOTE** to oversample the minority class  

3. **Neural Network Model**  
   - Built a Keras sequential model with dense and dropout layers  
   - Trained to classify crossings as signal-controlled or uncontrolled  

4. **Evaluation**  
   - Achieved ~92% accuracy  
   - Evaluated using a normalized confusion matrix and classification report  

---

## Visualization

The predictions are plotted on an **interactive Folium map** of Northern Ireland. Features include:

- Colored markers representing predicted crossing types  
- Green markers indicating misclassified points  
- A legend showing prediction categories  

The map helps to quickly identify areas where crossings might need closer attention or further study.

---

## Usage

1. Clone the repository:  
```bash
git clone https://github.com/yourusername/pedestrian-crossing-ni.git
