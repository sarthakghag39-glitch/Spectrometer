# Webcam Light Intensity & Spectrum Analyzer

A real-time webcam analysis tool developed for physics lab experiments. This application allows you to capture a live video feed, select a Region of Interest (ROI), and plot the spatial intensity distribution of light (Red, Green, Blue, and overall Mean intensity) across the selected region. 

It is ideal for verifying wave optics phenomena such as **single-slit/double-slit diffraction patterns**, **interference fringes**, and **color spectrum dispersion profiles**.

---

## 📸 Overview & Physics Application

In optics experiments, measuring the relative intensity of light across diffraction or interference patterns is crucial for analyzing fringe spacing, wavelength, and intensity decay. 

This program replaces expensive photodetector arrays by utilizing a standard webcam:
1. **Capture:** Receives real-time video frames from your webcam.
2. **Select (ROI):** Focuses on a horizontal strip of the diffraction pattern.
3. **Analyze:** Computes the average intensity value for each column of pixels in the cropped region.
4. **Plot:** Generates intensity profiles showing:
   * **Red Channel Intensity**
   * **Green Channel Intensity**
   * **Blue Channel Intensity**
   * **Mean Intensity** (Average of R, G, and B)

---

## 🛠️ Prerequisites & Installation

To run this project, you need Python installed on your system along with the following libraries:

```bash
pip install opencv-python numpy matplotlib
```

---

## 🚀 How to Run

1. Connect your webcam or light-source camera to your computer.
2. Open your terminal or command prompt in the project directory.
3. Run the script:
   ```bash
   python project.py
   ```

---

## 🎮 Controls & Usage

When the program starts, it opens a camera preview window. Use the following keyboard keys to interact with the application:

| Key | Action | Description |
|:---:|:---|:---|
| **`r`** | **Select ROI** | Pauses the frame and opens the Region of Interest selector. Click and drag a bounding box over the pattern you want to analyze, then press **`Enter`** or **`Space`** to confirm. |
| **`s`** | **Plot Intensity** | Captures the current ROI, calculates the column-wise mean RGB intensities, and plots them using `matplotlib`. |
| **`q`** | **Quit** | Safely releases the camera and closes all windows. |

### ROI Selection Instructions:
1. Press `r`.
2. Draw a rectangle across the horizontal width of your fringe pattern (e.g., from left to right covering the central maximum and secondary maxima).
3. Press `Enter` or `Space` to lock it in. You will see a cropped window displaying the active ROI.
4. Press `s` to generate the interactive plot showing the intensity curve.

---

## 📊 Plot Interpretation

The generated plot features:
* **Top Subplot:** The cropped image of the selected region of interest (e.g., the visual fringes).
* **Bottom Subplot:** A line graph where:
  * The **x-axis** represents the horizontal pixel position (column index) within the ROI.
  * The **y-axis** represents the average light intensity (ranging from `0` to `255`).
  * Curves are colored corresponding to **Red**, **Green**, and **Blue** channels, with a black line indicating the **Mean** intensity.
