# ML Project :-Tomato Disease Classification

## Dataset

- The dataset used is Tomato Disease Multiple Sources.
- Link: [Tomato Disease Dataset](https://www.kaggle.com/datasets/noulam/tomato)
- Volume: The dataset comprises images of diseased and healthy tomato plants, with a diverse set of classes.

## Preprocessing Techniques

- Image data augmentation using Keras ImageDataGenerator: rescaling, rotation, and horizontal flipping.
- Grayscale conversion.
- Data normalization (rescaling pixel values to be in the range [0, 1]).

## Model Architecture

- **Convolutional Tokenizer (CCT):**
  - A custom architecture combining Convolutional Tokenization, Positional Embeddings, Transformer Blocks, and Sequence Pooling.
  - Multiple transformer blocks for capturing complex relationships within the image.

## Training Techniques

- **Early Stopping:**
  - To avoid overfitting, early stopping was employed during training.
- **Learning Rate Reduction:**
  - ReduceLROnPlateau callback used to reduce the learning rate if the validation loss stagnates.

## Imbalance Handling

- Addressed class imbalance using `sklearn.utils.compute_weight`.

## Metrics

- **Metrics Used:**
  - Sparse Categorical Accuracy
  - Top-K Categorical Accuracy (Top-3 Accuracy)
  - Learning curves for loss and accuracy during training.

## Results

- **Training Metrics:**
  - Displayed learning curves for training and validation sets, including loss, Top-1 accuracy, and Top-3 accuracy.

## Deployment

- **Streamlit Web App:**
  - Utilized Streamlit for model deployment.
  - The web page allows users to upload an image and receives real-time predictions.
  - The model predicts the tomato disease class and provides a confidence percentage.

- **Working:**
  - The uploaded image is resized to the required input size.
  - The Convolutional Tokenizer predicts the class probabilities.
  - The result is displayed, indicating the predicted class (Tomato Disease type) and confidence level.

## How to Run

1. Open the project folder in the command prompt.
2. Ensure the following dependencies are installed:
   - Python
   - Streamlit
   - All necessary libraries
3. Run the following command:
   ```bash
   streamlit run app.py
   ```
4. Open the provided localhost port in your browser.
5. Upload an image to classify it as a specific tomato disease or healthy, along with the confidence percentage.