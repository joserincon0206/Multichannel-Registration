The task is to register, i.e., make the objects captured by different sensors be in close proximity in a reference frame.
This is particularly useful if you want to segment objects based of multiple caracteristics. For instance, shape given by 
a depth camera, color given by an RGB camera, and hyperspectral data given by IR cameras. 

My idea is to use a depth camera to provide the 3D data of a scene seen by several cameras. Then, using perspective projection, 
remap the 3D points onto all of the cameras' image planes. After that, you can sample the intensities from all of the sensors.

Effectively getting a multichannel image: RGB, depth, hyperspectral. 

This folder contains the initial camera pose calibration video using standard OpenCv libraries. Camera Intrisics were computed using
a Robot Operating System (ROS) node. However, the camera pose estimate was not accurate for my application. The problem lied in the 
fact that the camera pose uses a checkeboard with coplanar points. We can have multiple solutions of yaw, pitch, roll, Tx, Ty, Tz, 
that can minimize the reporjection error. Unfortunately, I am looking for the best solution, and this method did not work. 

Nonetheless, I am attaching my efforts. 
