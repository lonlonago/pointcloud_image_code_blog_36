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

