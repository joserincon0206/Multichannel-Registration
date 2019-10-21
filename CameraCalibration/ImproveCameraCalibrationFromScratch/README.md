# Improved Camera Calibration

Please open file: # Calibration2.gif

Given that the standard OpenCV algorithm did not work for my application, I decided to write my own code. 

This code does not use coplanar points, i.e., checkerboard, but can be used for any configuration of points as long as you can easily 
detect them. 

I first created a fake 3D scence and coded the whole routine. Then I tested it on real data. 

Algorithm: 

1. Feature matching from Master and Slave cameras using Sift features and Flann matcher with OpenCv. 
2. The Master image is also align to a depth camera (this is by default in the RealSense Camera architecture). 
3. Get the depth points using the pixel coordinates of the matched features. 
4. Use prespective projection to project the 3D points to the Slave image. 
5. Compute errors from features in Salve image, and projected 3D points from Master image. 
6. Formulate problem as a Non-Linear least squeare problem. 
7. Compute Jacobian Matrix
8. Update estimate using Levenberg-Marquardt method. 
9. Repeat until convergence. 
