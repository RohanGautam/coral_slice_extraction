# Coral Slice Extraction

A Python tool for extracting and analyzing profiles from 3D point cloud data of coral microatolls.

<p align="center">
  <img src="imgs/image.png" alt="Coral slice extraction">
</p>

## Installation

1. Clone the repository:

2. Create a new conda environment:

```bash
conda create -n coral-profile python=3.8
conda activate coral-profile
```

3. Install required packages:

```bash
pip install open3d numpy matplotlib pandas jupyter
```

## Project structure

```
├── data/ # Store your .ply files here
├── out/ # Output directory for CSV files
├── coral_slice.ipynb # Main notebook for processing
└── README.md
```

## Usage

1. Place your .ply files in the `data/` directory

2. Launch Jupyter Notebook

```bash
jupyter notebook # or open in vscode and select appropriate kernel
```

4. Run the notebook cells sequentially to:
   - Load the point cloud
   - Set the center point
   - Extract profiles at specified angles
   - Generate visualizations
   - Export profile data to CSV

## Common Issues

1. If you encounter the GLFW error: "Cocoa: Failed to find service port for display", try restarting VSCode or your Jupyter kernel. This sometimes happens during open3d visualisation.

2. If the slice box is not visible in the scene, try adjusting the `hyp` parameter in the `get_point_theta()` function call.

## Parameters

- `center`: Coordinates for the center of the point cloud from which the slice starts, going radially outward.
- `hyp`: Controls the length of the slice
- `theta_rad`: Controls the thickness of the slice
- `angles_degree`: Array of angles at which to extract profiles

## Output

The script generates:

- CSV files containing profile data in the `out/` directory
- Scatter plot visualizations of the extracted profiles, in the notebook
