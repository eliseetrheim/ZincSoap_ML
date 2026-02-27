# Evaluating Unsupervised Clustering Strategies for Identifying Degradation-Related Chemical Domains in SEM-EDS Spectrum Imaging of Zinc-Soap Affected Paint Layers

## Elise Etrheim, eliseetrheim2027@u.northwestern.edu, Northwestern University Department of Materials Science & Engineering

--- 

### Project Background

*This project was developed and completed within the context of Northwestern University's MSE 465: Advanced Electron Microscopy & Diffraction course, under the guidance of Prof. Roberto dos Reis.*

--- 

### Project Structure

---

### About the Dataset

This project uses publicly available SEM-EDS spectrum-imaging data from the National Institute of Standards and Technology (NIST) Public Data Repository. The dataset accompanies the publication *Characterization of Zinc Carboxylates on an Oil Paint Test Panel* (Romano et al., 2019). It includes hyperspectral EDS maps, point-based EDS spectra, FTIR data, and supporting metadata.

The dataset can be accessed at:

https://data.nist.gov/od/id/8C40CFA7931709DAE0532457068179072082

This project only requires use of the SEM-EDS datasets and associated validation files: 

#### 1. Primary Data (Required)
**Aerial View Spectrum Image**
- Aerial 150x.rpl
- Aerial 150x.raw.gz
- Aerial 150x.raw.sha512sum
- Aerial 150x.rpl.sha512.sum

**Cross-Section Spectrum Image**
- CS 148x.rpl
- CS 148x.raw.gz
- CS 148x.raw.sha512sum
- CS 148x.rpl.sha512sum

The .rpl files contains metadata and header information necessary for interpreting spectral data. The .raw.gz files contain the compressed hyperspectral data cube. Checksum files are included to verify data integrity.

#### 2. Point-Based EDS Spectra (For Interpretation)
**All files named:** 
- Spectrum *.msa

These spectra are used for qualitative chemical interpretation and comparison with cluster-mean spectra.

#### 3. Region-of-Interest (ROI) Images & Quantification Tables (Optional but Recommended)
**ROI Images**
- CS diffusion ROI.tif
- Gel and Bioplastic ROI.tif
- White1to3 and Red4.tif

These TIFF files indicate acquisition locations and can help contextualize clustering results spatially. 

**Quantification Tables**
- Aerial Gel.xlsx
- Bioplastic.xlsx
- CS diffusion.xlsx
- Gel.xlsx
- Red.xlsx
- White.xlsx

These are used for qualitative validation and interpretation of cluster compositions. 

#### 4. Files Not Required
**The following dataset components are not used in this project:** 
- FTIR hyperspectral data
- DART-MS data
- Supporting documentation files not directly related to SEM-EDS

## Total Required Data Volume: ~55MB

---

### Reproducibility & Environment Set-up

To reproduce the analysis environment: 
1. clone this repository to your local machine

	git clone https://github.com/yourusername/ZincSoap_ML.git

	cd ZincSoap_ML

2. Create the conda environment using the provided file: 

	conda env create -f environment.yml

	conda activate zincsoap-ml

The environment includes the core scientific Python stack (NumPy, SciPy, Pandas, Matplotlib, scikit-learn), HyperSpy for SEM-EDS hyperspectral data processing, and JupyterLab for running the analysis notebooks. 

3. Download the dataset separately (see *About the Dataset* section) and place the files in a local directory that is not tracked by Git. 

4. Launch JupyterLab to run the analysis notebooks.


