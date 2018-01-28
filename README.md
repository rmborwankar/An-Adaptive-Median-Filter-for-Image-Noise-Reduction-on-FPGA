# An-Adaptive-Median-Filter-for-Image-Noise-Reduction-on-FPGA
An adaptive median filter to remove the impulse noise from an Image on FPGA and compared the result with in-built MATLAB function for median filtering.

Proposed System:
For a 3 by 3 window, the center pixel has 8 direct neighbors. The median filtering is nothing but replacing the center pixel value with the median of the 8 neighbors. [1] The figure 1 below shows the minimum exchange network required to generate a median value from 9 pixel input. The algorithm uses partial sorting. The pixels are loaded and compared with their neighbors. The pixels with lower vale among the two goes to left side, while the higher value goes to right. The pixels are read in a raster scanning way. In order to conduct median filtering on the boundary rows and columns we need to pad the image. Therefore, the original image which is of size 240 by 200 is now 242 by 202. The padding can be done before the image pixels are read by HDL module or it can be done by the HDL module itself. [1] In order to make implementation faster we perform pipelining in terms of reading the pixels. At every clock cycle 3 pixels are read and compared. While the comparison is done next 3 pixels are loaded and so on a so forth.

Reference:
[1] J. I. Smith, “Implementing median filters in xc4000e fpgas,” Xilinx Xcell, vol. 23, p. 16, 1999.

Note:
The pixel.coe file is not in the project which contains the image pixels.
