# YOLO Annotation Toolkit

A lightweight, browser-based suite for creating, editing, and verifying object detection annotations in CSV format. 

Built with React (Standalone), this toolkit requires **no installation**, **no backend**, and runs entirely in your web browser.

**[Live Demo](https://)** *(Replace the link above once you enable GitHub Pages)*

## Project Structure

This toolkit consists of three main files:

* **`index.html`**: The main dashboard/landing page.
* **`tagger.html`**: A single-image editor for creating or fixing boxes.
* **`checker.html`**: A batch review tool for comparing "Clean" vs "Annotated" images side-by-side.

## Features

* **Zero Dependencies:** No Python, no Docker, no Node.js installation required. Just open the HTML file.
* **Universal Drag & Drop:** Drag images and CSVs directly into the browser.
* **Privacy Focused:** All processing happens client-side. Your images are never uploaded to a server.
* **Flexible CSV Support:** Includes a settings panel to map custom CSV column names.
* **YOLO Logic:** Handles normalized coordinates (`x_center`, `y_center`, `width`, `height`) relative to image size.

---

## How to Use

### 1. Tagger (Create & Edit)
*Best for: Fixing a specific image or starting from scratch.*

1.  Launch **Tagger**.
2.  Drag and drop **one image** onto the canvas.
3.  (Optional) Drag and drop an existing `.csv` file to load current boxes.
4.  Type a class name (e.g., "cat") and press **Add**.
5.  Draw bounding boxes.
6.  Click **Download CSV** to save your work.

### 2. Checker (Review & Verify)
*Best for: Quality assurance on a batch of dataset files.*

1.  Launch **Checker**.
2.  Drag and drop a **batch of files** (multiple images + their corresponding `.csv` files).
3.  The tool automatically pairs `image.png` with `image.csv`.
4.  Use the **Queue** in the sidebar to navigate files.
5.  **Left Screen:** Interactive (Add/Delete boxes here).
6.  **Right Screen:** Read-only (Original image for comparison).
7.  Click **Save & Next** to download the corrected CSV and move to the next image.

---

## CSV Data Format

By default, the tools export and expect CSV files with the following headers (though you can map custom headers in the settings):

```csv
class_id,class_name,x_center,y_center,width,height
0,person,0.523000,0.451000,0.120000,0.340000
1,car,0.781000,0.510000,0.250000,0.150000
