# Ros-noetic-SingleLineCommand-Installation
# Installing ROS Noetic on Ubuntu

This guide provides step-by-step instructions to install ROS (Robot Operating System) Noetic on Ubuntu and verify the installation.

## Installation Steps

1. **Open a Terminal**

   Open a terminal in Ubuntu by pressing `Ctrl + Alt + T` or searching for "Terminal" in the application menu.

2. **Run the Installation Command**

   Copy and paste the following command into the terminal and press `Enter`:

   ```bash
   sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' && sudo apt install curl && curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add - && sudo apt update && sudo apt install ros-noetic-desktop-full && source /opt/ros/noetic/setup.bash
   ```

   This command:
   - Adds the ROS repository to your system’s sources list.
   - Installs `curl` (if not already installed).
   - Downloads and adds the ROS public key.
   - Updates the package list.
   - Installs the full ROS Noetic desktop package.
   - Sources the ROS setup script to configure your environment.

3. **Handle Prompts**

   During the installation, if prompted with a `(Y/N)` question (e.g., to confirm package installation), type `Y` and press `Enter` to proceed.

## Verify Installation

After the installation completes, verify that ROS Noetic is installed correctly by following these steps:

1. **Check ROS Version**

   Run the following command in the terminal to verify the ROS version:

   ```bash
   rosversion -d
   ```

   **Expected Output**:
   ```
   noetic
   ```

2. **Run ROS Master**

   Start the ROS master by running:

   ```bash
   roscore
   ```

   If the installation was successful, you should see output similar to the following:

   ```
   ... logging to /home/user/.ros/log/xxxx...
   Checking log directory for disk usage. This may take a while.
   Press Ctrl-C to interrupt
   started roslaunch server http://localhost:42471/
   ros_comm version 1.14.13
   ...
   started core service [/rosout]
   ...
   ```

   To stop the ROS master, press `Ctrl + C` in the terminal.

## Notes

- Ensure your Ubuntu version is compatible with ROS Noetic (typically Ubuntu 20.04 Focal Fossa).
- If you encounter issues, ensure your system is up-to-date by running `sudo apt update && sudo apt upgrade` before starting the installation.
- To use ROS in every new terminal session, add the following line to your `~/.bashrc` file:

  ```bash
  source /opt/ros/noetic/setup.bash
  ```

  You can do this by running:

  ```bash
  echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
  ```

Congratulations! You have successfully installed and verified ROS Noetic on your Ubuntu system.
