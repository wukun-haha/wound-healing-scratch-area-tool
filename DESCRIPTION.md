# Wound Healing Scratch Area Tool — Project Description

**Author: Wukun (Kenny) Ouyang, Cornell University**

---

The Wound Healing Scratch Area Tool is a browser-based, client-side application for quantifying the cell-free scratch region in wound healing (scratch) assay images. It is designed for researchers who image confluent cell monolayers with a scratch down the middle and need to measure how the open area changes over time.

The tool works entirely in the front end: you open a single HTML file in Chrome, Edge, or Safari, load one or more microscopy images, and run automatic analysis with no server or installation. You first define the scale by clicking the two endpoints of the scale bar in the image and entering its real length (e.g. 100 µm). The software then uses Otsu thresholding to separate cell-covered regions from the scratch, automatically detects the upper and lower cell fronts, and computes the scratch area in both pixels and µm². Results are listed in a table and can be exported as CSV for use in spreadsheets or downstream analysis.

To keep measurements consistent and unbiased, the pipeline excludes pure white and pure black pixels when computing the Otsu threshold, so any built-in scale bar in the image does not affect the segmentation. Analysis is always performed on the raw image only: an offscreen canvas is used so that any overlaid lines (e.g. the user-drawn scale bar or previously detected fronts) are never included in the analyzed pixels. Batch mode runs the same analysis on all loaded images using the current scale, with a one-frame delay after each image load to ensure the correct image is processed.

This project is suitable for horizontal scratch assays with a visible scale bar and clear contrast between cells and the scratch. All processing stays local; no images or data are sent to any server.

---

*Use this text as the repository description (short version for GitHub About) or the full paragraph above for the README / project page.*
