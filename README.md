# CNN_LSTM Soil Moisture Prediction  

This repository contains a research project focused on predicting soil moisture using satellite images and a hybrid deep learning model combining Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks. The goal is to process GeoTIFF files containing soil moisture data, prepare the data for training, and build an effective predictive model to forecast soil moisture values.  

---

## Table of Contents  
1. [Project Overview](#project-overview)  
2. [Repository Structure](#repository-structure)  
3. [Requirements](#requirements)  
4. [Data Description](#data-description)  
5. [Implementation Steps](#implementation-steps)  
6. [Usage Instructions](#usage-instructions)  
7. [Outputs](#outputs)  
8. [Future Work](#future-work)  
9. [Contact Information](#contact-information)  

---

## Project Overview  

Soil moisture is a crucial parameter for agriculture, hydrology, and climate studies. This project leverages satellite images in GeoTIFF format to create a data pipeline and implement a CNN-LSTM model:  
- **CNN**: Extracts spatial features from soil moisture images.  
- **LSTM**: Captures temporal patterns to predict soil moisture for upcoming days.  

The model combines these techniques to create an efficient and accurate prediction framework.  

---

## Repository Structure  


---

## Requirements  

The following Python libraries are required to run the code:  
- `os`: For file handling and directory operations.  
- `rasterio`: To read and process GeoTIFF files.  
- `numpy`: For numerical computations.  
- `matplotlib`: To visualize data and results.  
- `seaborn`: For enhanced data visualization.  
- `random`: For generating random operations when required.  

To install these libraries, run:  

```bash  
pip install rasterio numpy matplotlib seaborn  

# CNN-LSTM Soil Moisture Prediction

## Data Description
**Input Data:**  
GeoTIFF files representing soil moisture values collected daily for the year 2022.

**Directory Structure:**  
Place all GeoTIFF files in a folder named `2022_geotiffs` within the repository directory.

**Summary:**  
- **Total GeoTIFF files:** 364  
- **Data dimensions:** The output shape is `(number of files, height, width)`, representing the combined spatial and temporal data.

---

## Implementation Steps

### 1. Data Loading
- Use the `rasterio` Python library to load GeoTIFF files.
- Extract each GeoTIFF as a 2D NumPy array.
- Handle missing values (`NaN`) by replacing them with `0.0`. This ensures the model does not encounter invalid data during training.

### 2. Data Preprocessing
- Combine all the individual 2D arrays from the GeoTIFF files into a single 3D NumPy array. The final structure will be:  
  `(number of files, image height, image width)`.  
  Example: `(364, 919, 1792)` where 364 represents the days of the year.
- Save this array for efficient reuse during the training phase.

### 3. Model Development
- **CNN (Convolutional Neural Network):**  
  Extract spatial features from the soil moisture maps. Each GeoTIFF file represents a spatial distribution of soil moisture values, and CNN layers capture the spatial patterns effectively.
- **LSTM (Long Short-Term Memory):**  
  Process temporal sequences of soil moisture maps. LSTM layers are designed for sequential data and help predict future values based on historical patterns.
- Combine CNN and LSTM layers into a hybrid model that learns both spatial and temporal dependencies.

### 4. Prediction
- Train the hybrid CNN-LSTM model using the preprocessed data.
- Evaluate the model’s performance using metrics such as RMSE, MAE, or accuracy.
- Use the trained model to predict soil moisture for future dates by inputting sequences of past GeoTIFF data.

---
Clone the Repository
Run the following command to clone the repository and navigate into the project directory:
```bash
git clone https://github.com/your-username/CNN_LSTM_Soil_Moisture_Prediction.git
cd CNN_LSTM_Soil_Moisture_Prediction


### Notes:
- Make sure to replace `your-username` in the GitHub URL with your actual GitHub username.
