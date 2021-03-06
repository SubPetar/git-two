# Adaptive Trajectory Refinement for SLAM

This branch contains the code and the report of Master Thesis: "Adaptive Trajectory Refinement for SLAM" done at Vision for Robotics Lab (V4RL) by Petar Subotic. It represents 
adaptation of master repository "Spline-Based Direct IMU Integration for SLAM".

New folder, ./ATR_CODE/Adaptive_trajectory_Refinement_woBias/ is based on folder CT_SLAM_woBias from master repository which **does not** estimate IMU biases. Furthermore, in current implementation, 
landmark positions in space (3D) are fixed and are **not updated**.

In ./ATR_CODE/Functions/ , functions for creating non-uniform cubic B-splines are located, which are used in ./ATR_CODE/Adaptive_trajectory_Refinement_woBias/preprocessing_woBias.m . 

In folder ./ATR_CODE/Adaptive_trajectory_Refinement_woBias/, three scripts can be found for running three different strategies:

```
main_woBias_Insertion_strategy.m
```

,

```
main_woBias_Removal_strategy.m
```

and

```
main_woBias_Interlined_strategy.m
```

**Insertion strategy** iteratively adds one contol pose and optimized trajectory. **Removal strategy** iteratively removes one control pose and optimizes the trajectory. **Interlined strategy** iteratively 
removes one control pose and optimizes the trajectory and afterwards inserts one control pose and optimizes the trajectory.

For **Insertion strategy** and **Interlined strategy**, in **__INSERTION PARAMETERS__** section, we can choose between three different insertion methods:

- Middle insertion

- Center of residual mass

- Maximal residual

by changing __choose_pose_per_segment_method__ to 'middle', 'center_of_residual_mass' and 'maximal_residual'. Other Insertion parameters 
should be left with their default values.

In order to run aforementioned scripts, different parameters can be set at the beginning of the file. 
All the *paths* to the different data-files need to be changed in order to run the scripts on another machine. 

In order to run the scripts, the [EuRoc Dataset](https://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets) needs to be downloaded and visual data needs to be created by firstly creating landmarks using

```
creatWall.m
```
and then using
```
main_slam_simulator.m
```
to create camera frames along the trajectory. Both files are located in the folder ./ATR_CODE/Simulator/. 


Additionally, some less relevant scripts  e.g., for plotting and manually created detasets for different strategies can be located 
on this [link](https://drive.google.com/file/d/1H8i8pVSwMgpUySW8B-9_3H9HuaMZr6V6/view?usp=sharing) 





