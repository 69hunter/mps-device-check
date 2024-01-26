# MPS Device Check Readme

## Overview

This repository contains a simple Python script that checks for the availability of the Metal Performance Shaders (MPS) device using PyTorch. The script initializes a PyTorch tensor on the MPS device and prints the tensor if the device is available; otherwise, it notifies the user that the MPS device was not found.

## Prerequisites

Before running the script, ensure that you have the following prerequisites installed:

- Python: The script is written in Python, so you need to have Python installed on your machine.

- Pipenv: Pipenv is recommended for managing Python dependencies. If you don't have Pipenv installed, you can install it using the following command:

  ```bash
  pip install pipenv
  ```

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/69hunter/mps-device-check.git
   ```

2. Navigate to the project directory:

   ```bash
   cd mps-device-check
   ```

3. Install dependencies using Pipenv:

   ```bash
   pipenv install
   ```

4. Activate the virtual environment:

   ```bash
   pipenv shell
   ```

5. Run the script:

   ```bash
   python main.py
   ```

   The script will output either the initialized tensor on the MPS device or a message indicating that the MPS device was not found.

## Script Explanation

The script consists of the following steps:

1. **Check for MPS Availability:**
   ```python
   if torch.backends.mps.is_available():
   ```

   It checks whether the Memory Persistence Service (MPS) is available.

2. **Initialize MPS Device:**
   ```python
   mps_device = torch.device("mps")
   ```

   If the MPS device is available, it initializes the device.

3. **Create and Print Tensor:**
   ```python
   x = torch.ones(1, device=mps_device)
   print(x)
   ```

   It creates a PyTorch tensor with all elements set to 1 on the MPS device and prints the tensor.

4. **Handle MPS Device Not Found:**
   ```python
   else:
       print("MPS device not found.")
   ```

   If the MPS device is not available, it prints a message indicating that the MPS device was not found.

## Conclusion

This simple script serves as a quick check to see if the Memory Persistence Service (MPS) device is available using PyTorch. Use it as a starting point for more complex scripts or integrate it into your projects that require MPS functionality. The PyTorch library will be automatically installed as part of the Pipenv setup.