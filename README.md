![Robotic Desktop Workspace](https://github.com/morganrivers/spatial_computing/blob/main/DALL%C2%B7E%202025-03-22%2013.34.45%20-%20A%20high-tech%20workspace%20featuring%20a%20pair%20of%20SO-100%20robotic%20arms%20with%20precise%20pincers%2C%20actively%20organizing%20printed%20pieces%20of%20paper%20and%20small%203D-printed%20c.webp?raw=true)

# Robotic Desktop Workspace: Integrating Spatial Computing with Robotic Arms

Please note the image and most of the text below are edited responses from ChatGPT formulating my ideas, proceed with caution! This repo is currently meant as an inspiration and brainstorm, rather than a fully-thought out project framwork.

## Overview
This project explores the integration of spatial computing environments (inspired by Dynamicland and [folk.computer](https://folk.computer/)) with robotic manipulation capabilities provided by SO-100 robotic arms. The core idea is to extend traditional desktop computing beyond screens into interactive, physical-digital hybrid spaces.

Imagine your desk as a dynamic workspace where documents, objects, and digital information coexist and interact seamlessly, manipulated by robotic arms that organize, construct, and respond to user interactions.

The cost of the system should be quite accessible: at $115 an arm, a dual-arm setup costs only $230. For other hardware recommendations see ([folk.computer](https://folk.computer/pilot)). For the projector, the AAXA P400 ($269) is a good option for a portable 1080p projector. Logitech C922 is a good camera option at $100 a camera.

## Vision
We aim to:

- Create a tangible computing environment bridging digital projection, physical objects, and robotic manipulation.
- Facilitate novel interaction paradigms such as remote physical collaboration, interactive 3D websites, on-demand physical object construction (via 3D printing), and intelligent document organization.
- Push computing beyond the screen into a physically embodied and interactive environment.
- Bring people together. Computing can be open and collaborative, interaction with computing systems can allow for parallel input. We can start to interact in the same physical space with computing more effectively.

## Applications

### Initial Applications
The initial practical applications we envision include:

1. **Document Management System**
   - Papers placed on a physical desk are automatically recognized (via QR codes and computer vision)
   - Robotic arms organize documents into binders
   - Documents can be returned to their original spatial arrangement when needed

2. **Remote Physical Board Games**
   - Play chess or go with someone on the other side of the world
   - When a remote player places a piece, the robotic arm physically moves it on your board
   - Creates a tangible, physical gaming experience despite geographic separation

3. **Collaborative Remote Play**
   - Interactive games like pong played on your physical desk
   - Physical elements manipulated by robotic arms based on remote player actions
   - Projection mapping enhances the gaming experience with visual feedback

4. **3D Physical Websites**
   - Websites represented as physical 3D structures on your desk
   - Built using 3D printed pieces or standard shapes arranged by robotic arms
   - Interactive elements respond to physical manipulation detected by cameras
   - Blend of digital projection and physical objects to create immersive browsing

5. **Interactive Learning Tools**
   - When doing math on paper, request help and have the correct equations projected or drawn by the robotic arm
   - Physical manipulatives for educational concepts arranged by arms and enhanced with projection
   - Camera-based detection of user interactions with physical objects

6. **Musical Instrument Construction**
   - Robotic arms can build 3D printed instruments like pianos
   - Camera detects when the constructed instrument is played
   - System responds with sounds, visual feedback, or further interactions

Some ideas don't require 3d printing:
  
7. **Internet browsing**
   - Imagine a physical binder with the Internet in it! You pull papers out and see the associated websites.

8. **Email**
   - I have an inbox for mail that shows how much there is. I can move the sheet of paper to the table and see the message projected on it. I move it to read or deleted. I can also reply as normal. Each sheet gets a unique mail item.

9. **Coding**
    - Projecting such a high-dimensional activity as tracing through software stacks and folder directory demands a 3 dimensional workspace. Multiple Levels can be assembled on your desktop with papers corresponding to different layers of your software stack. Coding can start to use your visual, spatial, and tactile intelligence and memory more effectively. 
     
## Software Stack
The preliminary software stack includes:

- Base System
  - **OS**: Ubuntu Server 24.04 LTS as recommended for Folk Computer
  - **Folk Computer Framework**: [FolkComputer/folk GitHub repo](https://github.com/FolkComputer/folk) which provides the reactive database, programming environment, and projection mapping capabilities

- Robotic Arm Control
  - **ROS2 Framework**: [ROS2 Jazzy Jalisco](https://www.ros.org/) the latest LTS release with Ubuntu 24.04 support
  - **SO-100 ROS2 Driver**: [brukg/SO-100-arm](https://github.com/brukg/SO-100-arm) providing ROS2 support for the SO-100 robot with URDF models, Gazebo simulation, and MoveIt2 integration
  - **ROS2 Control Packages**: ros2-control, ros2-controllers, and MoveIt for motion planning

- Computer Vision & Spatial Awareness (Logitech C922 Optimized)
  - **OpenCV with C922 Configuration** for image processing and computer vision
  - **AprilTag Library**: [AprilRobotics/apriltag](https://github.com/AprilRobotics/apriltag) for robust fiducial marker detection with Python bindings
  - **Custom gesture and object recognition pipeline** for interactive applications

- Integration Layer
  - **Folk-ROS2 Bridge**: Custom Python modules for bidirectional communication
  - **Spatial Programming Interface**: Lua-based scripting integrated with Folk for creating spatial programs
  - **Projection Mapping Tools**: Calibration and mapping software for the AAXA P400 projector

## Detailed Hardware Stack

- **Robotic Arms**: [SO-100/SO-ARM100](https://github.com/TheRobotStudio/SO-ARM100) - An open-source robotic arm with 6 degrees of freedom and high-torque servo motors that can be controlled via ROS2 with both 5-DOF and 7-DOF configurations available

- **Computing Platform**: 
  - [Beelink SER5 or Mini S12 mini PC](https://folk.computer/pilot) as recommended by Folk Computer for optimal performance (60fps vs 5-15fps on Raspberry Pi)
  - Alternatively: NVIDIA Jetson platform for AI-enhanced capabilities which works well with the SO-ARM100 and supports the LeRobot AI framework

- **Projector**: AAXA P400 ($269) for portable 1080p projection mapping

- **Camera**: Logitech C922 ($100) with 1080p resolution and good low-light performance

- **Optional**: 3D printer for creating custom physical components that can be manipulated by the robotic arms

## Future Directions
Potential expansions of this project include:

- Multi-user simultaneous physical-digital collaboration spaces
- Integration with large language models for conversational interfaces that control physical manipulation
- Advanced haptic feedback mechanisms
- Computer vision-powered design tools that blend physical modeling with digital precision
  
## Repository Structure (Placeholder)
This repository currently serves as a placeholder and brainstorming space. Future implementations, documentation, code, and resources related to the integration of spatial computing and robotic arms will be provided here.

## Contributions
While this is currently a placeholder project, future collaboration is encouraged. Please reach out or open an issue to discuss ideas, potential contributions, or questions.
