# Wound Healing Scratch Area Tool

**Author: Wukun (Kenny) Ouyang, Cornell University**

A browser-based, client-side tool for quantifying the cell-free scratch region in wound healing assay images. Open the HTML file in Chrome, Edge, or Safari; load microscopy images; define scale by clicking the scale bar endpoints; then run automatic Otsu-based front detection to get scratch area in px² and µm². Pure white/black pixels are excluded from thresholding so built-in scale bars do not bias results; analysis uses an offscreen canvas (image only). Supports single-image and batch analysis with CSV export. All processing is local—no data is uploaded.

## How to use

1. Open `scratch_area_tool.html` in a modern browser (Chrome / Edge / Safari).
2. On the left panel:
   - **Upload microscopy image**: choose one or more images where cells are on the top and bottom and the scratch is in the middle. You can drag & drop or use the file picker.
   - **Set scale bar**:
     - Enter the real length of the scale bar (e.g. 100 µm) in “Real length (µm)”.
     - Click “Draw scale bar on image” and then click the two endpoints of the scale bar on the image.
   - **Compute scratch area**:
     - Click “Auto-detect fronts & calculate area” to run Otsu-based detection and get pixel area and scratch area (µm²).
     - Use “Batch analyze all loaded images” to run the same analysis on all loaded images with the current scale.
3. Results are shown in the table and can be exported as CSV.

## Notes

- Designed for images where the scratch is approximately horizontal, with cell layers at the top and bottom and a clear scale bar.
- **Automatic detection**: The tool uses an offscreen canvas (image only, no overlaid lines) and Otsu thresholding; pure white and pure black pixels are excluded when computing the threshold so built-in scale bars do not bias the result.
- Batch analysis waits one frame after loading each image so the correct image is used; single and batch both analyze the same pure image content.
- All computation is done locally in the browser; images are not uploaded anywhere.
