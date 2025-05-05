# Medical Image Steganography using Dynamic Three-Bit LSB Embedding
This is an image steganography algorithm based on dynamic 3-bit LSB embedding, optimized for medical and e-healthcare systems.  
The method is inspired by the research article:  
[A Dynamic Three-Bit Image Steganography Algorithm for Medical and e-Healthcare Systems](https://www.researchgate.net/publication/344534131_A_Dynamic_Three-Bit_Image_Steganography_Algorithm_for_Medical_and_e-Healthcare_Systems)
## REQUIREMENTS:
  - python 3
  - numpy
  - opencv-python
  - matplotlib
  - skimage
## Algorithm Review:
### Introduction
This algorithm hides secret messages inside grayscale medical images (like brain MRIs) using an adaptive LSB approach.  
The number of embedded bits (1, 2, or 3) depends on the intensity of each pixel — maximizing capacity while preserving quality.

### Key Features
#### 1. IRD-Based Image Segmentation:
Pixels are categorized into three intensity regions:
- **Low (0–85)** → Embed 1 bit  
- **Medium (86–170)** → Embed 2 bits  
- **High (171–255)** → Embed 3 bits
#### 2. Dynamic Bit Embedding:
The algorithm automatically adapts the number of LSBs used per pixel based on intensity segmentation — improving imperceptibility and capacity.
#### 3. Lossless Message Extraction:
Thanks to region tracking, the hidden message can be extracted with 100% accuracy.
#### 4. Image Quality Evaluation:
After embedding, the image is evaluated using:
- **MSE (Mean Squared Error)**
- **PSNR (Peak Signal-to-Noise Ratio)**
- **SSIM (Structural Similarity Index)**
#### 5. Optional Gaussian Noise Robustness Test:
The algorithm's performance can be tested by adding Gaussian noise to verify message recovery in noisy conditions.
### Usage Guidelines:
#### Embedding:
Run the main notebook and provide:
- A grayscale medical image (e.g., brain MRI)
- A binary message (text converted to bits)

The algorithm will segment the image, embed the message, and output a stego image.
#### Extraction:
Using the same segmentation rules, the message is fully recovered from the stego image.
### Result:
Here’s an example from a test image:
| Metric         | Value         |
|----------------|---------------|
| Accuracy       | 100%          |
| PSNR           | ~72–81 dB     |
| SSIM           | ~1.000        |
### Conclusion:
This project demonstrates an adaptive and secure way to embed sensitive medical data into diagnostic images without compromising visual quality. The method is simple, effective, and optimized for healthcare image workflows.
## Usage Example:

[Original Image](Original_Image.png)  
[Stego Image](Stego_Image.png)  
[Extracted Message Screenshot](Extracted_Message.png)

> [!NOTE]
> If you're running this in Google Colab, upload a sample grayscale MRI image and the message file before execution.

