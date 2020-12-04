# Facial-Feature-Detection-and-3D-Reconstruction-with-Texture-Generation

This repository has been built to detect facial features using the standard 68 landmark data file and will hance generate a 5 landmark coordinate system that will eventually be used by the 3D reconstruction scripts to generate an object file with built-in vector textures.


## System Requirements

Project uses below python packages:

- __NumPy__ : A fundamental package for scientific computing with Python.

- __OpenCV__ : A library of Python bindings designed to solve computer vision problems.

- __dlib__ : A toolkit for making real world machine learning and data analysis applications.

- __imutils__ : A series of convenience functions to make basic image processing functions such as translation, rotation, resizing, skeletonization, displaying Matplotlib images, sorting contours, detecting edges, and much more easier with OpenCV and both Python 2.7 and Python 3.

- __Reconstruction__ : Reconstructions can be done on both Windows and Linux. However, we suggest running on Linux because the rendering process is only supported on Linux currently. If you wish to run on Windows, you have to comment out the rendering part.

- __scipy__ 

- __pillow__

- __Tensorflow 1.4 ~ 1.12__

- __Basel Face Model 2009 (BFM09)__ : Expression Basis (transferred from Facewarehouse by Guo et al.). The original BFM09 model does not handle expression variations so extra expression basis are needed.

- __tf mesh renderer__ : We use the library to render reconstruction images. Install the library via pip install mesh_renderer. Or you can follow the instruction of tf mesh render to install it using Bazel. Note that current rendering tool does not support tensorflow version higher than 1.13 and can only be used on Linux.


## Installation

1. Clone the repository:
```
git clone https://github.com/SwagatSBhuyan/Facial-Feature-Detection-and-3D-Reconstruction-with-Texture-Generation.git
cd Facial-Feature-Detection-and-3D-Reconstruction-with-Texture-Generation
```

2. Download and install Python 3.6 or Anaconda 4 on your system as per your operating system [Download Python](https://www.python.org/downloads/release/python-360/) [Download Anaconda 4](https://www.anaconda.com/products/individual)
> please note: Follow the Anaconda Documentation properly to install the required Conda dependencies to run Python scripts and notebooks.

3. Install the required python packages needed to run the scripts.

4. Download the Basel Face Model. Due to the license agreement of Basel Face Model, you have to download the BFM09 model after submitting an application on its [home page](https://faces.dmi.unibas.ch/bfm/bfm2019.html). After getting the access to BFM data, download "01_MorphableModel.mat" and put it into ```./BFM``` subfolder.

5. Download the Expression Basis provided by [Guo et al](https://github.com/Juyong/3DFace). You can find a link named "CoarseData" in the first row of Introduction part in their repository. Download and unzip the Coarse_Dataset.zip. Put "Exp_Pca.bin" into ```./BFM``` subfolder. The expression basis are constructed using Facewarehouse data and transferred to BFM topology.

6. Download the trained [reconstruction network](https://drive.google.com/file/d/176LCdUDxAj7T2awQ5knPMPawq5Q2RUWM/view), unzip it and put "FaceReconModel.pb" into ```./network``` subfolder.

7. Run Jupyter Notebook in Local Terminal:
```
jupyter notebook
```
8. Insert desired images to render in the ```./images``` folder in the root directory.

9. Run the two lines of code already present inside the notebook:
```
!python 5_landmark_detection.py --shape-predictor shape_predictor_68_face_landmarks.dat --image images/image_1.jpg
!python main.py
```
> please note: instead of 'image_1.jpg' you can insert the name of the desired image to reconstruct.

10. check the ```./output``` folder to acquire the generated .obj files with built-in vector textures, that can be rendered using softwares, such as [meshlab](https://www.meshlab.net/#download).


## Citation
Please cite the following paper if this model helps your research:
```
@inproceedings{deng2019accurate,
    title={Accurate 3D Face Reconstruction with Weakly-Supervised Learning: From Single Image to Image Set},
    author={Yu Deng and Jiaolong Yang and Sicheng Xu and Dong Chen and Yunde Jia and Xin Tong},
    booktitle={IEEE Computer Vision and Pattern Recognition Workshops},
    year={2019}
}
```

## References
1. @microsoft/Deep3DFaceReconstruction Deep 3D face Reconstruction [GitHub](https://github.com/microsoft/Deep3DFaceReconstruction)
2. @raviranjan0309/Detect-Facial-Features Detect Facial Features [GitHub](https://github.com/raviranjan0309/Detect-Facial-Features)


