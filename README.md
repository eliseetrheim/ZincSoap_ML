# Evaluating Unsupervised Clustering Strategies for Identifying Degradation-Related Chemical Domains in SEM-EDS Spectrum Imaging of Zinc-Soap Affected Paint Layers

## Elise Etrheim, eliseetrheim2027@u.northwestern.edu, Northwestern University Department of Materials Science & Engineering

--- 

### Project Background

*This project was developed and completed within the context of Northwestern University's MSE 465: Advanced Electron Microscopy & Diffraction course, under the guidance of Prof. Roberto dos Reis.*

--- 

### Project Structure

ZincSoap_ML/

1. `data_processed/`
Intermediate processed datasets saved in HyperSpy format and generated in 01_data_preparation.ipynb from raw formats. 

2. `01_data_preparation.ipynb`
Loads raw SEM-EDS data, performs preprocessing, and saves processed .hspy datasets for downstream analysis. 
 
3. `02_clustering_analysis.ipynb`
Core analysis notebook, containing:   
- Feature extraction (elemental maps)  
- Data transformation and normalization
- Clustering (k-means, GMM, hierarchical)
- Cluster evaluation (ARI, metrics)
- Figure generation  

4. `03_point_scan_comparison.ipynb`
Uses point EDS spectra for qualitative validation of clustering results, generating comparison plots and spectral interpretations. 

5. `figures/`
Output directory for all figures.  

6. `environment.yml`
Conda environment specification for reproducibility.  

7. `README.md`
Project overview, dataset description, and usage instructions.

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

#### 3. Region-of-Interest (ROI) Images
- CS diffusion ROI.tif
- Gel and Bioplastic ROI.tif
- White1to3 and Red4.tif

These TIFF files indicate acquisition locations and can help contextualize clustering results spatially. 

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

---

### How to Run the Analysis

1. Run `01_data_preparation.ipynb`
   → Loads raw SEM-EDS data and saves processed `.hspy` files to `data_processed/`

2. Run `02_clustering_analysis.ipynb`  
   → Performs feature extraction, clustering, and generates all main figures

3. Run `03_point_scan_comparison.ipynb`  
   → Produces validation plots comparing clustering results with point spectra

All figures will be saved automatically to the `figures/` directory.

