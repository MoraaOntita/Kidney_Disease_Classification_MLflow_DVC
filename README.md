# Kidney_Disease_Classification_MLflow_DVC

## Overview
This project implements a Kidney Disease Classification model using Convolutional Neural Networks (CNN) to analyze kidney CT scan images. The pipeline is built using TensorFlow for model training and evaluation, MLflow for tracking experiments, and DVC (Data Version Control) for data management. The application is served as a web service using Flask, allowing users to upload images and receive predictions.


## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Model Training](#model-training)
- [Model Evaluation](#model-evaluation)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Data Ingestion**: Automates downloading and extracting kidney CT scan images.
- **Model Preparation**: Loads and prepares a base model (e.g., VGG16) for transfer learning.
- **Training Pipeline**: Implements data augmentation and trains the model with specified parameters.
- **Model Evaluation**: Evaluates the trained model and logs metrics using MLflow.
- **Web API**: Flask-based API for model predictions with image upload capability.
- **Version Control**: Manages data and model versions using DVC.

## Technologies Used

- **Python**: Primary programming language.
- **TensorFlow**: Framework for building and training the CNN model.
- **Keras**: High-level API for TensorFlow, simplifying model building.
- **MLflow**: Tool for tracking experiments, logging parameters, metrics, and models.
- **DVC**: Data versioning tool for managing datasets and model files.
- **Flask**: Micro web framework for serving the application.
- **Docker**: Containerization for consistent deployment environments.


## Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-username/Kidney_Disease_Classification_MLflow_DVC.git
   cd Kidney_Disease_Classification_MLflow_DVC
   ```

2. **Create a virtual environment (optional but recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install required packages:**
   ```bash
   pip install -r requirements.txt
   ```

## Getting Started
1. **Data Preparation:** Update the `config.yaml` file with paths to your training data and any specific parameters you want to use for model training.

2. **Run DVC Pipeline:** Use DVC to execute the pipeline stages:
   ```bash
   dvc repro
   ```

## Usage
To run the Flask web application, execute:

   ```bash
   python app.py
   ```
This will start the server, and you can access the API at ` http://127.0.0.1:5000 `.

## Model Training
The model is trained using a pipeline that includes data ingestion, base model preparation, training, and evaluation. Each stage of the pipeline is defined in separate scripts located in the pipeline directory.

## Model Evaluation

The model evaluation stage logs metrics such as loss and accuracy. These metrics can be viewed on DagsHub by visiting your project page at [DagsHub](https://dagshub.com/).

### Viewing Experiments on DagsHub

To check your experiments on DagsHub:

1. **Log into your DagsHub account** or create a new account if you don’t have one.
2. **Navigate to your project** page where your model evaluations are logged.
3. **Select the relevant experiment** from the list to view detailed metrics and visualizations.

Make sure to integrate DagsHub with your project during the evaluation process to track these metrics correctly.

## API Endpoints

### 1. Home Endpoint
- **Method:** GET  
- **Path:** /  
- **Description:** Returns the main page of the web application.

### 2. Train Model Endpoint
- **Method:** POST  
- **Path:** /train  
- **Description:** Triggers the training process of the model.

### 3. Predict Endpoint
- **Method:** POST  
- **Path:** /predict  
- **Request Body:**
```json
{
  "image": "base64_encoded_image_string"
}
```

- **Description:** Takes a base64 encoded image string and returns the prediction.

## Contributing
Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.

2. Create a new branch:

```bash
git checkout -b feature/YourFeature
```
3. Make your Changes and Commit:

```bash
git commit -m "Add your feature"
```

4. Push to the branch.

```bash
git push origin feature/YourFeature
```

5. Open a pull request.

## License
This project is licensed under the MIT License. See the LICENSE file for details.


## Acknowledgements

- [DagsHub](https://dagshub.com/) for model tracking and collaboration.
- [TensorFlow](https://www.tensorflow.org/) for deep learning framework.
- [Flask](https://flask.palletsprojects.com/) for web application development.

**Happy Coding!**