<h1 align="center">OpenRoSDE</h1>

<p align="center">
  <strong>The open-source Software Development Environment (SDE) for collaborative research in robotic system integration</strong><br>
  One containerized environment for every contributor, in simulation or on the real robot.
</p>

<p align="center">
  <a href="https://doi.org/10.1080/01691864.2022.2068353"><img src="https://img.shields.io/badge/paper-10.1080%2F01691864.2022.2068353-4F46E5" alt="Paper DOI: 10.1080/01691864.2022.2068353"></a>
  <a href="https://www.apache.org/licenses/LICENSE-2.0"><img src="https://img.shields.io/badge/license-Apache--2.0-2E5C8A" alt="License: Apache-2.0"></a>
  <a href="https://www.docker.com/"><img src="https://img.shields.io/badge/Docker-containerized-2496ED?logo=docker&logoColor=white" alt="Containerized with Docker"></a>
  <a href="https://wiki.ros.org/noetic"><img src="https://img.shields.io/badge/ROS-Noetic-22314E?logo=ros&logoColor=white" alt="ROS Noetic"></a>
  <a href="https://docs.ros.org/en/lyrical/"><img src="https://img.shields.io/badge/ROS%202-Lyrical-22314E?logo=ros&logoColor=white" alt="ROS 2 Lyrical"></a>
  <a href="https://openrosde.org/"><img src="https://img.shields.io/badge/website-openrosde.org-4E7A38" alt="Website: openrosde.org"></a>
</p>

<p align="center">
  <a href="https://openrosde.org/">Website</a> ·
  <a href="https://github.com/openrosde/openrosde">OpenRoSDE Repository</a> ·
  <a href="https://openrosde.org/docs/getting-started/quick-start">Quick Start</a> ·
  <a href="https://doi.org/10.1080/01691864.2022.2068353">Advanced Robotics Paper</a> ·
  <a href="https://github.com/openrosde/openrosde/blob/main/CONTRIBUTING.md">Contributing Guide</a> ·
  <a href="https://coarobo.com/">Coarobo GK</a>
</p>

---

## 🔍 Overview

