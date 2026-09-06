# Dataset Screening Code

Code for the SHHS participant screening procedure described in the study.

## Data Source

The screening procedure uses the following source files:

- `shhs1-dataset-0.20.0.csv`
- `shhs2-dataset-0.20.0.csv`

The SHHS data are available through the National Sleep Research Resource.

## Screening Procedure

The screening procedure and PSG-availability verification used variables defined in the official SHHS data dictionary (shhs-data-dictionary-0.20.0-variables.csv), with categorical coding interpreted according to the corresponding domain file (shhs-data-dictionary-0.20.0-domains.csv). The variables considered were 'shhs1_psg', 'shhs2_psg', 'ahi_a0h3a', 'abnoreeg', 'afib', 'alzh2', 'hf15', 'prev_hx_stroke' and 'stroke15'.

The SHHS1 screening was performed using the SHHS1 source file 'shhs1-dataset-0.20.0.csv'. Based on the variables available in this source file, the SHHS1 screening included 'shhs1_psg', 'ahi_a0h3a', 'abnoreeg', 'afib', 'hf15', 'prev_hx_stroke', and 'stroke15'. Participants were retained when 'shhs1_psg' was coded as 1, 'ahi_a0h3a' was <5 events/h, and all categorical clinical screening variables were explicitly coded as 0.

The SHHS2 screening was performed using the source file 'shhs2-dataset-0.20.0.csv'. Participants were linked between SHHS1 and SHHS2 using the subject identifier ('nsrrid'), such that records with the same 'nsrrid' corresponded to the same participant across the two study visits. Only SHHS2 records corresponding to participants who had satisfied the SHHS1 screening criteria were considered for subsequent follow-up screening.

Based on the variables available in the source file, the SHHS2 screening included 'shhs2_psg', 'ahi_a0h3a', 'abnoreeg', 'afib', and 'alzh2'. Participants were retained when 'shhs2_psg' was coded as 1, 'ahi_a0h3a' was <5 events/h, and all categorical clinical screening variables were explicitly coded as 0.

In addition, the recording-level `comm` annotation was reviewed for EEG quality. One otherwise eligible SHHS2 recording with a documented 15-Hz low-pass filter was excluded following expert review because this processing was incompatible with the predefined frequency-band analysis used in the study.

## Requirements

The code was tested with Python 3.8.

Required Python packages:

- pandas
- numpy
- openpyxl

