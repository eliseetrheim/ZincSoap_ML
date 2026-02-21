# Evaluating Unsupervised Clustering Strategies for Identifying Degradation-Related Chemical Domains in SEM-EDS Spectrum Imaging of Zinc-Soap Affected Paint Layers

## Elise Etrheim, eliseetrheim2027@u.northwestern.edu, Northwestern University Department of Materials Science \& Engineering

--- 

### Project Background

--- 

### Project Structure

---

### About the Dataset

This project uses publicly available SEM-EDS spectrum-imaging data from the National Institute of Standards and Technology (NIST) Public Data Repository. The dataset accompanies the publication *Characterization of Zinc Carboxylates on an Oil Paint Test Panel* (Romano et al., 2019). It includes hyperspectral EDS maps, point-based EDS spectra, FTIR data, and supporting metadata.

The dataset can be accessed at:

https://data.nist.gov/od/id/8C40CFA7931709DAE0532457068179072082

Only the SEM-EDS spectrum-imaging files are used in this project. Users who wish to reproduced the analysis should download the dataset separately and place the files in a local directory that is not tracked by Git. 

---

### Environment Set-up

This project uses a dedicated conda environment. To reproduce the environment used for the analysis, run: 

conda env create -f environment.yml

conda activate zincsoap-ml

The environment includes the core scientific Python stack (NumPy, SciPy, Pandas, Matplotlib, scikit-learn), HyperSpy for SEM-EDS hyperspectral data processing, and JupyterLab for running the analysis notebooks. 



