# ROS Seek Thermal Camera
A ROS wrapper for Seek Thermal cameras.

This ROS package provides integration for Seek Thermal cameras into the Robot Operating System (ROS) environment. It utilizes the Python script `ros-seekcamera-opencv.py` to capture thermal images from a Seek Thermal camera and publish them as ROS Image messages. It has been tested on the [Seek Thermal Starter Kit](https://www.thermal.com/oem.html).

This ROS package is unofficial and in no way supported by Seek Thermal. The Python script `ros-seekcamera-opencv.py` in this package is modified from the original script available at [https://github.com/seekthermal/seekcamera-python/blob/main/examples/seekcamera-opencv.py](https://github.com/seekthermal/seekcamera-python/blob/main/examples/seekcamera-opencv.py) to work seamlessly with ROS. The modifications were made to adapt the script to ROS, and credit for the original script goes to its authors. We express our gratitude for their work.   

## Prerequisites
Before using this package, you should have the following prerequisites installed on your system:
- ROS (Robot Operating System)
- Python 3.X
- [numpy >= 1](https://numpy.org):
```txt
sudo apt install python3-numpy
```
- [opencv-python](https://github.com/opencv/opencv-python):
```txt
pip3 install opencv-python==4.2.0.32
```
- seekcamera-python:
```txt
pip3 install seekcamera-python
```

You have the option to install manually by first installing Python, and then clone the seekcamera-python repository.

```txt
git clone https://github.com/seekthermal/seekcamera-python.git
```

Change directories into the cloned repository

```txt
cd seekcamera-python
```

Install via [pip](https://pypi.org/project/pip)

```txt
pip3 install -e .
```

## Package Contents
### Launch Script
The `seek_cam.launch` file is used to launch the ROS node responsible for interfacing with the Seek Thermal camera and publishing the images. You don't need to modify this file.

### Python Script
The `ros-seekcamera-opencv.py` script is responsible for interfacing with the Seek Thermal camera, capturing thermal images, and publishing them as ROS Image messages. The script provides the necessary functionalities for this task and interacts with the `seekcamera` library.

### ROS Topics
- Subscribed: None
- Published: /seek_thermal_image (sensor_msgs/Image)

## Usage
To use this package, follow these steps:
1. Make sure you have satisfied all the prerequisites mentioned above.
2. Clone this package into your ROS workspace.
```txt
git clone https://github.com/wessamhamid/seek_thermal_ros.git
```
3. Build your workspace to ensure that the package is properly integrated.
4. Connect your Seek Thermal camera to your computer.
5. Launch the `seek_cam.launch` file to start capturing thermal images and publishing them as ROS Image messages.
```txt
roslaunch seek_thermal_ros seek_cam.launch
```

## Notes
To switch the color palette, in the `ros-seekcamera-opencv.py` script, replace the following line:
```txt
camera.color_palette = SeekCameraColorPalette.TYRIAN
```
with any one of these:
```txt
camera.color_palette = SeekCameraColorPalette.WHITE_HOT
```
```txt
camera.color_palette = SeekCameraColorPalette.BLACK_HOT
```
```txt
camera.color_palette = SeekCameraColorPalette.SPECTRA
```
```txt
camera.color_palette = SeekCameraColorPalette.PRISM
```
```txt
camera.color_palette = SeekCameraColorPalette.IRON
```
```txt
camera.color_palette = SeekCameraColorPalette.AMBER
```
```txt
camera.color_palette = SeekCameraColorPalette.HI
```
```txt
camera.color_palette = SeekCameraColorPalette.GREEN
```
