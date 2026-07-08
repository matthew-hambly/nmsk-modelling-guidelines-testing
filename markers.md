---
title: Markers
parent: Data collection
nav_order: 1
layout: default
---

# Markers

Marker quality is part of model validity. In CEINMS workflows, marker trajectories provide the movement information used for model scaling, inverse kinematics, inverse dynamics, muscle-tendon lengths, and moment arms. Errors introduced at this level can propagate through the full pipeline and may not be recoverable during post-processing or calibration.

Marker-based optical motion capture is the laboratory reference method for quantitative movement analysis, but skin-mounted markers are not direct measurements of bone motion. Their validity depends on camera calibration, marker placement, visibility, soft-tissue artefact, labelling consistency, and mechanical stability.

A trial that can be labelled, exported, and processed is not necessarily a valid modelling trial.

---

## Measurement principle

Optical motion capture reconstructs three-dimensional marker trajectories from multiple calibrated camera views. The system tracks reflective markers; bone motion is inferred later through anatomical assumptions, marker-set definitions, and musculoskeletal model constraints.

A marker trajectory may be smooth and complete while still being mechanically misleading.

Marker-based modelling combines:

- camera-based reconstruction of external markers;
- anatomical interpretation of marker locations;
- model-based estimation of segment and joint motion.

Poor data at any layer can affect downstream modelling.

---

## Marker role in CEINMS workflows

Marker trajectories are commonly used upstream of CEINMS for:

- model scaling;
- anatomical landmark calibration;
- inverse kinematics;
- inverse dynamics, when external force data are available;
- muscle-tendon length and moment-arm computation;
- preparation of CEINMS calibration and execution inputs.

Marker errors do not remain local. A small marker-placement or tracking error may alter segment pose, joint kinematics, angular velocity, inverse dynamics moments, muscle-tendon lengths, and moment arms.

CEINMS calibration can compensate for some parameter uncertainty, but it cannot rescue fundamentally incorrect kinematics or inconsistent joint moments.

> Control marker errors at the source. Do not rely on gap filling, smoothing, inverse kinematics, or calibration to repair poor measurement quality.

---

## Model compatibility

Markers must be compatible with the anatomical coordinate systems and degrees of freedom of the musculoskeletal model. Their role is not merely to provide visible points, but to provide sufficient information to reconstruct anatomical segment motion in a form the model can interpret.

Detailed guidance on marker-set selection is provided in [Selecting a markerset]({% link markerset_guide.md %}).

A marker set should provide:

- repeatable anatomical landmark definition;
- stable segment tracking;
- compatibility with model coordinate systems;
- sufficient information for the target movement;
- robustness to occlusion and soft-tissue artefact.

More markers do not automatically improve data quality. Additional markers are useful only when they provide interpretable, model-compatible information.

---

## Marker types

### Anatomical markers

Anatomical markers are placed on palpable landmarks. They define segment dimensions, joint centres, and anatomical coordinate systems, especially during static calibration. Placement errors create systematic errors that may affect all dynamic trials.

### Tracking markers

Tracking markers track segment motion during dynamic trials. They must remain stable relative to the underlying segment. A visible marker is not necessarily valid if it slides, rotates, or deforms with soft tissue.

### Marker clusters

Clusters can improve tracking robustness, especially when individual anatomical markers are prone to occlusion. They are valid only when mechanically stable. A loose, rotating, or sliding cluster produces false segment motion.

---

## Common failure modes

### Soft-tissue artefact

Soft-tissue artefact occurs when a skin-mounted marker moves relative to the underlying bone. It cannot be fully removed by filtering because it may occur in the same frequency range as true movement. It must be reduced through careful placement, fixation, cluster design, and task-specific judgement.

### Occlusion

Occlusion is common during elbow flexion, wrist and hand tasks, shoulder elevation, reaching, grasping, bilateral movement, and tasks involving supports, tables, handles, braces, or exoskeletons. It should be identified during rehearsal, not after the dataset has been collected.

### Marker swaps

Marker swaps occur when the system confuses two markers. They are common when markers are close together, temporarily occluded, or moving quickly. A swapped marker can produce smooth but anatomically false trajectories.

### Mechanical instability

Visibility does not guarantee validity. A marker may remain visible and labelled while no longer representing the intended anatomical segment. This can occur when a marker base loosens, a cluster rotates, or a marker moves with clothing, straps, braces, or support devices.

### Static trial errors

A poor static trial contaminates the full workflow. Missing anatomical markers, incorrect labels, inconsistent posture, misplaced landmarks, or model-incompatible static posture can all produce systematic downstream errors.

The static trial is not administrative. It is a calibration measurement.

---

## Trial checks

### Static trial

Before recording the static trial, confirm:

- all required markers are present;
- labels are correct;
- anatomical markers follow the selected marker set;
- posture matches the model requirement;
- no marker is hidden;
- enough frames are recorded for a stable static pose.

