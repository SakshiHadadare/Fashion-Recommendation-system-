# Fashion Recommender System
## Introduction
The Fashion Recommender System is a machine learning application designed to recommend fashion items based on image similarity. By leveraging a pre-trained ResNet50 model, the system extracts features from images and uses these features to find the most similar items in a large dataset of 40k+ fashion images.

## Table of Contents
1. [Project Structure](#project-structure)
2. [Installation](#installation)
3. [Usage](#usage)
   - [Generate Embeddings](#generate-embeddings)
   - [Run the Streamlit App](#run-the-streamlit-app)
4. [Model and Data](#model-and-data)
5. [Acknowledgements](#acknowledgements)

## Project Structure
- **`images/`**: This directory contains all the fashion images used for generating recommendations. It should have 40k+ image files.
- **`uploads/`**: This directory is where uploaded images are saved when using the Streamlit app.
- **`embeddings.pkl`**: A pickle file storing the feature vectors of the images, generated by the `app.py` script.
- **`filenames.pkl`**: A pickle file storing the filenames of the images corresponding to the feature vectors.
- **`app.py`**: A Python script that extracts features from images using a pre-trained model and saves them in `embeddings.pkl`.
- **`main.py`**: The main script for the Streamlit application, which provides the user interface for uploading images and displaying recommendations.
- **`README.md`**: This file, which contains documentation for the project.
  
## Installation

#### Prerequisites
- Python 3.7 or higher
- TensorFlow
- Streamlit
#### Steps
1. Clone the repository:  
`git clone https://github.com/SakshiHadadare/Fashion-Recommendation-system`  
`cd Fashion-Recommendation-system`  
2. Create a virtual environment:  
`python -m venv venv`  
`source venv/bin/activate`  # On Windows use `venv\Scripts\activate`
3. Install the required packages

## Usage

### Generate Embeddings
Before you can run the Streamlit app, you need to generate the embeddings for your images. This involves extracting features from each image using the ResNet50 model and saving these features in a pickle file.
**Steps:**
1. Ensure you have all your images in the `images/` directory.
2. Run the following command to generate the embeddings:  
   `python feature_extraction.py`  
- This command will:
  - Load images from the images/ directory.
  - Extract features using the ResNet50 model.
  - Save the features and filenames into `embeddings.pkl` and `filenames.pkl`, respectively.

### Run the Streamlit App
Once the embeddings have been generated, you can start the Streamlit application to interact with the recommender system.
**Steps:**
1. Start the Streamlit app by running:  
   `streamlit run main.py`  
This command will launch the Streamlit app, and it should open in your default web browser.
2. The app will open in your default web browser. You will see an interface where you can upload an image.
3. After uploading an image, the app will:
   - Extract features from the uploaded image.
   - Use these features to find and display the most similar images from the dataset.

**Interface:**
- Upload Image:
  - Allows you to upload an image file.
  - The uploaded image will be processed to extract features.
- Recommended Images:
  - Displays images from the dataset that are most similar to the uploaded image.
  - Similarity is determined based on the extracted features.

**Notes:**
- Make sure the `uploads/` directory exists.
  - This directory is used to temporarily save uploaded images.
  - Create it if it does not already exist.
- Ensure `embeddings.pkl` and `filenames.pkl` files are available in the project directory.
  - These files contain the precomputed embeddings and filenames necessary for the recommender system.

## Model and Data
- Model: The system uses a pre-trained ResNet50 model, excluding the top layers, to extract features from the images.
- Data: The dataset consists of 40k+ fashion images. Ensure that all images are placed in the images/ directory before running the feature extraction script.

## License
This project is a derivative work based on the YouTube video titled "[Fashion Recommender System | Clothes Recommendation | Ecommerce Project]" by [CampusX]. The video can be found [here](https://youtu.be/xanJe6e8Xuw?si=pgxuar_wmbpVsDIE).  
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements
This project leverages the powerful ResNet50 model from Keras and the simplicity of Streamlit to create an interactive and user-friendly recommender system. Special thanks to the open-source community for providing tools and frameworks that make such projects possible.
