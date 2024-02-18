#  First, the principle of the algorithm 

##  1. Algorithm flow 

   When the VoxelGrid filter downsamples, it can reduce the point cloud data while maintaining the shape characteristics of the point cloud, which is very practical in improving the speed of algorithms such as registration, surface reconstruction, and shape recognition. Algorithm principle: Create tiny three-dimensional cubes in the point cloud data, these three-dimensional cubes are called voxel grids, and then in each voxel, replace all points in the voxel with the center of gravity of all points contained in the voxel, so that downsampling can be realized to improve the processing speed of subsequent algorithms.  

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574267358
  ```  
   When using setLeafSize () and setMinimumPointsNumberPerVoxel () at the same time, if there are more points in the voxel than the specified number of points, setLeafSize () is used to calculate; if the number of points in each voxel is less than the minimum number of points, then use the minimum point to recalculate the minimum voxel side length that satisfies the constraint 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574267358
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574267358
  ```  
 ![avatar]( 01f7cf1bbe864c9c9966c8aa97d68c4e.png) 

