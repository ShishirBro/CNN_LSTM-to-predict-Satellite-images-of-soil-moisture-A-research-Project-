CNN_LSTM Soil Moisture Prediction
This repository contains a research project focused on predicting soil moisture using satellite images and a hybrid deep learning model combining Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks. The goal is to process GeoTIFF files containing soil moisture data, prepare the data for training, and build an effective predictive model to forecast soil moisture values.

Table of Contents
Project Overview
Repository Structure
Requirements
Data Description
Implementation Steps
Usage Instructions
Outputs
Future Work
Contact Information
Project Overview
Soil moisture is a crucial parameter for agriculture, hydrology, and climate studies. This project leverages satellite images in GeoTIFF format to create a data pipeline and implement a CNN-LSTM model.

CNN: Extracts spatial features from soil moisture images.
LSTM: Captures temporal patterns to predict soil moisture for upcoming days.
The model combines these techniques to create an efficient and accurate prediction framework.

Repository Structure
plaintext
Copy
Edit
📂 Codes
 ├── CNN_LSTM_SM_Prediction.ipynb  # Main Jupyter Notebook for the implementation
 ├── Dataextraction_geotiff.txt    # Instructions or script for GeoTIFF extraction
 └── README.md                     # Project documentation (this file)
Requirements
The following Python libraries are required to run the code:

os: For file handling and directory operations.
rasterio: To read and process GeoTIFF files.
numpy: For numerical computations.
matplotlib: To visualize data and results.
seaborn: For enhanced data visualization.
random: For generating random operations when required.
To install these libraries, run:

bash
Copy
Edit
pip install rasterio numpy matplotlib seaborn
Data Description
Input Data: GeoTIFF files representing soil moisture values collected daily for the year 2022.
Directory Structure: Place all GeoTIFF files in a folder named 2022_geotiffs within the repository directory.
Summary:
Total GeoTIFF files: 364
Data dimensions: The output shape is (number of files, height, width), representing the combined spatial and temporal data.
Implementation Steps
Data Loading:

Use rasterio to load GeoTIFF files.
Extract data as 2D NumPy arrays.
Handle missing values (NaN) using the clean_data function, which replaces invalid values with 0.0.
Data Preprocessing:

Combine individual GeoTIFF files into a single 3D NumPy array.
Structure of the final array: (number of files, image height, image width).
Model Development:

Design a hybrid CNN-LSTM model:
CNN: Extracts spatial features from soil moisture maps.
LSTM: Processes temporal sequences for predictive modeling.
Prediction:

Train the model on historical data.
Predict soil moisture for future dates based on the input sequence.
Usage Instructions
Step 1: Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/CNN_LSTM_Soil_Moisture_Prediction.git
cd CNN_LSTM_Soil_Moisture_Prediction
Step 2: Prepare the Dataset
Ensure all GeoTIFF files are stored in the directory 2022_geotiffs under the main repository folder.

Step 3: Launch the Notebook
Run the Jupyter Notebook to preprocess data and begin model training:

bash
Copy
Edit
jupyter notebook Codes/CNN_LSTM_SM_Prediction.ipynb
Step 4: Execute Cells Sequentially
Follow the steps in the notebook to process data, clean it, and prepare it for the hybrid CNN-LSTM model.

Outputs
GeoTIFF File Summary:

Logs the number of GeoTIFF files processed and their shape.
Example output:
yaml
Copy
Edit
Found 364 GeoTIFF files.
Data array shape: (364, 919, 1792)
Cleaned Data:

All NaN values in the GeoTIFF data are replaced with 0.0.
Future Work:

The notebook prepares the data and sets the groundwork for training the CNN-LSTM model.
Predictions and evaluation metrics will follow in subsequent steps.
Future Work
Develop and fine-tune the CNN-LSTM model.
Evaluate model performance using accuracy, RMSE, or other metrics.
Explore additional datasets to improve model robustness.
Investigate the impact of hyperparameter tuning and advanced architectures.
Contact Information
For questions, feedback, or collaboration:

Author: Shishir Bro
📧 Email: schaulag@purdue.edu
