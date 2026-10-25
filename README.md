# 🚗 Autonomous Systems & Computer Vision Pipelines

> **Classical computer vision for autonomous vehicle perception: image processing, geometric transformations, feature detection and a complete lane detection pipeline, implemented with OpenCV and Python.**

---

## 🧰 Tech Stack

<div align="center" style="display: flex; flex-wrap: wrap; justify-content: center; gap: 25px; padding: 20px 0;">
  <a href="https://www.python.org" target="_blank" title="Python"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" width="50" height="50" /></a>
  <a href="https://opencv.org/" target="_blank" title="OpenCV"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" alt="OpenCV" width="50" height="50" /></a>
  <a href="https://numpy.org/" target="_blank" title="NumPy"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg" alt="NumPy" width="50" height="50" /></a>
  <a href="https://git-scm.com/" target="_blank" title="Git"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" width="50" height="50" /></a>
</div>

Libraries used: OpenCV (`opencv-python`), NumPy, Matplotlib, and scikit-image (for HOG features).

---

## 📌 Overview

The repository is a structured walk through the classical computer vision methods that an autonomous vehicle uses to see the road. Each notebook covers one method, explains the theory in markdown, applies it to a sample photo, checks the result, and saves its outputs. The notebooks build on each other and end with a lane detection pipeline.

Every notebook:
- starts with a markdown overview of the method and its use in driving;
- runs end-to-end on the sample image in its own folder;
- checks results with numbers or overlays, not only by eye;
- saves all outputs to an `output/` folder.

---

## 🚀 Getting Started

```bash
git clone https://github.com/Basti-T/ml-autonomous-systems.git
cd ml-autonomous-systems
python -m pip install opencv-python numpy matplotlib scikit-image jupyter
jupyter notebook
```

Open any notebook and run all cells. Each notebook works from its own folder, so run it from there or start Jupyter in that folder.

---

## 📓 Notebooks

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
| 11 | [Line Detection with the Hough Transform](hough_transform/hough_transform.ipynb) | Hough transform | Polar line representation, voting in the accumulator, the vote threshold, and reading line angles |
| 12 | [Detecting Lane Lines](lane_lines_hough/lane_lines_hough.ipynb) | Lane detection | Vanishing-point ROI, probabilistic Hough segments, averaging and extending lanes, and the overlay |
| 13 | [Template Matching](template_matching/template_matching.ipynb) | Feature matching | Matching methods, score thresholds, non-maximum suppression and multi-scale search |
| 14 | [Corner Detection](corner_detection/corner_detection.ipynb) | Corners | Harris response, non-maximum suppression, Shi-Tomasi corners, sub-pixel refinement, and handling transparent backgrounds |
| 15 | [Image Pyramids](image_pyramids/image_pyramids.ipynb) | Multi-scale | Gaussian pyramids with `pyrDown` and `pyrUp`, aliasing, and exact reconstruction with Laplacian pyramids |
| 16 | [Colour Histograms and Back Projection](color_histograms/color_histograms.ipynb) | Colour features | BGR and HSV histograms, hue-saturation histogram, and back projection to find a sample colour |
| 17 | [Histogram of Oriented Gradients](hog_features/hog_features.ipynb) | Shape features | Gradient strength and direction, orientation histograms per cell, block normalisation, and HOG with scikit-image |

---

## 🗺️ Topics

- **Image basics and colour:** loading and converting images, colour spaces, channel histograms and colour masks (notebooks 1, 2, 3, 5, 16).
- **Filtering and edges:** convolution, sharpening and blurring, Sobel, Laplacian and Canny edge detection (notebooks 6, 7).
- **Geometric transformations:** rotation, translation, resizing, perspective transform and bird's-eye view (notebooks 8, 9).
- **Feature detection and matching:** template matching, Harris and Shi-Tomasi corners, image pyramids, and histograms of oriented gradients (notebooks 13, 14, 15, 17).
- **Lane detection:** colour and brightness thresholds, region of interest, Hough transform, and a vanishing-point based lane pipeline (notebooks 2, 3, 4, 10, 11, 12).

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
├── region_of_interest_selection/        # 10. Region of interest from the vanishing point
├── hough_transform/                     # 11. Line detection with the Hough transform
├── lane_lines_hough/                    # 12. Lane detection with the Hough transform
├── template_matching/                   # 13. Finding an object with template matching
├── corner_detection/                    # 14. Harris and Shi-Tomasi corner detection
├── image_pyramids/                      # 15. Gaussian and Laplacian image pyramids
├── color_histograms/                    # 16. Colour histograms and back projection
├── hog_features/                        # 17. Histogram of oriented gradients
└── README.md
```

Each folder contains its notebook, the sample image the notebook loads, and the images the notebook saves.
