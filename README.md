# Mask R-CNN Image Segmentation

This project performs instance segmentation on images using a pre-trained Mask R-CNN model.

## Usage

The main steps are:

1. Clone the Mask R-CNN repository
2. Setup the Mask R-CNN model and load pre-trained weights 
3. Load and pre-process an input image
4. Make predictions using the model
5. Post-process and visualize results

### Setup

- Install dependencies:
  ```
  pip install -r requirements.txt
  ```
- Clone Mask R-CNN repo:
  ```python
  clone_repo("https://github.com/matterport/Mask_RCNN")
  ```
- Setup model and load weights:
  ```python
  config = MaskRCNNConfig()
  model = setup_model(config)
  load_weights(model, weights_path)
  ```

### Making Predictions

- Load input image:
  ```python
  img = load_and_display(image_path)
  ```
- Make predictions:
  ```python
  results = model.detect([img])
  ```
- Visualize predictions:
  ```python
  display_predictions(img, results[0], class_names)
  ```

### Post-processing

The `results` dictionary contains the following keys:

- `rois`: Bounding box coordinates
- `masks`: Segmentation masks 
- `class_ids`: Class IDs for each detection
- `scores`: Confidence scores

Post-processing functions include:

- Drawing bounding boxes on the image
- Calculating mask pixel sums
- Segmenting the image based on the highest scoring mask

## References

- [Mask R-CNN Repository](https://github.com/matterport/Mask_RCNN)
- [Keras Image Processing](https://keras.io/api/preprocessing/image/)
- [Matplotlib Visualization](https://matplotlib.org/)
