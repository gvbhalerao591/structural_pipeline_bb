# UK Biobank structural pipeline for processing T1w scans
---
### Usage: 
```
bash main_processT1 <subject_folder> <coefficients_file>
```

### Description:
This script processes T1-weighted MRI data, performing gradient distortion correction (if provided), brain extraction, tissue segmentation, non-linear registration to MNI space, and subcortical structure segmentation.

### Arguments:
1) subject_folder        : The path to the subject's folder, which must contain a T1-weighted image. (organisation: subjects folder >> T1 >> T1.nii.gz)
2) coefficients_file     : The coefficients file for Gradient Distortion Correction (GDC). Set to "none" if distortion correction is not required.

### Required Tools: 
FSL (https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/)

### Notes:
- Ensure that the paths to FSL and bb_pipeline binaries are correctly set in your environment.
- The coefficients file for GDC should come from the scanner or other calibration source. If no correction is needed, simply pass "none" as the second argument.
---
### Example:
```
bash main_processT1 /path/to/subject_folder /path/to/coefficients/file
bash main_processT1 /path/to/subject_folder none  # Skips GDC if "none" is provided
```
### Output:
Saved in /path/to/subject_folder/IDP_files
- bb_IDP_T1_FIRST_vols (not normalised)
- bb_IDP_T1_SIENAX
- bb_IDP_T1_FIRST-norm_vols (normalised for head size)

### IDP details:
Refer IDP_list.txt 


