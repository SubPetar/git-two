# Adaptive Trajectory Refinement for SLAM

This branch contains the code and the report of Master Thesis: "Adaptive Trajectory Refinement for SLAM" done at Vision for Robotics Lab (V4RL) by Petar Subotic. It represents 
adaptation of master repository "Spline-Based Direct IMU Integration for SLAM".

New folder, Adaptive_Trajectory_Refinement_woBias is based on folder CT_SLAM_woBias which **does not** estimate IMU biases. Furthermore, in current implementation, 
landmark positions in space (3D) are fixed and are **not updated**.

In folder Adaptive_Trajectory_Refinement_woBias, three scripts can be found for running three different strategies:

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

**Insertion strategy** iteratively adds new contol pose and optimized trajectory. **Removal strategy** iteratively removes one control pose and optimizes the trajectory. *Interlined strategy* iteratively 
removes one control pose and optimizes and afterwards inserts one control pose and optimizes the trajectory.

For **Insertion strategy** and *Interlined strategy*, in **__INSERTION PARAMETERS__**, we can change three different insertion methods:

- Middle insertion

- Center of residual mass

- Maximal residual

by changing __choose_pose_per_segment_method__ to 'middle', 'center_of_residual_mass', 'maximal_residual'. Other Insertion parameters should have their mentioned defiend values;


