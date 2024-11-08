# Sequence-based Facial Emotion Recognition using EfficientNet and LSTM

This repository contains the final project for the Deep Learning class at Vanderbilt University. The project, titled **"Sequence-based Facial Emotion Recognition using EfficientNet and LSTM."**

## Description

This project advances facial emotion recognition (FER) by integrating a pre-trained EfficientNet model with Long Short-Term Memory (LSTM) networks to process sequence-based inputs. EfficientNet, originally designed for single-frame image analysis, is adapted here to capture temporal dynamics, improving the model’s ability to recognize emotions over a series of frames. The model predicts valence and arousal levels across sequences, with a robust 21-class system ranging from -10 to 10.

The approach leverages EfficientNet (`enet_b0_8_va_mtl.pt`) for extracting spatial features from each frame, while LSTM layers capture the temporal transitions, resulting in a deeper understanding of emotional changes over time. The model was trained on the AFEW-VA dataset, achieving notable improvements in accuracy and demonstrating the benefits of temporal analysis for FER tasks.

## Repository Contents

- **`paper/`** - Contains the final project report and supplementary materials.
- **`Plot_Loss_Accuracy.ipynb`** - Jupyter Notebook for visualizing training and validation loss and accuracy.
- **`Train_EfficientNetLSTM_v4.ipynb`** - Jupyter Notebook for training the EfficientNet-LSTM model on the AFEW-VA dataset.
- **`README.md`** - Documentation for this repository.
- **`.npy files`** - NumPy files containing model predictions, ground truth labels, and training and validation metrics for further analysis.

## Installation and Setup

### Clone the Repository

Clone this repository to your local machine:
```bash
git clone https://github.com/<celestineakpanoko>/Sequence-based-FER.git
cd Sequence-based-FER
```


### Download Pre-trained Weights

Download the `enet_b0_8_va_mtl.pt` pre-trained model file from [link to model file](https://github.com/av-savchenko/face-emotion-recognition/blob/main/models/affectnet_emotions/enet_b0_8_va_mtl.pt) and place it in the root directory of the project. This model file is required for EfficientNet to work with sequence data.

## Usage

### Training the Model

To train the model on the AFEW-VA dataset:

1. Open `Train_EfficientNetLSTM_v4.ipynb` in Jupyter Notebook.
2. Set up the dataset paths and ensure the dataset is properly formatted.
3. Execute each cell to start training. The notebook includes detailed steps for data preprocessing, model training, and saving results.

### Plotting Loss and Accuracy

To visualize the model’s performance metrics over training epochs:

1. Open `Plot_Loss_Accuracy.ipynb` in Jupyter Notebook.
2. Run the cells to plot the training and validation loss and accuracy. This notebook is useful for monitoring the model’s learning progress.

### Using Saved Predictions and Metrics

The `.npy` files in this repository contain pre-saved predictions and metrics. These files include:

- **`arousal_predictions.npy`**: Predicted arousal values.
- **`valence_predictions.npy`**: Predicted valence values.
- **`true_arousal_labels.npy`** and **`true_valence_labels.npy`**: Ground truth labels.
- **`train_accuracy.npy`**, **`val_accuracy.npy`**, **`train_losses.npy`**, **`val_losses.npy`**: Arrays for analyzing model performance during training.

These files can be loaded in Python to re-evaluate model performance or to create custom visualizations.

## Results

The model achieved substantial improvements in recognizing complex emotional expressions compared to baseline CNN-LSTM models. The use of LSTM layers allowed for better temporal integration, which improved the model's ability to capture subtle emotional changes across sequences.

### Key Highlights

- **Improved Accuracy**: The integration of LSTM layers with EfficientNet increased the model’s accuracy in predicting valence and arousal across time.
- **Temporal Dynamics**: The model successfully captured emotional transitions, underscoring the value of temporal modeling for facial emotion recognition.

For a complete analysis of the results, including detailed evaluation metrics and visualizations, please refer to the final project report located in the `paper/` directory.


## Acknowledgments

We would like to thank the following for their contributions and support:

- **AFEW-VA Dataset**: [AFEW-VA Dataset](https://cs.anu.edu.au/few/AFEW-VA/) for providing the emotion data used in this project.
