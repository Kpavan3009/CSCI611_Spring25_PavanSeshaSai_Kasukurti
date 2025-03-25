
# Style Transfer-Assignment 4 

This repository contains an implementation of the neural style transfer algorithm based on the paper "Image Style Transfer Using Convolutional Neural Networks" by Gatys et al. The implementation uses a pre-trained VGG19 network to extract content and style features from images, then optimizes a target image to match both the content representation of one image and the style representation of another.

## Overview

Neural style transfer is a technique that allows you to take the style of one image (like a painting) and apply it to the content of another image (like a photograph). This implementation follows the approach outlined in the original paper, using a pre-trained VGG19 network to extract features and optimize a target image.

## Requirements

- Python 3.6+
- PyTorch
- torchvision
- matplotlib
- numpy
- PIL
- requests

## Installation

```bash
pip install torch torchvision matplotlib numpy pillow requests
```

## Usage

### Running Locally

1. Clone this repository:

```bash
git clone https://github.com/Kpavan3009/CSCI611_Spring25_PavanSeshaSai_Kasukurti
cd CSCI611_Spring25_PavanSeshaSai_Kasukurti/Assignment_4
```

2. Run the Jupyter notebook:

```bash
jupyter notebook Style_Transfer_Exercise.ipynb
```

3. Follow the instructions in the notebook to:
   - Load content and style images
   - Extract features using VGG19
   - Define loss functions
   - Optimize the target image

### Running in Google Colab

1. Upload the `Style_Transfer_Exercise.ipynb` file to Google Drive
2. Open it with Google Colab
3. Make sure to select a GPU runtime (Runtime > Change runtime type > Hardware accelerator > GPU)
4. Run all cells in the notebook

## Implementation Details

The implementation includes the following key components:

1. **Feature Extraction**: Uses a pre-trained VGG19 network to extract features from specific layers
2. **Gram Matrix Calculation**: Computes the Gram matrix for style representation
3. **Loss Functions**: Defines content and style losses based on feature representations
4. **Optimization**: Uses Adam optimizer to update the target image

## Hyperparameter Experimentation

As part of the assignment, I experimented with various hyperparameters to understand their effects on the style transfer results:

1. **Style Weight**: Controls the emphasis on style versus content
   - Lower values (1e4) preserve more content details
   - Higher values (1e8) create more stylized images
2. **Layer Weights Distribution**: Affects which aspects of style are emphasized
   - Higher weights on early layers create larger style elements
   - Higher weights on later layers emphasize finer details
3. **Number of Iterations**: Affects refinement level
   - 500 iterations: Quick but rough results
   - 2000 iterations: Good balance
   - 5000 iterations: More refined details
4. **Learning Rate**: Controls optimization speed
   - Lower rates (0.001) produce more stable results
   - Higher rates (0.01) can be faster but less stable
5. **Initial Image**: Starting point affects final result
   - Content image start: Most reliable
   - Random noise start: More diverse results

## Results

The report includes example outputs showing the results of style transfer with different hyperparameter settings. The default parameters (style weight = 1e6, 2000 iterations, learning rate = 0.003) provide a good balance between content preservation and style transfer.

## Performance

On a T4 GPU (Google Colab), the style transfer process takes approximately:

- 5-10 minutes for 500 iterations
- 15-30 minutes for 2000 iterations
- 40-60 minutes for 5000 iterations

## Acknowledgments

- This implementation is based on the paper "Image Style Transfer Using Convolutional Neural Networks" by Gatys et al.
- The pre-trained VGG19 model is from the PyTorch model zoo

## Author

Pavan Sesha Sai Kasukurti (012122111)
