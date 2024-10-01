This project develops a deep learning model to segment metastasis from brain MRI images using TensorFlow and Keras. 
It includes two models: Nested U-Net and Attention U-Net. The solution is deployed as a web application using FastAPI and Streamlit, allowing users to upload MRI images and view segmentation results.

## Installation

To run this project, you need to install the required Python libraries. You can install them using the following command:

"pip install tensorflow fastapi uvicorn streamlit numpy pillow matplotlib"


How to Run
Start the FastAPI server: Navigate to the project directory in your terminal and run the following command:
"uvicorn app:app --reload"


Run the Streamlit interface: Open another terminal session and run:
"streamlit run streamlit_app.py"


Open the Streamlit web interface: Go to http://localhost:8501 in your web browser to upload brain MRI images and view the segmentation results.


**Approach**

  Data Preprocessing
    Image Enhancement: Used CLAHE (Contrast Limited Adaptive Histogram Equalization) to improve the image contrast.
    Normalization: Scaled pixel values to the range [0, 1].
    Resizing: Adjusted images to the size required by the models (256x256).
  Model Architecture
    Nested U-Net (U-Net++): Enhances the standard U-Net with nested skip pathways and deep supervision.
    Attention U-Net: Incorporates attention gates in the U-Net architecture to focus on relevant features for more precise segmentation.
  Training
    Models were trained using augmented data to improve generalization.
    Used Adam optimizer with a binary cross-entropy loss function.
  Deployment
    FastAPI: Serves the model and handles image uploads.
    Streamlit: Provides an interactive web interface for users to upload images and view results.

