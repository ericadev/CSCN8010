## Project Documentation.

Before we begin, you'll need to have some software installed on your system:
* Python 3.8+
* Git
* DVC (`pip install dvc[gdrive]`) - we'll use the Google Drive remote for simplicity.
* Kaggle API (`pip install kaggle`)

We will follow a structured, nine-step process to build your application. Here is the plan we will follow:

***

| Step | Name | Description |
| :--- | :--- | :--- |
| 1 | **Project Initialization** | Set up the project directory, initialize Git for code versioning, and initialize DVC for data versioning. |
| 2 | **Data Acquisition** | Programmatically download or manually place the dataset into the project folder. |
| 3 | **Data Processing & DVC** | Unzip, clean, and organize the raw images into a `train`/`test` structure. Use DVC to start tracking the dataset. |
| 4 | **DVC Remote Storage** | Configure a remote storage location (like a local folder, Google Drive, or S3) and push the dataset to it. |
| 5 | **PyTorch DataLoaders** | Define image transformations and create PyTorch `DataLoader` objects to efficiently feed data to the model. |
| 6 | **CNN Model Definition** | Define the CNN architecture, typically using a pre-trained model for transfer learning (e.g., ResNet50). |
| 7 | **Model Training (Baseline)** | Write the training loop, define the loss function and optimizer, and train the model on the training data while monitoring it on a validation set. |
| 8 | **Model Evaluation (Baseline)** | Evaluate the final trained model on the unseen test set, calculating metrics like accuracy, a confusion matrix, and a classification report. |
| 9 | **Versioning the Model (Baseline)**| Use DVC to version the final trained model file (`.pth`), completing the full reproducible ML pipeline. |
| 10 | **Hyperparameter Tuning** | Improve model performance by systematically searching for optimal hyperparameters (e.g., learning rate, batch size) using tools like Optuna. |
| 11 | **Re-Train with Optimal Parameters**| Re-run the full training process using the best hyperparameters found during tuning to produce a final, high-performance model. |
| 12 | **Experiment Tracking** | Integrate a tool like MLflow or W&B to log metrics, parameters, and model artifacts for better experiment comparison and organization. |
| 13 | **Inference & Deployment** | Create a script to run predictions on new images and build a simple interactive web UI using a library like Gradio or Streamlit. |