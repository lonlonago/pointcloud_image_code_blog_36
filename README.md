  1. Download PCL1.11.0

  Second, install PCL1.11.0

  III. VS2019 related settings

  IV. Configuration PCL1.11.0

  Test code

  Appendix - Get your own list of link libraries

##  1. Download PCL1.11.0 

 ![avatar]( 20200526085007336.png) 

 GitHub download address: https://github.com/PointCloudLibrary/pcl/releases download the two files in the red box  

##  Second, install PCL1.11.0 

 ![avatar]( 20200526085600527.png) 

 2.1 Install "PCL-1.11.0 -AllInOne-msvc2019-win64". (1) Select the second one to automatically add system variables (2) Select the D disk for the installation path, and the system will automatically create a new PCL 1.11.0 folder. 2.2 After the installation is completed, open the folder D:\ PCL 1.11.0\ 3rdParty\ OpenNI2 Double-click OpenNI-Windows-x64-2 and select the path (D:\ PCL 1.11.0\ 3rdParty\ OpenNI2) to install. 

>  For some computers, OpenNI2 may not pop up when installing, and it is installed on the C disk by default. At this time, you need to double-click the installer in the target folder, click REMOVE first, uninstall the original installation to the C disk, and then reinstall it to the target folder. 

 ![avatar]( 20200526090128836.png) 

  2.3 After all installation is completed, copy the pcl-1.11.0-pdb-msvc2019-win64.zip unzipped .pdb file to (D:\ PCL 1.11.0\ bin). 2.4 Set environment variables: Right-click on the computer - properties - advanced system settings - advanced - environment variables - user variables - Path - edit! As shown in the figure below, restart the computer after the settings are completed. Give it directly here to prevent errors (add them in turn): 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 At this point, the configuration of environment variables is complete. 

##  III. VS2019 related settings 

 ![avatar]( 20200526090823909.png) 

 3.1 Create a new empty project, select Debug for the solution configuration, and select x64 for the solution platform. 3.2 Create a new C++ source file 3.3 Right-click the newly created project - Properties: Open the properties table 

 ![avatar]( 20200526103657409.png) 

  3.4 Configuration Properties - Debugging - Environment - Add: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20200526104101644.png) 

 ![avatar]( 20200526104535843.png) 

 ![avatar]( 20200526104722251.png) 

  3.5 C/C++ - Language - Conforms to schema: No 3.6 C/C++ - General - SDL check: No  

##  IV. Configuration PCL1.11.0 

 ![avatar]( 20200925194241929.png) 

 For ease of use, the form of adding a property table is used here. Note: To add a property table, you need to set the SDL detection in the property table to: No again. Otherwise, the following error will be reported:  

 ![avatar]( 20200526091549978.png) 

 4.1 Views - Other Windows - Property Manager  

 ![avatar]( 20200526092104635.png) 

 ![avatar]( 20200526092333946.png) 

 4.2 After opening the property manager, select Debug | X64 - click Debug | X64 left inverted triangle - right-click and select, add new project property table 4.3 Project property table naming  

 ![avatar]( 2020052609260194.png) 

 4.4 Double-click the newly added property sheet - VC ++ directory - include directory and add 7 include paths  

 The specific include path added is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20200526093426340.png) 

 4.5 VC ++ directory - library directory, add 6 lib paths. The specific lib paths added are as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20200526093806871.png) 

  4.6 C/C++ - Preprocessor - Preprocessor Definition - Add: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20200526094047662.png) 

 ![avatar]( 20200526094504741.png) 

 ![avatar]( 20200526102730254.png) 

 ![avatar]( 20200526105924435.png) 

 ![avatar]( 20200526110148988.png) 

  4.7 Linker - input - additional dependencies - add the relevant lib files of PCL and VTK. The Debug version I use. The specific addition content of additional dependencies is as follows: (The content is slightly more, and it is placed in PCL1.11.0 additional dependencies. At the end of the article, in the appendix, the method of obtaining additional dependencies in batches is given) When entering into the property table, one line must correspond to a lib to be successful. Debug version 4.8 saves the property table. The next time you need to create a new project, just do the third step of VS2019 related settings, then open the property manager, add the existing property table, and find the previously saved property table to add it.   

##  Test code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20200526110936338.png) 

 Output the image below (the numbers may be different) to indicate that the installation was successful!  

