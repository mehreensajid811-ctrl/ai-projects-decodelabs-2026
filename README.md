# Project 4 - OCR Recognizer (DecodeLabs)

Path 1 (OCR): pytesseract + OpenCV. Reads text from an image, keeps only words with >= 80% confidence.

## Setup
    pip install opencv-python pytesseract pillow numpy
    # Tesseract engine: Ubuntu `sudo apt install tesseract-ocr` | macOS `brew install tesseract` | Windows: UB-Mannheim installer

## Run
    python ocr_recognizer.py                    # generated sample (tilted, noisy, uneven light)
    python ocr_recognizer.py photo.png --psm 3  # your own image

## Pipeline
Grayscale -> Gaussian blur -> deskew -> adaptive threshold -> Tesseract -> 80% gate -> annotated image

## Output (./output)
1_gray / 2_blur / 3_deskewed / 4_binary .png  (each pre-processing stage)
result_annotated.png                          (green = kept, red = dropped boxes with confidence)
