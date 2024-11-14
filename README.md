# AI-Driven Smart Traffic Management System

## Overview
This project aims to build an AI-driven traffic management system to predict traffic volumes and suggest optimal and alternative paths based on real-time data. The system uses an LSTM model (via TensorFlow) to forecast traffic congestion and employs graph-based algorithms to route vehicles optimally.

---

## Database Information
The dataset used in this project is structured as follows:

1. **Columns**:
   - **DateTime**: Timestamp of the traffic data recorded at each junction.
   - **Junction**: The identifier of each junction in the traffic network.
   - **Vehicles**: The recorded number of vehicles at each junction per hour.
   - **ID**: Unique identifier for each record.

2. **Database Structure**: The data is stored in a tabular format (CSV or SQL), with each row representing a single observation of vehicle count at a particular junction and timestamp.

---

## Prerequisites
To run this project, you’ll need to install the necessary dependencies. These can be set up within a Conda environment.

### Dependencies
- **Python 3.8 or higher**
- **TensorFlow** (for LSTM model)
- **Pandas** (for data handling)
- **Numpy** (for array manipulation)
- **Matplotlib** (for visualizations)
- **Scikit-learn** (for additional preprocessing)
- **NetworkX** (for graph-based pathfinding)

### Conda Environment Setup
Run the following commands in your terminal to set up a Conda environment and install the dependencies:

```bash
# Create a new Conda environment
conda create -n traffic_management python=3.8

# Activate the environment
conda activate traffic_management

# Install dependencies
conda install pandas numpy matplotlib scikit-learn networkx
pip install tensorflow
```

### Additional Requirements
If your dataset is in SQL format and you’re using `SQLAlchemy` or `sqlite3` for database handling, install it with:

```bash
conda install -c anaconda sqlalchemy
# or for sqlite
conda install sqlite
```

---

## Instructions to Run the Code

1. **Clone the Repository**:  
   Clone this repository to your local machine (or navigate to the directory where the files are located).

   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. **Prepare the Dataset**:
   - Place the dataset file (e.g., `traffic_data.csv`) in the `data/` directory of the project.
   - If using a database format, ensure the database file (e.g., `traffic_data.db`) is in the `data/` directory, and update any database connection code accordingly.

3. **Run Preprocessing and Training Script**:
   - Run the script to preprocess the data and train the LSTM model.
   - Make sure to set the paths to the data correctly in the script.

   ```bash
   python preprocess_and_train.py
   ```

4. **Run Prediction and Pathfinding**:
   - After training, you can use the model to make predictions and execute the pathfinding algorithms.
   
   ```bash
   python traffic_prediction_and_pathfinding.py
   ```

5. **Visualize and Analyze Results**:
   - The script will output the optimal and alternative paths based on traffic conditions.
   - View the generated visualizations and logs for the analysis of traffic congestion and route suggestions.

---

## Project Structure

```
├── data/
│   └── traffic_data.csv          # Traffic data file
├── models/
│   └── lstm_model.h5             # Saved LSTM model (after training)
├── scripts/
│   ├── preprocess_and_train.py   # Preprocessing and training script
│   └── traffic_prediction_and_pathfinding.py  # Prediction and pathfinding code
└── README.md                     # Project instructions
```

---

## Notes
- **Customization**: Modify the dataset path, model parameters, and threshold values in the code as needed.
- **Troubleshooting**: Ensure the Conda environment is activated when running the scripts.
