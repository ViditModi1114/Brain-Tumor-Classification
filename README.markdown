# Brain Tumor Classification

This project is a web-based application for classifying brain tumor images into four categories: **Glioma**, **Meningioma**, **Pituitary Tumor**, and **No Tumor**. It uses a pre-trained deep learning model (`Model.h5`) built with TensorFlow/Keras and is deployed using Flask. The application allows users to upload an image, processes it, and displays the predicted tumor type along with the uploaded image.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [File Structure](#file-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Model Details](#model-details)
- [License](#license)

## Project Overview
The Brain Tumor Classification application enables users to upload brain MRI images to classify them into one of four categories. The application uses a pre-trained convolutional neural network (CNN) model to analyze the images and provide predictions. The interface is user-friendly, built with HTML templates and styled with basic CSS, and the backend is powered by Flask.

## Features
- Upload brain MRI images for classification.
- Predicts tumor type: Glioma, Meningioma, Pituitary Tumor, or No Tumor.
- Displays the uploaded image and prediction result.
- Easy-to-use web interface with navigation between home, upload, and result pages.
- Error handling for invalid or corrupted image uploads.

## Tech Stack
| Component          | Technology                     |
|--------------------|--------------------------------|
| **Framework**      | Flask                          |
| **Model**          | TensorFlow/Keras (Model.h5)    |
| **Frontend**       | HTML, Jinja2, CSS              |
| **Dependencies**   | NumPy, OpenCV, Pandas, SciPy, Scikit-learn, Matplotlib |
| **Deployment**     | Gunicorn (via Procfile)        |
| **License**        | GNU General Public License v3  |

## File Structure
| File/Folder         | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `app.py`            | Main Flask application with routes for home, upload, prediction, and results |
| `Model.h5`          | Pre-trained TensorFlow/Keras model for brain tumor classification           |
| `requirements.txt`  | List of Python dependencies for the project                                 |
| `Procfile`          | Configuration for deploying the app with Gunicorn                           |
| `LICENSE`           | GNU General Public License v3                                              |
| `Uploads/`          | Directory to store uploaded images temporarily                             |
| `templates/`        | HTML templates for the web interface                                        |
| &nbsp;&nbsp;`- home.html`   | Home page with image upload form                                    |
| &nbsp;&nbsp;`- new.html`    | Information page about tumor types                                  |
| &nbsp;&nbsp;`- result.html` | Displays prediction result and uploaded image                        |

## Installation
To set up the project locally, follow these steps:

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd brain-tumor-classification
   ```

2. **Create a Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   Ensure `requirements.txt` is in the project root, then run:
   ```bash
   pip install -r requirements.txt
   ```

4. **Place the Model**
   - Ensure the pre-trained model file `Model.h5` is in the project root directory.

5. **Create Uploads Directory**
   - Create a directory named `Uploads` in the project root to store uploaded images:
     ```bash
     mkdir Uploads
     ```

6. **Run the Application**
   ```bash
   python app.py
   ```
   The app will run locally at `http://127.0.0.1:5000`.

## Usage
| Step                        | Action                                                                 | Where to Perform                   | Output Location                     |
|-----------------------------|----------------------------------------------------------------------|------------------------------------|-------------------------------------|
| **Access the Application**  | Open a browser and navigate to `http://127.0.0.1:5000`                | Browser                            | Home page (`home.html`)            |
| **Upload an Image**         | On the home page, click "Choose File" to select a brain MRI image     | `home.html` (Upload form)          | Temporary storage in `Uploads/`     |
| **Submit for Prediction**   | Click the "Predict" button after selecting an image                   | `home.html` (Submit button)        | Redirects to `result.html`          |
| **View Prediction**         | The result page displays the predicted tumor type and the uploaded image | `result.html`                     | Prediction and image on `result.html` |
| **Learn About Tumors**      | Navigate to the "Home" link to view tumor type descriptions           | `new.html` (via navigation link)   | Tumor info on `new.html`            |

### Notes
- **What to Upload**: Upload brain MRI images in formats like JPG or PNG.
- **Where to Upload**: Use the file input field on the home page (`http://127.0.0.1:5000/home`).
- **Where to Get Output**: The prediction result and uploaded image are displayed on the result page (`http://127.0.0.1:5000/result`).

## Model Details
- **Model File**: `Model.h5`
- **Input**: Images resized to 64x64 pixels, normalized to [0, 1].
- **Output**: Classification into one of four classes: Glioma, Meningioma, Pituitary Tumor, or No Tumor.
- **Preprocessing**: Images are converted to RGB, resized, and normalized using OpenCV.
- **Training**: The model is pre-trained (not included in this repository). Ensure `Model.h5` is present in the root directory.

## License
This project is licensed under the GNU General Public License v3. See the [LICENSE](LICENSE) file for details.