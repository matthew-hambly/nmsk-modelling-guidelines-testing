---
title: Electromyography
parent: Data collection
nav_order: 2
layout: default
has_toc: false
---

# Electromyography
Electromyography (EMG) measures the electrical activity associated with muscle contraction using electrodes placed on the skin or within the muscle. EMG provides valuable insight into neuromuscular function and is widely used in biomechanics and neuromusculoskeletal modelling to estimate muscle activations and understand movement strategies.

## Electrodes
A range of electrode types are available for EMG recording, including surface electrodes, high-density surface electrode arrays ([HD-EMG](./hd_emg.md)), and intramuscular electrodes. The choice of electrode depends on the application, target muscle, and required spatial resolution. For most biomechanical and neuromusculoskeletal modelling applications, surface bipolar electrodes are commonly used. These consist of two recording surfaces placed a fixed distance apart and provide a practical balance between ease of application, signal quality, and participant comfort.

## Placement
Where possible, follow [SENIAM](http://www.seniam.org/) guidelines for best practices on accurately and reliably placing EMG electrodes. Before placement the preparation for surface EMG involves shaving the skin, lightly abrading the area, and wiping with alcohol.

### Lower limb EMG set

| Muscle | Sensor placement | Placement test movement |
|--------|------------------|-------------------------|
| Vastus medialis | At 80% of line between ASIS & knee joint space at anterior border of medial ligament | Seated & resisted knee extension, hip & knee at 90° |
| Vastus lateralis | At 2/3 of line from ASIS to lateral aspect of patella | Seated & resisted knee extension, hip & knee at 90° |
| Rectus femoris | Midpoint of line between ASIS & superior aspect of patella | Seated & resisted knee extension, hip & knee at 90° |
| Tibialis anterior | At 1/3 on the line between the tip of fibula & the tip of medial malleolus (prox.) | Support the leg above the ankle joint with the ankle joint in dorsiflexion & foot in inversion |
| Sartorius |------------------|-------------------------|
| Semitendinosus | 50% on the line between ischial tuberosity & medial tibial epicondyle | Hip extension & knee flexion in prone, knee at 45°, with internal tibial rotation |
| Biceps femoris long head | 50% on the line between the ischial tuberosity and the lateral epicondyle of the tibia. | Thigh extension & knee flexion in prone, knee at 45°, with external tibial rotation |
| Medial gastrocnemius | Most prominent bulge of the muscle | Resisted ankle plantar flexion while prone with knee slightly flexed |
| Lateral gastrocnemius | At 1/3 of line between head of fibula & heel | Resisted ankle plantar flexion while prone with knee slightly flexed |
| Soleus | At 2/3 of line between the medial condylis of femur & medial malleolus (distal) | Resisted ankle plantar flexion while prone with knee slightly flexed |
| Gluteus medius | At 1/2 of line between the iliac crest & greater trochanter | Hip abduction while lying on the contralateral side |
| Gluteus maximum | At 1/2 of line between the sacral vertebrae & greater trochanter | Hip extension in prone with external femoral rotation |
| Tensor fasciae latae | At 1/6 line from ASIS to lateral femoral condyle (proximal) | Hip abduction while lying on the contralateral side |

 

### Upper limb EMG set

| Muscle | Sensor placement | Placement test movement |
|--------|------------------|-------------------------|
| Deltoid anterior (DELTant) | One finger width distal and anterior to the acromion. | Shoulder flexion (raise the arm forward). |
| Deltoid medius (DELTmed) | From the acromion to the lateral epicondyle of the elbow, corresponding to the greatest bulge of the muscle. | Shoulder abduction (raise the arm sideways). |
| Deltoid posterior (DELTpost) | Area about two fingerbreadths behind the angle of the acromion. | Shoulder horizontal abduction or extension (move arm backwards). |
| Trapezius descendens (TRAPdesc) | 50% on the line from the acromion to the spine on vertebra C7. | Shoulder shrug (scapular elevation). |
| Trapezius transversalis (TRAPtrans) | 50% between the medial border of the scapula and the spine, at the level of T3. | Scapular retraction (squeeze shoulder blades together). |
| Trapezius ascenden (TRAPasc) | 2/3 on the line from the trigonum spinae to the 8th thoracic vertebra. | Scapular depression (pull shoulders downward). |
| Infraspinatus (INFSP) | 4 cm below the spine of the scapula, over the infraspinous fossa of the scapula laterally, avoiding the posterior deltoid muscle. | External rotation of the shoulder with the elbow at the side. |
| Latissimus dorsi (LAT) | Approximately 4 cm below the inferior border of the scapula, halfway between the spine and the lateral edge of the torso, positioned about 25° obliquely. | Shoulder extension or adduction (pull arm downward/backward). |
| Pectoralis major clavicular (PECclav) | Approximately 2 cm below the clavicle, medial to the anterior deltoid, aligned with the muscle fibres running inferolaterally. | Shoulder flexion or horizontal adduction (forward press movement). |
| Pectoralis major sternal (PECstern) | Approximately 3–5 cm lateral to the sternum at the level of the fourth rib, aligned with the muscle fibres running laterally toward the humerus. | Shoulder horizontal adduction (e.g., pressing arms together in front of chest). |
| Triceps brachii long head (TRIlong) | Halfway along the line between the posterior crista of the acromion and the olecranon, two finger widths medial to the line. | Elbow extension (straighten the elbow). |
| Triceps brachii lateral head (TRIlat) | Halfway along the line between the posterior crista of the acromion and the olecranon, two finger widths lateral to the line | Elbow extension (straighten the elbow). |
| Biceps brachii (BICshort) | Along the line between the medial acromion and the fossa cubiti, one third of the distance from the fossa cubiti. | Elbow flexion (bend the elbow) or forearm supination. |
| Brachioradialis (BRD) | 1/3 of the distance from the lateral epicondyle to the styloid process of the radius, over the prominent muscle belly on the lateral forearm. | Elbow flexion with the forearm in a neutral position (hammer curl). |

EMG recordings from the forearm muscles are often performed using [HD-EMG](./hd_emg.md), as the close proximity of the muscles can make it difficult to isolate individual muscle activity with conventional bipolar electrodes.

## Maximal voluntray contraction
When using EMG recordings to inform neuromusculoskeletal modelling, and to facilitate comparisons across participants, it is important to normalise EMG signals to a reference value representing maximal muscle activity. EMG guidelines often recommend collecting maximal isometric voluntary contractions (MVIC) for signal normalisation. However, many dynamic tasks produce EMG signals that exceed MVIC's. Consider using a range of both maximal effort dynamic and isometric tasks to ensure a true maximal signal is obtained [CEDE project - Dick et al. 2024](https://doi.org/10.1016/j.jelekin.2024.102910). 

## Quality checks
- After placing the EMG sensors, verify the quality of each signal by performing a movement that is expected to activate the muscle of interest. A clear increase in signal amplitude should be visible during the contraction.
- Inspect each signal for:
    - Movement artefact, particularly during dynamic tasks. Ensure electrodes are securely attached and cables or sensors are not moving excessively.
    - Excessive noise, where baseline noise is large relative to the muscle activity. Minimise sources of electrical interference and verify electrode placement and skin preparation.
    -Clipping or saturation during high-intensity contractions. Confirm that an appropriate gain setting is being used.
    - Cross-talk, where activity appears in a muscle channel that is inconsistent with the performed movement. Check electrode placement and orientation.
    - Poor electrode contact, indicated by intermittent signals, signal dropouts, or unusually low amplitudes. Check electrode adhesion and skin preparation.
- Continue to monitor signal quality throughout data collection, as signals can degrade due to electrode movement, sweat accumulation, loss of skin contact, battery depletion, or wireless communication issues
- If signal quality changes during the session, pause data collection and rectify the issue before continuing.

## Signal processing
Guidelines on the subsequent EMG processing steps can be found [here](../2_preprocessing/emg_preprocessing.md).

## Other useful resources
**NOTE:** Many of these are generally focused purely on EMG and do not necessarily consider the use within NMSK modelling.
- SENIAM guidelines - [website](https://www.seniam.org/), [publication](http://seniam.org/pdf/contents8.PDF)
- [International Society of Electrophysiology and Kinesiology EMG (ISEK)](https://isek.org/)
    - Reporting standards - [website](https://isek.org/emg-standards/), [publication](https://isek.org/wp-content/uploads/2015/05/Standards-for-Reporting-EMG-Data.pdf)
    - [Tutorials](https://isek.org/isek-jek-tutorials/)
- [Consensus for Experimental Design in Electromyography (CEDE)](https://cede.isek.org/)
- [Ten frequently asked questions (FAQs) on surface electromyography](https://doi.org/10.1016/j.jelekin.2026.103159)
- [Surface electromyography: physiology, engineering, and applications](https://books.google.com.au/books?hl=en&lr=&id=Rl7WCgAAQBAJ&oi=fnd&pg=PR7&dq=Surface+electromyography:+physiology,+engineering,+and+applications&ots=yddhnehmVj&sig=DrFb9QdBRfBd19l6SXbAXdN6ELI) textbook edited by Roberto Merletti & Dario Farina

---

**[Previous page (Markerset Guide)]({% link markerset_guide.md %})**

**[Next page (HD-EMG)](hd_emg.md)**
