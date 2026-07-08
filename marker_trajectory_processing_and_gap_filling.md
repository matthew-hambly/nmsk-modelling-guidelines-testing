---
title: Marker processing
parent: Preprocessing
nav_order: 1
layout: default
has_toc: false
---

# Marker Processing: Labelling, gap filling, coordinate system rotations, filtering 
<!-- TODO:
      - Brief overview
      - Add references where applicable
      - Write "Gap Filling recommendations" section
-->

## Data acquisition inputs
- Labelled marker trajectories from motion capture system (e.g., Vicon, Qualysis)
- Hardware metadata: sampling rate, motion capture coordinate definitions.
- User defined parameters: motion direction rotations, filter cut-off frequencies.

## Processing workflow
1. Label and gap fill marker trajectories in Motion Capture Software (e.g., Vicon/Qualysis).
2. Import marker trajectories and preserve orginal files.
3. Low-pass filter trajetories. Filter cut-off frequency will depend on inteneded analysis/outcome measures. Caution: un-filled gaps can cause large filter artefacts. Ensure filering process is robust to gaps.
4. Rotate trajectories from lab coordinate system to OpenSim coordinate system. Additional rotations may be required to align motion direction with forward (+X) in OpenSim.  
5. Export final trajectories with consistent marker labels.

## Output formatting requirements
- Preferred OpenSim input: `.trc` text file.
- Header must include metadata and end with `endheader`.
- First data column should be 'Frame#' (positive integer), and second column should be `Time` (seconds).
- Remaing column have two rows of headers. The first should be the Marker label (e.g., 'LASIS', 'RASIS') every third column, the second row should be 'Xn', 'Yn', 'Zn', for markers 1 to n.
- One row per sample, no duplicated or missing timestamps.
- Gaps must be 'NaN', and not '0'.
- Optional intermediate/support files: `.csv`, `.sto`, `.json`, `.txt`.

## Quality checks
- Check for continuity.
- Confirm absense of filter artefact (e.g., if gaps have been replaced with zeros instead of NaN).
- Confirm marker labels are consistent across all trials.

## Gap Filling recommendations

---

**[Next page (Filtering choices and rationales for kinematics and kinetics)](filtering_choices_and_rationales_for_kinematics_and_kinetics.md)**
