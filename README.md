# ComputingMotionOutliers

**To see an example and output of this script, please download the pdf ExampleOutput_MotionCorrelatedWithPEandFA.pdf.**

This repo shows how global motion metrics can by computed and covaried with group-level results calculated via FSL.
The best way to account for motion using FSL include using motion parameters as a covariate as no interest, and removing noisy artefacts (identified via ICA) using FIX (Smith et al 2004). 

Another method to account for motion outliers can the inclusion of a confound matrix of motion outlier metrics (computed on the raw data) in a first-level FEAT, as calculated by fsl_motion_outliers. FSL has been manufactured to encourage the inclusion of motion correction at the subject level, but in order to compute a metric of global motion, we will compute metrics of motion outliers per session, per person, then average them person, and use this as a continuous covariate in a regression. This will assess the influence of our global motion parameters on our interaction of interest- that between PE and FA. For more information on how to calculate motion outliers, please see: https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers

Steps:
1. Caclulate motion outliers per session per participant (use script ComputeMotionOutlier.txt).
3. Average motion outlier values per person (this is stored here in PTandHCMO.csv. Each column has the motion outliers for all participants for all their sessions).
4. Covary the motion outliers with results (use script MotionCorrelatedWithPEandFA_v3.mlx).

