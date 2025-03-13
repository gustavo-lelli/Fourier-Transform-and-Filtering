# Assignment 2: Fourier Transform and Filtering in Frequency Domain

## Overview
This assignment focuses on implementing image filtering techniques in the frequency domain using the Discrete Fourier Transform (DFT). The goal is to apply various filters to an input image, compare the filtered image with a reference image using Root Mean Squared Error (RMSE), and visualize the results.

## Requirements
- **Python 3**
- **Libraries**: `imageio`, `numpy`, `matplotlib` (for visualization only, not required for submission)

## Installation
Install the required libraries using pip:

```bash
pip install imageio numpy matplotlib
```


## Code Structure

### Functions

1. **`low_pass_filter(P, Q, kernel_size)`**:
   - Creates a low-pass filter mask with the same dimensions as the image.
   - Parameters: `P`, `Q` (dimensions of the image), `kernel_size` (radius of the filter).

2. **`high_pass_filter(P, Q, kernel_size)`**:
   - Creates a high-pass filter mask with the same dimensions as the image.
   - Parameters: `P`, `Q` (dimensions of the image), `kernel_size` (radius of the filter).

3. **`band_pass_filter(P, Q, kernel_size1, kernel_size2)`**:
   - Creates a band-pass filter mask with the same dimensions as the image.
   - Parameters: `P`, `Q` (dimensions of the image), `kernel_size1`, `kernel_size2` (radii of the filter).

4. **`laplacian_high_pass_filter(P, Q)`**:
   - Creates a Laplacian high-pass filter mask with the same dimensions as the image.
   - Parameters: `P`, `Q` (dimensions of the image).

5. **`gaussian_low_pass_filter(P, Q, ro1, ro2)`**:
   - Creates a Gaussian low-pass filter mask with the same dimensions as the image.
   - Parameters: `P`, `Q` (dimensions of the image), `ro1`, `ro2` (standard deviations for the Gaussian filter).

6. **`RMSE(reference_image, filtered_image)`**:
   - Computes the Root Mean Squared Error (RMSE) between the reference image and the filtered image.
   - Parameters: `reference_image`, `filtered_image`.

### Main Script

- Loads the input image and reference image.
- Applies the selected filter to the input image in the frequency domain.
- Transforms the filtered image back to the spatial domain using the inverse Fourier Transform.
- Computes and prints the RMSE between the filtered image and the reference image.
- Optionally saves and displays the filtered image.

## Usage

### Input Parameters
- `input_image`: Filename of the input image (e.g., `apollo17.png`).
- `reference_image`: Filename of the reference image (e.g., `apollo17_ref.png`).
- `index`: Filter index (0, 1, 2, 3, or 4).
  - `0`: Ideal Low-pass filter.
  - `1`: Ideal High-pass filter.
  - `2`: Ideal Band-stop filter.
  - `3`: Laplacian High-pass filter.
  - `4`: Gaussian Low-pass filter.
- Additional parameters depending on the filter:
  - For filters 0, 1, and 2: `kernel_size` (radius).
  - For filter 2: `kernel_size1` and `kernel_size2` (radii).
  - For filter 4: `ro1` and `ro2` (standard deviations).

### Running the Code
Modify the input parameters in the script as needed and run the script to perform the filtering and RMSE calculation.

## Author
- Gustavo Lelli Guirao
- NUSP: 11918182
- SCC0251 - Image Processing and Analysis (1º/2024)