# schunk_description Project

## Introduction

The `schunk_description` project hosts the URDF (Unified Robot Description Format) models for the SCHUNK EGU 50 gripper. This document provides instructions on how to modify and utilize the provided models, especially concerning the replacement of finger models on the EGU 50 gripper.

## Package Structure

- **egu_50_description**: This package contains the URDF model files for the EGU 50 gripper.
  - **urdf**: Directory containing xacro files for different components.
    - `egu_50_base_link.xacro`: Base model of EGU 50 gripper without fingers.
    - `egu_50_fingers_link.xacro` and `egu_50_fingers_version2_link.xacro`: Different finger models for EGU 50 gripper.
  - **meshes**: Directory to place the mesh files for custom fingers.

## Customizing Fingers

To replace the fingers on the EGU 50 model, follow the steps below:

1. **Creating Finger Xacro Files**:
   - Create your own xacro files for the new fingers, referencing the structure and contents from `egu_50_fingers_link.xacro` or `egu_50_fingers_version2_link.xacro` as needed.
   
2. **Placing the Files**:
   - Place your created xacro file(s) in the `egu_50_description/urdf` directory.
   - Place corresponding mesh files in the `egu_50_description/meshes` directory.

3. **Naming Conventions**:
   - Ensure the base link names in your xacro files are `${prefix}base_link_left` and `${prefix}base_link_right`.

4. **Updating the Main Xacro File**:
   - Open `egu_50.xacro` file.
   - Replace the line:
     ```xml
     <xacro:include filename="$(find egu_description)/urdf/egu_50_fingers_version2_link.xacro"/>
     ```
     with your own finger xacro file name.
   - In the instantiation section, update the model name accordingly:
     ```xml
     <xacro:egu_50_fingers_version2_link prefix="${prefix_2}_" meshType="STL" />
     ```
     - If your mesh file is in `.dae` format, replace `STL` with `${meshType}`, for other formats, replace `STL` with the appropriate format (e.g., `stl`).

## Enabling Mimic Joint Functionality in Gazebo

The package utilizes the MimicJointPlugin for Gazebo to enable the mimic joint functionality. To activate this feature:

1. Clone the repository from [roboticsgroup_upatras_gazebo_plugins](https://github.com/roboticsgroup/roboticsgroup_upatras_gazebo_plugins.git) into your workspace.
2. Compile the plugin in your workspace to enable the mimic joint functionality in Gazebo.

## Conclusion

With the above steps, you should be able to customize the finger models on the EGU 50 gripper and utilize the mimic joint functionality in Gazebo. For any issues or further inquiries, feel free to open an issue in this repository.
