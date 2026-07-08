---
title: Marker set guide
parent: Markers
nav_order: 1
layout: default
---

# Selecting model-compatible marker sets

Marker set selection is a modelling decision, having direct downstream consequences on the musculosketal modelling stages, in particular the [model scaling](../3_msk_modelling/model_scaling_and_personalisation.md) and [inverse kinematics](../3_msk_modelling/inverse_kinematics.md). The marker set must provide the anatomical information, segment tracking, coordinate-system compatibility, and downstream model inputs required by the study.

A central question to ask is:
> Does this marker set provide the information required by the model and the task?


## Core rule
Select the musculoskeletal model before finalising the marker set.

Recommended workflow for selecting a marker set:
1. Define the research question(s)
2. Select a musculoskeletal model with the appropriate configuration, for example:
    - Degrees of freedom
    - Musculotendon units
3. Select or adapt the experimental marker set
4. Define marker-to-model mapping
5. Pilot test the marker set with the actual task
6. Process pilot test data and refine marker set where needed


## Body-region considerations
### Full body and lower limb

**Example marker set:** the marker set below consist of placing the markers on both left and right limbs. Foot markers may vary depending on the need of the study.
| Segment | Description                    | Marker count | Marker name |
|---------|--------------------------------|--------------|-------------|
| Pelvis  | Anterior superior iliac spine  | 2            | ASIS        |
|         | Posterior superior iliac spine | 2            | PSIS        |
| Thigh   | Medial femoral condyle         | 2            | MFC         |
|         | Lateral femoral condyle        | 2            | LFC         |
|         | Thigh cluster                  | 2 x 4        | THI (1-4)   |
| Shank   | Medial malleolus               | 2            | MMAL        |
|         | Lateral malleolus              | 2            | LMAL        |
|         | Shank cluster                  | 2 x 4        | TIB (1-4)   |
| Foot    | Calcaneous                     | 2            | CAL         |
|         | Toe                            | 2            | TOE         |
|         | 2nd metatarsal head            | 2            | MT2         |
|         | 5th metatarsal head            | 2            | MT5         |

#### Foot and shoe markers

