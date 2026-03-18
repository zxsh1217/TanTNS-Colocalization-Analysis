# MATLAB Colocalization Analysis for TanTNS
This repository contains MATLAB scripts for colocalization analysis of dual-color fluorescence images (AF488 and AF647 channels).

## 📋 Requirements
- MATLAB R2020b or later
- Image Processing Toolbox

## 📁 Repository Structure
├── scripts/                        # 所有 MATLAB 脚本
│   ├── Script_1 Colocalization spots of 488+647.mlx       # 主程序：执行双通道共定位分析；函数：灰度化、二值化、尺寸筛选
│   ├── Script_2 Counting of colocalization spots 488+647.mlx       # 计数并标记荧光点、在原图上绘制结果
├── example_data/                    # 示例荧光图像（同一视野）
│   ├── Sample data of AF488 channel.png              # AF488 通道图像
│   └── Sample data of AF647 channel.png              # AF647 通道图像
└── README.md                        # 本说明文件


## 🚀 Quick Start
1. **Clone or download** this repository to your local machine.
2. **Open MATLAB** and navigate to the repository folder.
3. **Run the main script** with the example images:
   ```matlab
   cd scripts
   main_colocalization('../example_data/Sample data of AF488 channel.png', '../example_data/Sample data of AF647 channel.png')
4. Expected output:
   A figure will show the original fluorescence image with detected colocalized spots numbered in obvious color.

## 🔧 How It Works
The analysis follows these steps:
1. Read images: Load fluorescence images from both channels.
2. Convert to grayscale: rgb2gray (if input is RGB).
3. Binarization: imbinarize (for subsequent analysis).
4. Size filtering: Remove objects outside 5–100 pixel area using bwpropfilt to exclude noise and large aggregates.
5. Colocalization identification: Pixels present in both filtered binary images (and operation).
6. Label and count: Use bwlabel and regionprops to enumerate colocalized spots.
7. Visualization: Overlay numbered bounding boxes on the original image.

## 📥 Input/Output
Input: 
  Two fluorescence images from the same field of view (AF488 and AF647 channels). Supported formats: PNG, TIFF, JPEG.
  Images can be grayscale or RGB (will be converted to grayscale automatically).
Output
  Console report with spot counts.
  Figure showing original fluorescence image with numbered colocalized spots (saved automatically in results/ folder if specified).

## 📝 Citation
If you use this code in your research, please cite:

Xiaoshuang Zhao, et al. "Fluorescence Encoding Technology Based Tetrahedral Nano-string for Logic Identification of Breast Cancer Cells]." (under review, 2026).

and this repository:

Xiaoshuang Zhao. (2026). MATLAB Colocalization Analysis for Fluorescence Images (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.xxxxxx

Note: A permanent DOI will be added upon manuscript acceptance.

## 📄 License
This project is licensed under the MIT License – see the LICENSE file for details.

## 📧 Contact
For questions, issues, or suggestions, please open an issue on GitHub or contact: [zxsh1217@163.com]
