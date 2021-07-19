# ComputingMotionOutliers
NOTE: this repo is under construction

This repo shows how global motion metrics can by computed and covaried with group-level results calculated via FSL.
The best way to account for motion using FSL include using motion parameters as a covariate as no interest, and removing noisy artefacts (identified via ICA) using FIX. 

Another method to account for motion outliers can the inclusion of a confound matrix of motion outlier metrics (computed on the raw data) in a first-level FEAT, as calculated by fsl_motion_outliers. FSL has been manufactured to encourage the inclusion of motion correction at the subject level, but in order to compute a metric of global motion, we will compute metrics of motion outliers per session, per person, then average them person, and use this as a continuous covariate in a regression. For more information on how to calculate motion outliers, please see: https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers

Steps:
1. Caclulate motion outliers per session per participant (use scripts ____)
2. Average motion outlier values per person 
3. Covary the motion outliers with results (use script ___)


Step 1: 
First, we calculate Motion Outlier values for the filtered_func_dat
