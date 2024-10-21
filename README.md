# Dewow Filter for GPR Data

This project implements the Dewow filter (also known as "subtract mean" filtering) for Ground Penetrating Radar (GPR) data. The Dewow filter is used to remove low-frequency trends from GPR data, which can improve the clarity of the reflections from subsurface features. This implementation reads GPR profiles from specified files, applies the Dewow filter, and visualizes the results.

## Overview

The Dewow filter is crucial in GPR data processing as it enhances the visibility of subsurface features by eliminating background noise and low-frequency variations. The filter operates by calculating the mean of a specified window size and subtracting this mean from the data points, effectively centering the data around zero.

### Implementation

This implementation is provided in a Jupyter Notebook and utilizes Python with the following libraries:
- `numpy`: for numerical operations.
- `matplotlib`: for data visualization.

### Key Features

- **Data Import**: Read GPR data from `.rd3` files and their associated metadata.
- **A-scan Visualization**: Visualize single traces from the GPR profile.
- **Profile Visualization**: Display the entire GPR profile with enhanced contrast.
- **Dewow Filtering**: Apply the Dewow filter with customizable window sizes.

## Usage

1. **File Preparation**: Ensure your GPR data files are formatted correctly, with the necessary `.rad` and `.rd3` files available.

2. **Run the Notebook**: Open the Jupyter Notebook and run the following code snippets:

    ```python
    # Import necessary libraries
    import os
    import numpy as np
    import matplotlib.pyplot as plt
    import math

    # Define the file to be processed
    file = 'Profile8.rd3'

    # Create an instance of the GPR_Profile class
    profile_1 = GPR_Profile(file)

    # Visualize the A-scan
    profile_1.show_ascan()

    # Apply the Dewow filter with a specified window size
    profile_1.dewow_filter(82)

    # Visualize the processed profile
    profile_1.show_profile()
    ```

### Functions

- **`GPR_Profile(file)`**: Initializes the GPR profile by importing data from the specified file.
- **`import_data(file)`**: Loads the GPR data and metadata from the given file.
- **`show_ascan()`**: Displays a scatter plot of a selected A-scan from the GPR profile.
- **`show_profile()`**: Visualizes the complete GPR profile with color mapping based on amplitude.
- **`dewow_filter(window)`**: Applies the Dewow filter to the data using the specified window size.

## Parameters

- **`window`**: The size of the window used to calculate the mean for the Dewow filter. It should be an odd integer. If an even integer is provided, it will be adjusted to the next odd number.

