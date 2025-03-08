Below are step‐by‐step instructions for installing ROS 2 Humble Hawksbill on Ubuntu 22.04:

---

### 1. Set Up Your Sources List

Open a terminal and add the ROS 2 repository to your apt sources:

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'
```

---

### 2. Install Required Packages

Make sure your system has the required packages for managing repositories and HTTPS:

```bash
sudo apt update
sudo apt install curl gnupg lsb-release
```

---

### 3. Add the ROS 2 GPG Key

Import the repository key to authenticate packages:

```bash
curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

*Note:* While `apt-key` is deprecated in some contexts, these steps are still standard for ROS installation. Future updates to the ROS docs may suggest alternative key management methods.

---

### 4. Update Your Package Index

Refresh your apt package index to recognize the new repository:

```bash
sudo apt update
```

---

### 5. Install ROS 2 Humble

Choose the installation variant that best suits your needs. For a complete desktop installation (which includes demos and examples), run:

```bash
sudo apt install ros-humble-desktop
```

If you prefer a smaller install (bare-bones), you can install just the base packages:

```bash
sudo apt install ros-humble-ros-base
```

---

### 6. Set Up the Environment

To ensure that ROS 2 commands are available in your terminal, source the setup script:

```bash
source /opt/ros/humble/setup.bash
```

For convenience, you can add this command to your `~/.bashrc`:

```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

---

### 7. Verify the Installation

Test that ROS 2 is properly installed by running a demo node, for example:

```bash
ros2 run demo_nodes_cpp talker
```

If the node starts without errors, your installation was successful.

---

These steps should install ROS 2 Humble on Ubuntu 22.04. For further details or troubleshooting, refer to the [official ROS 2 installation guide](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html).