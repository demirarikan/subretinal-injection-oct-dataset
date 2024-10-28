# OCT Dataset: Ex-vivo Open-Sky Porcine Eye Imaging

This repository contains a dataset of **Optical Coherence Tomography (OCT)** images collected from **ex-vivo open-sky and intact porcine eyes** during robot assisted subretinal injections. The images have been hand-labeled to identify three key surfaces:

1. **Needle (1)**
2. **Internal Limiting Membrane (ILM) (2)**
3. **Retinal Pigment Epithelium (RPE) (3)**

The dataset is intended for use in developing models for segmentation or other types of image analysis. There is a total of 1560 images.

## Dataset Overview

A 42 gauge (100 micron thickness) needle was used during the procedures.  
The images in this dataset are annotated using the [Supervisely](https://supervisely.com) platform. Each pixel in the labeled images belongs to one of the following classes:

- `0`: Background
- `1`: Needle
- `2`: Internal Limiting Membrane (ILM)
- `3`: Retinal Pigment Epithelium (RPE)

### Important Notes

- Because the bevel is difficult to accurately detect while the needle is deeper in the tissue the bevel is not annotated. 
- The labeled images are not directly human-viewable since they contain discrete class values (0, 1, 2, and 3). 
- For visualization purposes, we provide an **example Jupyter notebook** that demonstrates how to convert these labeled images into a human-viewable format using color mapping.
- Files labelled xyz-intact are collected from intact porcine eyes instead of open-sky. 
  
## Repository Structure
```bash
.
├── data/
│   ├── jul9-3/
│   │   ├── ann/                 # JSON files for Supervisely annotations
│   │   ├── img/                 # Original OCT images
│   │   ├── masks_machine/       # Machine-readable masks (pixel values: 0, 1, 2, 3)
│   ├── jul9-4/
│   │   ├── ann/                 # JSON files for Supervisely annotations
│   │   ├── img/                 # Original OCT images
│   │   ├── masks_machine/       # Machine-readable masks (pixel values: 0, 1, 2, 3)
│   ├── ...
│   ├── meta.json                # Metadata for supervisely
│   ├── obj_class_to_machine_color.json  # Metadata for supervisely
├── notebooks/
│   ├── visualize_labels.ipynb    # Notebook for visualizing the annotations
│   ├── pytorch_dataloader.ipynb  # Example PyTorch Dataloader for the dataset
├── README.md
```

## Example Notebooks

1. **Visualizing the Annotations**: In the `visualize_labels.ipynb` notebook, you can find a function to convert the label images into a human-viewable format.

## Installation and Usage

To work with the dataset and provided notebook, you'll need to install the required Python packages. The basic setup is as follows:

### Requirements

- Python 3.12 (Probably works with any version of Python 3)
- `numpy`
- `matplotlib`
- `opencv-python` (for image processing)
- `jupyterlab` or `notebook` (for running the example notebooks)

### Installation

1. Clone the repository:
   ```bash
   git clone git@github.com:your-user-name/subretinal-injection-oct-dataset.git
   cd subretinal-injection-oct-dataset
   ```

2. Install dependencies:
   ```bash
   pip install numpy
   pip install matplotlib
   pip install opencv-python
   pip install jupyterlab
   ```

3. Run the example notebooks:
   ```bash
   jupyter notebook notebooks/visualize_labels.ipynb
   ```

## Dataset Citation

If you use this dataset in your research or projects, please cite it appropriately.

TODO: add citation

## License

This dataset is provided under the [MIT License](LICENSE).