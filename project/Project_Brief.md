# Neonatal MR Spectroscopy Processing Pipeline

## Background
MR Spectroscopy is prognostic for neonates with suspected encephalopathy. MRS has high sensitivity and specificity for abnormal cognitive and motor outcomes at 2 years. MRS is more accurate than conventional MRI and diffusion weighted imaging for predicting outcomes. The MRS spectrum is made up from signals from contributing metabolites. The spectrum is analysed by combining the fingerprints of each expected metabolite to fit the complete spectrum. The key metabolites are Lactate (Lac), Threonine (Thr) and N-Acetyl-Aspartate (NAA) the spectral amplitudes of each are used to calculate the ratio:


 (Lac+Thr)/(Total Naa)  


The raw MRS data outputted from the MR system in DICOM format. 
The pipeline output will be a pdf report with the MRS results, an assessment of the quality of the analysed data and the resulting spectrum.

## Challenges 
MRS is a low SNR technique.
Neonatal scanning is subject to significant movement artefacts – babies move.
Any movement partway through a scan can degrade the entire acquisition. 
To get around this the pipeline will need to:

- Acquire data in blocks and sum in post-processing
- Discard corrupted data
- Correct individual blocks for phase and frequency shifts prior to summation
