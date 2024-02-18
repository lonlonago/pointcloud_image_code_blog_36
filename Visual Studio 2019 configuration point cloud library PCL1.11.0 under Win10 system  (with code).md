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