##  Appendix - Get your own list of link libraries 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20200526112537554.png) 

  At this time, open your directory corresponding to Lu Jin, and there is an extra 0.txt file, which stores all the link library names in your folder. Since the link libraries of each Debug version and Release version are next to each other, just write a read document and save it separately. The specific code is as follows: (The main function is to read a txt file and output the odd and even lines to the new txt document separately.) 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574270527
  ```  
 ![avatar]( 20210211141508809.png) 



--------------------------------------------------------------------------------

 + 1. Download PCL1.11.1 

 + 2. Install PCL1.11.1 

 + 3. Set up VS2019 

 + 4. Configure PCL1.11.1 

 + 5. Test code 

 + 6. Appendix - Obtaining Additional Dependencies 

#  1. Download PCL1.11.1 

 ![avatar]( 20200925194814590.png) 

 GitHub download address: PCL 1.11.1 download the two files in the red box 

#  Second, install PCL1.11.1 

 ![avatar]( 2020092519503672.png) 

 2.1 Install "PCL-1.11.1 -AllInOne-msvc2019-win64". (1) Select the second one to automatically add system variables (2) Select the D disk for the installation path, and the system will automatically create a new PCL 1.11.1 folder. 2.2 After the installation is completed, open the folder D:\ PCL 1.11.1\ 3rdParty\ OpenNI2 Double-click OpenNI-Windows-x64-2 and select the path (D:\ PCL 1.11.1\ 3rdParty\ OpenNI2) to install. 

>  For some computers, OpenNI2 may not pop up when installing, and it is installed on the C disk by default. At this time, you need to double-click the installer in the target folder, click REMOVE first, uninstall the original installation to the C disk, and then reinstall it to the target folder. 

 ![avatar]( 20200925195256704.png) 

  2.3 After all installation is completed, copy the pcl-1.11.1-pdb-msvc2019-win64.zip unzipped .pdb file to (D:\ PCL 1.11.1\ bin). 2.4 Set environment variables: right-click on the computer - properties - advanced system settings - advanced - environment variables - user variables - Path - edit! Give it directly here to prevent errors (add in turn): 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 At this point, the configuration of environment variables is complete. 

#  III. Setting up VS2019 

 ![avatar]( 20200925195655282.png) 

 3.1 Create a new empty project, select Debug for the solution configuration, and select x64 for the solution platform. 3.2 Create a new C++ source file 3.3 Right-click the newly created project - Properties: Open the properties table  

 ![avatar]( 20200925200513680.png) 

 3.4 Configuration Properties - Debugging - Environment - Add:  

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 ![avatar]( 20200925200809433.png) 

 ![avatar]( 20200926214707189.png) 

 3.5 C/C++ - General - SDL Check: No 3.6 C/C++ - Language - Compliant Pattern: No  

#  IV. Configuration of PCL1.11.1 

 ![avatar]( 20200925201340532.png) 

 4.1 VC ++ directory - including directory, add 7 include paths. The specific include paths are as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 ![avatar]( 20200925201944380.png) 

 4.2 VC ++ directory - library directory, add 6 lib paths. The specific lib paths added are as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 4.3 C/C++ - Preprocessor - Preprocessor Definition - Add: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 ![avatar]( 20200925202603125.png) 

 ![avatar]( 20200925202810289.png) 

  4.4 Linker - input - additional dependencies - add related lib files for PCL and VTK. The Debug version I use. The specific additional dependencies added are as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 Installed!!! Release version with additional dependencies 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
#  Test code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 ![avatar]( 20200526110936338.png) 

 Output the image below (the numbers may be different) to indicate that the installation was successful!  

#  Appendix - Acquiring Additional Dependencies 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281116
  ```  
 ![avatar]( 20210211141445859.png) 



--------------------------------------------------------------------------------

#  I. Overview 

   The process of VisualStudio2022 configuration point cloud library PCL1.13.0 under Win10 system is basically the same as that of VisualStudio2019 configuration point cloud library PCL1.11.1 under Win10 system. There are two main differences: 

#  II. Configuration 

 Reference: 

 The specific additional dependencies added are as follows: Debug mode 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574288562
  ```  
 Release Mode 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574288562
  ```  
#  Enable Enhanced Instruction Setting Architecture 

 Project Properties - > C/C + ± > Code Generation - > Enable Enhanced Instruction Set Architecture - > Select AVX 

 ![avatar]( f195e4f093b74762bda4cc13e22089cd.png) 

  Reference: Ptr release in PCL aligned_free 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Overview of the process 

 ![avatar]( 20210419175117501.png) 

 For more details, please read the paper: [1] Song Chenghang, Li Jinru, Liu Guanjie. Improved ICP algorithm point cloud registration method using feature point sampling consistency [J]. Beijing Surveying and Mapping, 2021 (03): 317-322. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574234828
  ```  
#  III. Display of results 

 ![avatar]( 20210419175237958.png) 



--------------------------------------------------------------------------------

#  Overview of the process 

 ![avatar]( 20210417085810731.png) 

 For more details, please read the paper: [1] Wang Qingshan, Zhang Jun, Liu Yuansheng, Zhang Xinchen. Point cloud registration algorithm based on the combination of NDT and ICP [J]. Computer Engineering and Applications, 2020, 56 (07): 88-95. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574260945
  ```  
#  III. Display of results 

 ![avatar]( 20210417085952913.png) 



--------------------------------------------------------------------------------

#  Overview of the process 

 ![avatar]( 20210413213907991.png) 

  For more details, please read the paper: [1] Jinglu, Wu Bin, Li Xianshuai. Point cloud registration method based on SAC-IA and NDT fusion [J]. Geodesy and Geodynamics, 2021, 41 (04): 378-381. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266950
  ```  
#  III. Display of results 

 ![avatar]( 20210413214141921.png) 

#  IV. Experimental experience 

   Since there is no data used in the paper experiment, I tested it with my own point cloud data, and the efficiency of the algorithm is not very high (it may be due to the large amount of data, so voxel filtering is added to the algorithm, which can be deleted if not needed, without affecting the overall framework of the algorithm), and the accuracy has not reached the height described in the text for the time being. 



--------------------------------------------------------------------------------

#  Overview of the process 

 ![avatar]( b2dcdf7428694615be87ceedd6ab5069.png) 

 For more details, please read the paper: 

>  [1]Xu Guangxuan,Pang Yajun,Bai Zhenxu,Wang Yulei,Lu Zhiwei. A Fast Point Clouds Registration Algorithm for Laser Scanners[J]. Applied Sciences,2021,11(8): 

#  Code implementation 

 KeyPointsAnd3DSC.h 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574229623
  ```  
 Registration.h 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574229623
  ```  
 KeyPointsAnd3DSC.cpp 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574229623
  ```  
 Registration.cpp 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574229623
  ```  
 TestMain.cpp 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574229623
  ```  
#  III. Display of results 

 The RANSAC algorithm is inherently random, and it may not be able to register successfully every time!!! 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574229623
  ```  
 ![avatar]( d8a30855a8364012b423d20daf1ee6e7.png) 



--------------------------------------------------------------------------------

