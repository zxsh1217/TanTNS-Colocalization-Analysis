# MATLAB Colocalization Analysis for TanTNS
This repository contains MATLAB scripts for colocalization analysis of dual-color fluorescence images (AF488 and AF647 channels), as described in our paper: [Your Paper Title] (DOI: xxx).

## 📋 Requirements

- MATLAB R2020b or later
- Image Processing Toolbox

## 📁 Repository Structure
├── scripts/
│ ├── main_colocalization.m # Main script to perform colocalization analysis
│ ├── preprocess_image.m # Function for image preprocessing (grayscale, binarization, filtering)
│ └── utils/
│ ├── spot_counter.m # Count and label spots
│ └── plot_results.m # Visualize results on original image
├── example_data/ # Example fluorescence images (same field of view)
│ ├── 488_channel.png # AF488 channel image
│ └── 647_channel.png # AF647 channel image
├── results/ # Folder for saving output figures (optional)
└── README.md

## 🚀 Quick Start

1. **Clone or download** this repository to your local machine.

2. **Open MATLAB** and navigate to the repository folder.

3. **Run the main script** with the example images:
   ```matlab
   cd scripts
   main_colocalization('../example_data/488_channel.png', '../example_data/647_channel.png')
4. Expected output:

Console will display:
AF488 spots: XXX
AF647 spots: XXX
Colocalized spots: XXX
A figure will appear showing the original AF488 image with detected colocalized spots numbered in red.

## 🔧 How It Works
The analysis follows these steps:
1. Read images: Load fluorescence images from both channels.
2. Convert to grayscale: rgb2gray (if input is RGB).
3. Binarization: Otsu's method (graythresh) to separate signal from background.
4. Size filtering: Remove objects outside 5–100 pixel area using bwpropfilt to exclude noise and large aggregates.
5. Colocalization identification: Pixels present in both filtered binary images (and operation).
6. Label and count: Use bwlabel and regionprops to enumerate colocalized spots.
7. Visualization: Overlay numbered bounding boxes on the original image.

## 📥 Input/Output
Input
Two fluorescence images from the same field of view (AF488 and AF647 channels). Supported formats: PNG, TIFF, JPEG.

Images can be grayscale or RGB (will be converted to grayscale automatically).
Output
Console report with spot counts.

Figure showing original AF488 image with numbered colocalized spots (saved automatically in results/ folder if specified).
## 📝 Citation
If you use this code in your research, please cite:

[Your Paper Reference]

and this repository:

Your Name. (2026). MATLAB Colocalization Analysis for Fluorescence Images (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.xxxxxx
## 📄 License
This project is licensed under the MIT License – see the LICENSE file for details.

## 📧 Contact
For questions, issues, or suggestions, please open an issue on GitHub or contact: [your.email@university.edu]
