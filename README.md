# Unity3D_Configuration
This is a central repository for tools, tutorials, resources, and documentation for the Digital-Twin Chemworkcell in Unity.
____
The contents of this repository are in development.
___
## Requirements
### Software
    Unity Hub, Unity3D 2020.3.11f1, Universal Robots Polyscope, VMware Workstation pro14, Python 3, ROS Noetic, Visual Studio
### Environment
    Windows, Unbuntu20.04, URsim
### Components Repos
Repo | Functionality
---- | ----
[ROS TCP EndPoint](https://github.com/Unity-Technologies/ROS-TCP-Connector) | ROS node for sending/receiving messages from Unity
[ROS TCP Connector](https://github.com/Unity-Technologies/ROS-TCP-Connector) | Unity package for sending, receiving, and visualizing messages from ROS
[URDF Importer](https://github.com/Unity-Technologies/URDF-Importer) | Unity package for loading URDF files
[XCharts](https://github.com/XCharts-Team/XCharts) | Unity package for configurable charting and data visualization
## Quick Installation Instructions
### Unity3D Side
Install `Unity Hub` and `Unity3D`, then you need to add the `Workcell_DT` file to `Unity Hub` which cloned from this Repo.After opening `Unity Hub`, find the `Add`button in the project column, `click Add`, find the `workcell_DT` file, select it and click `SelectFile`.Note: When you open the project without any packages, the system will comes out the wrong window, always `ignore` it.<br><br>
After openning the `workcell_DT` project, Open `Window` -> `Package Manager`, In the Package Manager window, find and click the `+` button in the upper lefthand corner of the window. Select `Add package from git URL...`.Enter the git URL for the desired package. 
>For the [ROS-TCP-Connector](https://github.com/Unity-Technologies/ROS-TCP-Connector), enter `https://github.com/Unity-Technologies/ROS-TCP-Connector.git?path=/com.unity.robotics.ros-tcp-connector`<br><br>
>For the [URDF-Importer](https://github.com/Unity-Technologies/URDF-Importer), enter `https://github.com/Unity-Technologies/URDF-Importer.git?path=/com.unity.robotics.urdf-importer`.<br><br>
>For the [XCharts](https://github.com/XCharts-Team/XCharts), install from a local clone of the repository, clone the [XCharts2.0](https://github.com/XCharts-Team/XCharts/tree/2.0),In the Package Manager window, find and click the `+` button in the upper lefthand corner of the window. Select `Add package from local package...`.Then find the cloned `XCharts2.0`package -> `Asset` -> `package.json` file.
### URsim Side
First, you need to check the `IP address` of URsim. After opening the `URsim UR3` interface, click the `About` button to find the IP Address. <br>
Then enter the IP in the `Connect Panel` on the Unity side to connect.
### Ros Side
The ROS TCP connection needs to be created. Select `Robotics` -> `ROS Settings` from the top menu bar.<br>
In the ROS Settings window, the `ROS IP Address` should be the IP address of your ROS machine.<br>
Find the IP address of your ROS machine. In Ubuntu, open a terminal window, and enter `hostname -I`.<br><br>
Clone `ROS_UNITY` in Ubuntu20.04, then create the workstation `catkin_make && source devel/setup.bash`<br>If you are in scene `ur3control`. Open a new terminal, navigate to your Catkin workspace, and run:<br>
        `source devel/setup.bash`
        `roslaunch ros_tcp_endpoint endpoint.launch`<br>
Then It will connect the Unity Side, and communicate with each other.



