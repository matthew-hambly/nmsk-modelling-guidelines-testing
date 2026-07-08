---
title: Home
layout: home
nav_order: 1
---

# Data Processing and NMSK Modelling Guidelines

Details for the below topics can be found by clicking on the link or in the corresponding directory. It is strongly suggested to follow a [standard folder structure](./fundamentals/suggested_folder_structure.md).

## [1. Data collection and synchronisation](1_data_collection.md)
* [Markers](1_data_collection/markers.md)
    * [Markerset Guide](1_data_collection/markerset_guide.md)
* [EMG](1_data_collection/emg.md)
    * [HD-EMG](1_data_collection/hd_emg.md)
* [Force plates](1_data_collection/force_plates.md)
* [IMU](1_data_collection/imu.md)
* [Markerless](1_data_collection/markerless.md)
* [Sampling frequencies](1_data_collection/sampling_frequencies.md)
* [Synchronisation](1_data_collection/synchronisation.md)

## [2. Preprocessing](2_preprocessing/README.md)
* [Marker trajectory processing and gap filling](2_preprocessing/marker_trajectory_processing_and_gap_filling.md)
* [Filtering choices and rationales for kinematics and kinetics](2_preprocessing/filtering_choices_and_rationales_for_kinematics_and_kinetics.md)
* [Coordinate systems and conventions](2_preprocessing/coordinate_systems_and_conventions.md)
* [Force-plate processing](2_preprocessing/force_plate_processing.md)
* [EMG preprocessing](2_preprocessing/emg_preprocessing.md)
    * [Muscle synergies](2_preprocessing/muscle_synergies.md)

## [3. Musculoskeletal modelling](3_msk_modelling/README.md)
* [Model scaling and personalisation](3_msk_modelling/model_scaling_and_personalisation.md)
* [Inverse kinematics](3_msk_modelling/inverse_kinematics.md)
* [Muscle analysis](3_msk_modelling/muscle_analysis.md)
* [Inverse dynamics](3_msk_modelling/inverse_dynamics.md)
* [Joint reaction analysis](3_msk_modelling/joint_reaction_analysis.md)

## [4. Neuromusculoskeletal modelling](4_nmsk_modelling/README.md)
* [CEINMS](4_nmsk_modelling/CEINMS/README.md)
    * [CEINMS-NN](4_nmsk_modelling/CEINMS/ceinms_nn.md)
    * [CEINMS-WEB](4_nmsk_modelling/CEINMS/ceinms_web.md)
    * [CEINMS-RT](4_nmsk_modelling/CEINMS/ceinms_rt.md)
* [Model initialisation and tuning](4_nmsk_modelling/model_initialisation_and_tuning.md)
* [Model calibration](4_nmsk_modelling/model_calibration.md)
* [Execution](4_nmsk_modelling/execution.md)
    * [EMG-driven](4_nmsk_modelling/execution_emg_driven.md)
    * [EMG-hybrid/assisted](4_nmsk_modelling/execution_emg_hybrid.md)
    * [Static optimisation](4_nmsk_modelling/execution_static_optimisation.md)

## [Fundamentals](fundamentals/README.md)
* [Conventions](fundamentals/conventions.md)
* [File Types](fundamentals/file_types.md)
* [Software Tools](fundamentals/software_tools.md)
* [Standard Folder Structure](./fundamentals/suggested_folder_structure.md)

```mermaid
%%{init: {
  "theme": "base",
  "themeVariables": {
    "fontFamily": "Arial, sans-serif",
    "fontSize": "15px",
    "primaryTextColor": "#0F172A",
    "lineColor": "#64748B",
    "clusterBkg": "#F1F5F9",
    "clusterBorder": "#CBD5E1"
  }
}}%%

flowchart LR
 
 subgraph data_collection["`**Data collection**`"]
        markers["Markers"]
        imu_collection["IMU"]
        markerless_collection["Video"]
        emg_collection["EMG"]
        force_plate_collection["Force plates"]
  end

 subgraph preprocessing["`**Preprocessing**`"]
        marker_trajectory["Marker trajectory labelling, gap filling, and filtering"]
        force_plate_processing["Force-plate filtering"]
        emg_processing["EMG normalisation and filtering"]
        imu_processing["IMU filtering"]
        markerless_processing["Pose estimation"]
  end

 subgraph msk_model["`**Musculoskeletal modelling (OpenSim)**`"]
        model_scaling["Model scaling and personalisation"]
        inverse_kinematics["Inverse kinematics (markers or OpenSense)"]
        inverse_dynamics["Inverse dynamics"]
        muscle_analysis["Muscle analysis"]
  end

 subgraph nmsk_model["`**Neuromusculoskeletal modelling (CEINMS)**`"]
    direction LR
        model_cal["Model calibration"]
        nmsk_exec["Execution"]
  end

    markers --> marker_trajectory
    emg_collection --> emg_processing
    force_plate_collection --> force_plate_processing
    imu_collection --> imu_processing
    markerless_collection --> markerless_processing

    marker_trajectory --> model_scaling
    markerless_processing --> model_scaling
    model_scaling --> inverse_kinematics
    inverse_kinematics --> muscle_analysis & inverse_dynamics
    force_plate_processing --> inverse_dynamics

    muscle_analysis --> model_cal
    inverse_dynamics --> model_cal
    emg_processing --> model_cal
    model_cal --> nmsk_exec
```




----