OpenRoSDE, read "Open Robotic SDE", is the open-source reference implementation of the Software Development Environment (SDE) described in "**Software Development Environment for Collaborative Research Workflow in Robotic System Integration**" (DOI: [10.1080/01691864.2022.2068353](https://doi.org/10.1080/01691864.2022.2068353)).
The whole OpenRoSDE is containerized with [Docker](https://www.docker.com/), so all the contributors work in the exact same software environment.
Its robot, simulator, visualization, and behavior interfaces are primarily implemented with ROS, Gazebo, RViz, and FlexBE.

- **Three image layers**: `openrosde-base` holds the shared toolchain, `<platform>-devel` adds one robot, and `user-devel` holds the user overlay, where you add your own packages without forking OpenRoSDE.
- **Extensions**: each platform and each device lives in a repository of its own, public or private, which OpenRoSDE finds by name once it is cloned into `extensions/`.
- **ROS 1 & ROS 2**: each platform declares the ROS it runs, ROS Noetic on Ubuntu 20.04 or ROS 2 Lyrical on Ubuntu 26.04, side by side.
- **Robot models for any client**: `rosbridge` serves the robot description and every mesh as a GLB to web and Unity applications.
- **A CI that never moves a robot**: every setup is built, then checked in a container disconnected from every network.

## 📦 Repositories

| Repository                                                        | Role          | Description                                                                                     |
| ----------------------------------------------------------------- | ------------- | ----------------------------------------------------------------------------------------------- |
| [**openrosde**](https://github.com/openrosde/openrosde)           | Core          | Entry scripts, shared Docker images of ROS 1 and ROS 2, shared workspaces, user overlay, and CI |
| [**openrosde-docs**](https://github.com/openrosde/openrosde-docs) | Documentation | Source of the [openrosde.org](https://openrosde.org/) website and documentation                 |
| [**.github**](https://github.com/openrosde/.github)               | Organization  | This profile and the community health files of every repository                                 |

### Robot Platforms

Each platform holds one robot as sold, with its public drivers, and is cloned into `extensions/` of the core.

| Repository                                                                                      | Platforms                       | Robot                            | ROS                         |
| ----------------------------------------------------------------------------------------------- | ------------------------------- | -------------------------------- | --------------------------- |
| [**openrosde-platform-cobotta**](https://github.com/openrosde/openrosde-platform-cobotta)       | `cobotta`                       | Denso COBOTTA                    | ROS 1 Noetic                |
| [**openrosde-platform-fetch**](https://github.com/openrosde/openrosde-platform-fetch)           | `fetch`                         | Fetch Robotics Fetch             | ROS 1 Noetic                |
| [**openrosde-platform-hsr**](https://github.com/openrosde/openrosde-platform-hsr)               | `hsr`                           | Toyota HSR (Human Support Robot) | ROS 1 Noetic                |
| [**openrosde-platform-sciurus17**](https://github.com/openrosde/openrosde-platform-sciurus17)   | `sciurus17`                     | RT Sciurus17                     | ROS 1 Noetic                |
| [**openrosde-platform-turtlebot3**](https://github.com/openrosde/openrosde-platform-turtlebot3) | `turtlebot3`, `turtlebot3-ros2` | Robotis TurtleBot3 (Waffle Pi)   | ROS 1 Noetic, ROS 2 Lyrical |
| [**openrosde-platform-ur5e**](https://github.com/openrosde/openrosde-platform-ur5e)             | `ur5e`                          | Universal Robots UR5e            | ROS 1 Noetic                |

### Devices

Each device holds one upstream driver of hardware anyone can buy, with every model that driver supports, and is activated by the setup of a robot.

| Repository                                                                                | Hardware                                                                   |
| ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| [**openrosde-device-onrobot**](https://github.com/openrosde/openrosde-device-onrobot)     | The OnRobot RG and VG grippers                                             |
| [**openrosde-device-realsense**](https://github.com/openrosde/openrosde-device-realsense) | The RealSense cameras                                                      |
| [**openrosde-device-spacenav**](https://github.com/openrosde/openrosde-device-spacenav)   | Every 3Dconnexion device that `spacenavd` supports, such as the SpaceMouse |

## 🚀 Quick Start

```shell
git clone https://github.com/openrosde/openrosde.git && cd openrosde/
bash ./SETUP-DEVEL-MACHINE.bash
sudo reboot
```

Then follow the [Quick Start](https://openrosde.org/docs/getting-started/quick-start) to clone a platform, build the Docker image, and open a first session on it.

## 📄 Citing OpenRoSDE

If OpenRoSDE supports your research, please cite the paper that describes it:

L. El Hafi, G. A. Garcia Ricardez, F. von Drigalski, Y. Inoue, M. Yamamoto, and T. Yamamoto, "**Software Development Environment for Collaborative Research Workflow in Robotic System Integration**", in *RSJ Advanced Robotics (AR), Special Issue on Software Framework for Robot System Integration*, vol. 36, no. 11, pp. 533-547, Jun. 3, 2022.
DOI: [10.1080/01691864.2022.2068353](https://doi.org/10.1080/01691864.2022.2068353)

[https://openrosde.org/docs/project/citing](https://openrosde.org/docs/project/citing) gives its BibTeX entry and the related publications.

## 🤝 Get Involved

- Read the [contributing guide](https://github.com/openrosde/openrosde/blob/main/CONTRIBUTING.md), which also describes how to add a new robot platform.
- Report a problem in the repository concerned, such as the [issues of the core](https://github.com/openrosde/openrosde/issues).
- Report a security vulnerability privately, as the [security policy](https://github.com/openrosde/.github/blob/main/SECURITY.md) describes.
- Follow the [Code of Conduct](https://github.com/openrosde/.github/blob/main/CODE_OF_CONDUCT.md) in every space of the project.

## ⚖️ License

OpenRoSDE is released under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) and maintained by [Coarobo GK](https://coarobo.com/).
The versions before 3.0.0 were published under the MIT License, and their archive remains at [https://gitlab.com/coarobo/SDE](https://gitlab.com/coarobo/SDE).
