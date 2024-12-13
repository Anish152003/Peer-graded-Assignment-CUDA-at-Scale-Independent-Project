**Project Overview: Image Rotation with NVIDIA NPP and CUDA**

This project demonstrates how to use the NVIDIA Performance Primitives (NPP) library in conjunction with CUDA to perform efficient image rotation on a GPU. The goal is to leverage GPU power to rotate an image by a specified angle. This example serves as a template for understanding how basic image processing tasks can be implemented using CUDA and NPP in the *CUDA at Scale for the Enterprise* course.

### Project Structure

- **bin/**: Contains the compiled binary files (executables) of the project. Executable files will have an appropriate extension (e.g., `.exe` or other depending on the programming language).
  
- **data/**: Stores any input/output example data. If the data is large or can be generated dynamically, the directory might be left empty to avoid the need for large downloads.
  
- **lib/**: Holds any external libraries that are not installed via the system's package manager, making them easier to link with the project.
  
- **src/**: This is where the source code resides, organized hierarchically as needed.
  
- **README.md**: A description of the project for anyone interested in cloning or understanding its purpose.

- **INSTALL**: A human-readable guide for installing the project, providing platform-specific instructions when possible.

- **Makefile / CMakeLists.txt / build.sh**: Build scripts for compiling the project automatically.

- **run.sh**: An optional script for running the compiled executable, possibly with command-line arguments.

### Key Concepts
- **Performance Strategies**: Techniques to optimize the image processing operations.
- **Image Processing**: Rotating images using GPU acceleration.
- **NPP Library**: Utilizes the NPP library for optimized image operations on CUDA-enabled devices.

### Supported SM Architectures
The project supports various CUDA architectures, including SM 3.5, 3.7, 5.0, 5.2, 6.0, 6.1, 7.0, 7.2, 7.5, 8.0, and 8.6.

### Supported Operating Systems
- **Linux**
- **Windows**

### Supported CPU Architectures
- x86_64
- ppc64le
- armv7l

### Dependencies
- **FreeImage**: A library for image input/output operations.
- **NPP**: NVIDIA Performance Primitives library for optimized image processing.

### Prerequisites
To begin, you must install the CUDA Toolkit 11.4 for your platform. Ensure that the dependencies listed in the "Dependencies" section are also installed.

### Build and Run Instructions

**Windows**
- The Windows version uses Visual Studio IDE. Solution files (.sln) are available for each supported version of Visual Studio.
  - To build all samples, use the complete solution file.
  - To build a specific sample, use the corresponding solution file.
  
  **Note**: Some samples may require the Microsoft DirectX SDK (June 2010 or newer). Ensure VC++ paths are correctly set up.

**Linux**
- The Linux version uses makefiles for building.
  - To build, change to the sample directory and run `make`:
  
    ```bash
    $ cd <sample_dir>
    $ make
    ```

  - You can target specific architectures using `TARGET_ARCH`. For example:
  
    ```bash
    $ make TARGET_ARCH=x86_64
    ```

  - To build with debug symbols, use `dbg=1`:
  
    ```bash
    $ make dbg=1
    ```

  - To override the supported SM architectures, use `SMS="A B ..."`, where `A B ...` is a space-separated list of architectures:
  
    ```bash
    $ make SMS="50 60"
    ```

  - To specify a custom host compiler:
  
    ```bash
    $ make HOST_COMPILER=g++
    ```

### Running the Program
After building the project, you can execute it with the following command:

```bash
make run
```

This command will rotate the input image (`Lena.png`) by 45 degrees and save the result as `Lena_rotated.png` in the `data/` directory.

To run with custom input and output files, use:

```bash
./bin/imageRotationNPP --input data/Lena.png --output data/Lena_rotated.png
```

### Cleaning Up
To clean up compiled binaries and other generated files, run:

```bash
make clean
```

This will remove all files from the `bin/` directory.
