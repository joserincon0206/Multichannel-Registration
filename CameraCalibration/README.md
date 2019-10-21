# Camera Calibration

Multi-channel registration is the process by which you can align/register information regarding an object coming from different sesors. 

Suppose that you have an RGB image which can tell you the color of the object, and a depth image which can tell you its 3D shape, and IR
cameras which can tell you the amount of water content of that object. The images from all of the sensors are not aligned. For this reason, 
you cannot do a pixel-by-pixel analysis to identify an object based on those images. However, if we had the images aligned, we could
use some rules. For instance, let's say that we are interested in detecting apple with those sensors. Then we could say that, 
pixels that have a value (255, 0, 0) (RGB), and sphere-like structure (depth), and and high water content 
ratio (using 970 nm and 800 nm IR sensors), are most likely to come from an apple. 

The first step for this multi-channel registration is to find the camera extrinsics. I.e, the cameras' locations with respect 
to a common frame. In this case, I used the camera centre of the RealSense camera (RGB-depth). 