If anatomical markers are removed after the static trial, document it.

### Dynamic trials

Before formal dynamic trials, rehearse the target movement and check:

- marker visibility;
- repeated occlusion;
- cluster stability;
- capture-volume coverage;
- interference from supports, loads, braces, handles, or cables;
- whether the movement exceeds the model’s expected range.

For CEINMS workflows, movement must be suitable for musculoskeletal modelling, not merely visually acceptable. If marker trajectories drive the model into unrealistic postures or beyond physiological range, inverse kinematics may become unstable or fail.

External supports and loads must be documented. Marker trajectories describe movement; they do not measure unrecorded external forces.

---

## Quality control

Marker quality must be checked before data processing. Minimum checks include:

- marker visibility;
- label consistency;
- trajectory continuity;
- marker swaps;
- repeated occlusion;
- cluster stability;
- anatomical plausibility of reconstructed movement.

Inspect trajectories before export. Look for large gaps, sudden jumps, noisy trajectories, impossible paths, repeated marker loss, and markers reconstructed on reflective objects.

Successful export is not a quality-control criterion.

In OpenSim-based workflows, marker error is the distance between the experimental marker and the corresponding model marker after inverse kinematics. RMS marker errors around 1-2 cm may be acceptable in some whole-body or upper-limb workflows, while persistent errors above this range or maximum errors of several centimetres should trigger inspection. These are warning levels, not universal thresholds.

---

## Documentation

Record at minimum:

- subject ID;
- session date;
- operator;
- motion capture system;
- number of cameras;
- sampling frequency;
- marker set;
- static trial posture;
- dynamic trial names;
- task description;
- external loads, supports, braces, handles, exoskeletons, or other equipment;
- known marker issues;
- excluded trials and reasons;
- deviations from the marker protocol.

Common file types:

- `.c3d`: motion capture file containing marker trajectories and analogue data;
- `.trc`: marker trajectory file commonly used by OpenSim;
- `.mot`: motion file, often used for joint coordinates or external loads;
- `.sto`: OpenSim storage file, often used for model outputs;
- `.csv`: logs, metadata, or quality-control summaries.

---

## Key message

Marker data are not merely experimental records; they are model inputs. Poor marker data can invalidate scaling, inverse kinematics, inverse dynamics, muscle-tendon kinematics, moment arms, and CEINMS outputs.

---

## Useful resources

### Marker-based motion capture

- [Cappozzo et al. Human movement analysis using stereophotogrammetry. Part 1. *Gait & Posture*. 2005.](https://doi.org/10.1016/j.gaitpost.2004.01.010)
- [Chiari et al. Human movement analysis using stereophotogrammetry. Part 2. *Gait & Posture*. 2005.](https://doi.org/10.1016/j.gaitpost.2004.04.004)
- [Leardini et al. Human movement analysis using stereophotogrammetry. Part 3. *Gait & Posture*. 2005.](https://doi.org/10.1016/j.gaitpost.2004.05.002)

### Anatomical frames and coordinate systems

- [Cappozzo et al. Position and orientation in space of bones during movement. *Clinical Biomechanics*. 1995.](https://doi.org/10.1016/0268-0033(95)91394-T)
- [Wu and Cavanagh. ISB recommendations for reporting kinematic data. *Journal of Biomechanics*. 1995.](https://doi.org/10.1016/0021-9290(95)00017-C)
- [Wu et al. ISB recommendation on joint coordinate systems: shoulder, elbow, wrist and hand. *Journal of Biomechanics*. 2005.](https://doi.org/10.1016/j.jbiomech.2004.05.042)

### Practical documentation

- [OpenSim: How Inverse Kinematics Works](https://opensimconfluence.atlassian.net/wiki/spaces/OpenSim/pages/53090047/How%2BInverse%2BKinematics%2BWorks)
- [OpenSim: Inverse Kinematics Best Practices](https://opensimconfluence.atlassian.net/wiki/spaces/OpenSim/pages/53090489/_Inverse%2BKinematics%2BBest%2BPractices)
- [Vicon Nexus: Reconstruct and label movement trials](https://vicon-help.atlassian.net/wiki/spaces/Nexus215/pages/11377698/Reconstruct%2Band%2Blabel%2Bmovement%2Btrials)

#### Troubleshooting marker labelling 

- [Troubleshooting labelling skeleton templates in Vicon Nexus](https://help.vicon.com/space/Nexus215/11378339/Troubleshooting+labeling+skeleton+templates)
- [Troubleshooting auto-labelling with custom Vicon Skeleton Templates](https://www.youtube.com/watch?v=VAaBug0hWDQ)

#

**[Next page (Markerset Guide)]({% link markerset_guide.md %})**

**[Home]({% link index.md %})**