**Example bilateral lower limb and foot marker set** [(Maharaj et al., 2021)](https://doi.org/10.1080/10255842.2021.1968844)

| Segment | Description                    | Marker count | Marker name |
|---------|--------------------------------|--------------|-------------|
| Knee | Marker placed on medial epicondyle of the knee | 2 | MKN |
|      | Marker placed on lateral epicondyle of the knee | 2 | LKN |
| Shank | Cluster placed on anterior aspect of the leg | 2 x 3 | S (1-3) |
| Ankle | Marker placed on medial malleolus | 2 | MM | 
|       | Marker placed on lateral malleolus | 2 | LM | 
| Rear-foot | Marker placed on superior aspect of posterior calcaneus | 2 | PC |
|           | Marker placed on inferior aspect of posterior calcaneus | 2 | DC | 
|           | Marker placed on sustentaculum tali | 2 | MC |
|           | Marker placed on peroneal tubercle | 2 | LC |
| Midfoot | Marker placed on navicular tuberosity | 2 | NAV |
|         | Marker placed on base of the first metatarsal | 2 | MB1 |
|         | Marker placed on base of the second metatarsal | 2 | MB2 |
|         | Marker placed on base of the fifth metatarsal | 2 | MB5 |
| Forefoot | Marker placed on head of the first metatarsal | 2 | MH1 |
|          | Marker placed on head of the second metatarsal | 2 | MH2 |
|          | Marker placed on head of the fifth metatarsal | 2 | MH5 |
| Digits | Marker placed on the proximal phalanx of the hallux | 2 | D1 |
|        | Marker placed on the proximal phalanx of second digit | 2 | D2 |
|        | 	Marker placed on the proximal phalanx of fifth digit | 2 | D5 |


[ISB recommendations (Wu et al., 2002)](https://doi.org/10.1016/S0021-9290(01)00222-6)  
[ISB recommendations for skin-marker-based multi-segment foot kinematics (Leardini et al., 2021)](https://doi.org/10.1016/j.jbiomech.2021.110581)

### Upper body
Upper-body marker sets differ mainly in how they approximate scapular motion, humeral tracking, forearm rotation, wrist motion, and hand-object interaction. They are not simply reduced full-body marker sets.

**Example marker set:** this marker set is a combination from a shoulder model study ([Bolsterlee et al., 2014](https://doi.org/10.1007/s11517-013-1065-2)) and whole arm study which included hand motion ([Di Domenico et al., 2025](https://doi.org/10.1038/s41597-025-04552-5)).
| Segment | Description | Marker count | Marker name |
|---------|-------------|--------------|-------------|
| Thorax | 7th Cervical vertebra | 1 | C7 |
|  | 8th Thoracic vertebra | 1 | T8 |
|  | Incisura Jugularis | 1 | IJ |
|  | Processus Xiphoideus | 1 | PX |
| Shoulder | Acromioclavicular joint | 1 | AC |
|  | Trigonum spinae scapulae | 1 | TS |
|  | Angulus inferior | 1 | AI |
|  | Angulus acromialis | 1 | AA |
| Humerus | Lateral epicondyle | 1 | EL |
|  | Medial epicondyle | 1 | EM |
|  | Upper arm cluster | 1x3 | UARM (1-3) |
|  | Elbow cluster  | 1x3 | ELB (1-3) |
| Forearm | Radial styloid | 1 | RS |
|   | Ulnar styloid | 1 | US |
|   | Forearm cluster | 1x3 | FARM (1-3) |
| Hand | Distal interphalangeal joints (digits 2–5) | 4 | DIP (2-5) |
|   | Proximal interphalangeal joints (digits 2–5) | 4 | PIP (2-5) |
|   | Metacarpophalangeal joints (digits 1–5) | 5 | MCP (1-5) |
|   | Interphalangeal joint (thumb) | 1 | IP |
|   | Carpometacarpal joint (thumb) | 1 | CMC |
|   | Hand cluster | 1x3 | HAND (1-3) |

**Note:** Scapular tracking is difficult. Acromion markers and scapular clusters are practical approximations, not direct measurements of scapular bone motion.

[ISB recommendations (Wu et al., 2005)](https://doi.org/10.1016/j.jbiomech.2004.05.042)

## Landmark identification and static calibration
Anatomical landmarks define the relationship between external markers and modelled body segments. Poor landmark identification can introduce systematic errors in segment frames, joint centres, joint angles, muscle-tendon lengths, and moment arms. Anatomical landmarks should be palpable, model-relevant, consistently identified, placed in a repeatable posture, placed by trained operators, and documented when uncertain.

Static calibration posture must match the model requirement. A correct marker set with an inconsistent static posture can still produce poor scaling or poor anatomical frame definition.


## Suggested reporting details
A marker-set protocol should report:
- marker set name or source;
- body segments tracked;
- static calibration posture;
- anatomical landmarks used;
- tracking markers or clusters used;
- whether markers were placed on skin, clothing, shoes, braces, or devices;
- whether anatomical markers were removed after static calibration;
- task-specific deviations;
- marker-to-model mapping, if applicable.


## Additional tips
- **Treat marker names as part of the protocol:** Use fixed naming, avoid ambiguous left/right names, keep names consistent with the model when possible, and document renaming
- **Define marker-to-model mapping first:** determine which markers are being used for scaling and which are being used for tracking
- **Test with the actual task:** the pilot testing should check marker visibility and stability during full range of motion, within the entire capture volume and with potential obsrtuctions (e.g., supports, braces, handles, tables, cables, etc.)
- **Take photos of experiemntal setup when possible:** some markers (e.g., marker clusters or markers placed on shoes) are not placed on anatomical landmarks that can be consistenetly reproduced, having extensive documentation (e.g., photos and notes) on there placement is crucial when moving to the musculoskeletal modelling stage.


#
**[Previous page (Markers)]({% link markers.md %}) | [Next page (EMG)](emg.md)**

**[Home]({% link index.md %})**
