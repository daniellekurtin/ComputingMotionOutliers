# MotionMetrics

**To see an example and output of this script, please download the pdf ExampleOutput_DVARSCorrelatedWithPEandFA.pdf.**

This repo shows how global motion metrics can by computed and covaried with group-level results calculated via FSL.

The best way to account for motion using FSL include using motion parameters as a covariate as no interest, and removing noisy artefacts (identified via ICA) using FIX (Smith et al 2004). Another method to account for motion can the inclusion of a confound matrix of motion outlier metrics computed on the raw data in a first-level FEAT, as calculated by fsl_motion_outliers. 

We have adapted this last method to assess the influence of global motion. We used the function fsl_motion_outliers to compute the DVARS (the spatial root mean square of the data after temporal differencing) per session per subject (Power et al 2012). Then, DVARS are averaged per person, and are included as a continuous covariate in a linear mixed effects model. This assesss the influence of global motion on our interaction of interest- that between PE and FA. For more information on how to calculate motion metrics, please see: https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers. For more information on the study this is applied to, please see: https://www.biorxiv.org/content/10.1101/2020.10.09.332742v1.

Steps:
1. Caclulate DVARS per session per participant (use script CalcDVARs.txt).
2. Average DVARS values per person (this is stored here in PTandHCMO.csv. Each column has the DVARS for all participants for all their sessions).
3. Covary the averaged DVARS with results (use script MotionCorrelatedWithPEandFA_v3.mlx).

