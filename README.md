# 🚗 Autonomous Systems & Computer Vision Pipelines

> **Core computer vision techniques, image feature engineering, and neural networks for autonomous vehicle perception.**

---

## 🧰 Tech Stack & Tools

<div align="center" style="display: flex; flex-wrap: wrap; justify-content: center; gap: 25px; padding: 20px 0;">
  <a href="https://www.python.org" target="_blank" title="Python"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" width="50" height="50" /></a>
  <a href="https://opencv.org/" target="_blank" title="OpenCV"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" alt="OpenCV" width="50" height="50" /></a>
  <a href="https://www.tensorflow.org/" target="_blank" title="TensorFlow"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg" alt="TensorFlow" width="50" height="50" /></a>
  <a href="https://keras.io/" target="_blank" title="Keras"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/keras/keras-plain.svg" alt="Keras" width="50" height="50" /></a>
  <a href="https://numpy.org/" target="_blank" title="NumPy"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg" alt="NumPy" width="50" height="50" /></a>
  <a href="https://pandas.pydata.org/" target="_blank" title="Pandas"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg" alt="Pandas" width="50" height="50" /></a>
  <a href="https://git-scm.com/" target="_blank" title="Git"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" width="50" height="50" /></a>
</div>

---

## 🚧 Status: In Development

This repository is under active construction and grows notebook by notebook. It houses practical implementations of computer vision algorithms, image processing pipelines, and deep learning architectures for self-driving vehicle perception.

The first notebooks build the foundation of a classic **lane detection pipeline**. Many more are on the way.

---

## 📓 Notebooks

Each notebook starts with a markdown overview, runs end-to-end on the included sample road image, and saves all outputs.

| # | Notebook | Topic | What you learn |
|---|---|---|---|
| 1 | [Convert to Grayscale](convert_image_to_grayscale/image_to_rgb.ipynb) | Colour spaces | Loading images with OpenCV, BGR vs. RGB, grayscale conversion and pixel statistics |
| 2 | [Lane Detection in Grayscale](lane_detection_grayscale/lane_detection_grayscale.ipynb) | Colour selection | Masking white lane pixels with a brightness threshold and comparing thresholds with histograms |
| 3 | [Lane Detection in Colour](lane_detection_color/lane_detection_color.ipynb) | Colour selection | Masking white pixels with a per-channel RGB threshold and reading channel histograms |
| 4 | [Region of Interest](lane_detection_region_of_interest/lane_detection_region_of_interest.ipynb) | Masking | Restricting detection to a trapezoid in front of the car and combining it with the colour mask |
| 5 | [Colour Spaces](colorspaces/colorspaces.ipynb) | Colour spaces | Splitting an image into RGB and HSV channels and masking red, green, blue and yellow |
| 6 | [Sharpening and Blurring](sharpening_and_blurring/sharpening_and_blurring.ipynb) | Convolution | Kernels, sharpening, box, Gaussian, median and bilateral blurs, and unsharp masking |
| 7 | [Edge Detection](edge_detection/edge_detection.ipynb) | Edge detection | Sobel, Laplacian and Canny edge detectors, Gaussian pre-blur, and automatic Canny thresholds |
| 8 | [Rotation, Translation and Resizing](rotation_translation_resizing/rotation_translation_resizing.ipynb) | Geometric transformations | Affine matrices, rotation with an enlarged canvas, translation, combining transforms into one warp, and interpolation methods |
| 9 | [Perspective Transform](perspective_transform/perspective_transform.ipynb) | Perspective | Homography from four corner points, straightening a traffic sign, and checking the matrix |
| 10 | [Region of Interest Selection](region_of_interest_selection/region_of_interest_selection.ipynb) | Masking | Building the ROI from the vanishing point of the lane lines (Hough transform and line fitting), with a fixed-polygon fallback |

More notebooks are on the way. See the roadmap below.

---

## 🎯 Roadmap

* **Phase 1: Image Processing & Filtering** — OpenCV basics, convolution filters, and Canny/Sobel edge detection.
  * ✅ Colour spaces and grayscale conversion
  * ✅ Colour selection of lane pixels (grayscale and RGB)
  * ✅ Gaussian blur, Sobel, Laplacian and Canny edge detection
* **Phase 2: Geometric Transformations** — Camera calibration and perspective mapping (Bird's-Eye View).
  * ✅ Rotation, translation and resizing
  * ✅ Perspective transform (bird's-eye view)
* **Phase 3: Feature Extraction** — Template matching, HOG feature extraction, and corner detection.
* **Phase 4: Lane & Object Detection** — Region-of-interest masking and classifier-based detection.
  * ✅ Region-of-interest masking
  * ⏳ Hough transform for lane lines
  * ⏳ Classifier-based object detection
* **Phase 5: Traffic Sign Classification** — Convolutional Neural Networks (CNNs) using TensorFlow and Keras.

---

## 📂 Repository Structure

```text
ml-autonomous-systems/
│
├── convert_image_to_grayscale/          # 1. Colour image to grayscale
├── lane_detection_grayscale/            # 2. White lane mask from a grayscale image
├── lane_detection_color/                # 3. White lane mask from a colour image
├── lane_detection_region_of_interest/   # 4. Region-of-interest masking
├── colorspaces/                         # 5. Colour channels and colour masks
├── sharpening_and_blurring/             # 6. Convolution, sharpening and blurring
├── edge_detection/                      # 7. Sobel, Laplacian and Canny edges
├── rotation_translation_resizing/       # 8. Rotation, translation and resizing
├── perspective_transform/               # 9. Perspective transform of a traffic sign
├── region_of_interest_selection/        # 10. Polygon region of interest and masking
├── ...                                  # More notebooks coming soon
└── README.md
```

Each folder contains its notebook, the sample image `image_lane_c.jpg`, and the images the notebook saves.
