# Kinect Exposure
This application is made for changing Kinect webcam settings (tested on Kinect v2, may work on Kinect v1 and Azure Kinect)

The app is based on [MixedRealityCompanionKit](https://github.com/microsoft/MixedRealityCompanionKit/tree/master/KinectIPD)
### About

This application allows you to modify and customize the default Kinect settings, such as:

* Exposure (Auto/Manual)
* White Balance (Auto/Manual)

By default, Kinect operates in automatic mode and adjusts exposure, white balance, and frame rate depending on the light conditions. In most cases, there is not enough light in the room, resulting in overexposed images. Kinect, trying to adjust the image brightness to reference values, increases the exposure and thereby reduces the number of frames. This makes using Kinect as a webcam almost impractical.

I faced this problem when I started live streaming on Twitch. At first, I didn't pay much attention to it, but over time I wanted to improve the image quality. In search of a solution I came across the [MixedRealityCompanionKit](https://github.com/microsoft/MixedRealityCompanionKit/tree/master/KinectIPD). This is a set of solutions for various tasks related to Kinect.

In the original project, exposure level was implemented in the camera settings to calibrate the image. However, using the original project every time was inconvenient: the program is quite heavy and difficult to use for calibration, and using it just to configure the Kinect every time was pointless. Since this is an Open Source solution, I decided to create my own app or "shell" with the necessary functions based on those libraries.


# How to use
![4.png](img/4.png)

There are several parameters you can change:

* **Exposure level**
  * Switching exposure levels from automatic mode to manual mode. It will allow you to manually set the exposure level.
  * In manual mode, set the value depending on the light conditions. A value from 0 to about 25.00 does not affect on FPS. The value greater than 25.00 drops FPS from 30fps to 10-15 frames per second!
   
    >I think 15.00-17.00 is perfect.
* **White Balance**
  * Switching white balance from automatic to manual. This will allow you to manually set the balance level using the RGB values.
  * In manual mode, adjust  the picture color to desire one. The values themselves don't mean anything but depend on each other, this is just for reference.
  * To get reference values just switch back to auto mode for a second.
    
* **Next time launch**
  * You can run the application without the HUD (interface) using the saved settings. The application will apply the saved settings to the Kinect and then shut down itself. This is useful for simplifying camera setup. To open it again with HUD you will need to change the first line to "False" in the "Settings.txt" file.
  
![5.png](img/5.png)

 * **"Save" Button**
   * You can save the settings and they will be applied next time after launching the app.
  


# How to Install
This application requires the additional installation of certain components.
The application itself is a standalone folder with .exe file inside (and bunch of other files). Just unpack this folder to any location and create a shortcut for ease of use.

To be able to use this app with your Kinect you need to install 2 things:

**1. KinectRuntime Driver**
 * It should be installed by default after connecting the Kinect. If it's not happend just run KinectRuntime-.x64 or on the Device Manager, for the kinect device, look for new drivers and set this folder.

![6.png](img/6.png)

**2. Desktop Development with C++ (whatever that means).**
  * To install it, I guess you need to install Visual Studio. At least, it's the easy way to do so. After the Visual Studio installation, open the Start menu and run "Visual Studio Installer." Click "Modify", then choose "Desktop Development with C++" and click "Install" or "Modify." Done!
    
![1.png](img/1.png)
![2.png](img/2.png)
![3.png](img/3.png)

After all these steps, you can launch the application.
> [!CAUTION]
> **Attention!!! Your Kinect must be active!** Just open any video capture app, like the default Windows Camera app or OBS.
