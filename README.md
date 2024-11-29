# XCT-XRDCT Paper Code

This repo stores all of the associated code for the multimodal data descriptor paper , of which the pre-print is found at [Three-Dimensional, Multimodal Synchrotron Data for Machine Learning Applications](https://arxiv.org/abs/2409.07322)

The paper describes four resolution X-Ray Computed Tomography (XCT) data obtained on the I13-2 beamline, along with XCT data from DIAD, two resolutions of X-Ray Diffraction Computed Tomography data (XRD-CT) from DIAD, and powder X-Ray Diffraction data from the ISIS Neutron & Muon Source Materials Characterisation Lab.

XRD_Analysis_ascii.ipynb shows how to load and visualise the powder-XRD data, showing how the peaks for the Zn and Na phase

A copy of the bash code to execute savu, along with the savu process list is provided for the I13-2 and DIAD XCT entries on Zenodo.

Sinograms.ipynb describes the loading and processing used to plot sinograms for the Zinc and Sodium phases.

DiffTomo_Analysis.ipynb is a Jupyter Notebook which shows how to perform the reconstruction of the XRD-CT data collected from DIAD.

I13-2_Alignment.ipynb is a Jupyter Notebook which shows the process used to align the XCT data across all four resolution obtained on I13-2.

## Guide to download data

The .h5 files in the Zenodo entries are large (>50GB), and therefore cannot be downloaded directly from Zenodo using the browser and must be downloaded using the command line command 'curl'. To generate the link to the file from Zenodo, simply right-click the download button for the file and select 'Copy Link' then paste to the command line. The reconstructed .h5 files for each large XCT dataset all share the same name so it is recommended to specify the name of the downloaded file. Below is an example that downloads the .h5 file for reconstructed 1.625 micron data and downloads it as '169067_recon.h5' to share the same naming convention as the associated .nxs file.

```bash
curl https://zenodo.org/records/13327651/files/tomo_p4_tomopy_recon.h5 > 169067_recon.h5
```

We recommend the following name convention for the I13 XCT data to work seamlessly with the notebooks:
- 169065_recon.h5 = 0.3125 micron XCT data reconstructed
- 169066_recon.h5 = 0.8125 micron XCT data reconstructed
- 169067_recon.h5 = 1.625 micron XCT data reconstructed
- 169068_recon.h5 = 2.6 micron XCT data reconstructed

**Please note: All filenames within the notebooks are designed to work with data downloaded in the same directory**

## Loading the Jupyter Notebooks

To load the Jupyter Notebooks, a basic working conda environment is provided that can load all the relevant python packages used in the notebooks.

To install the conda environment, run the following command inside the cloned Github Repo:

```bash
git clone https://github.com/calum-green/XCT-XRDCT_Multimodal_Dataset
cd XCT-XRDCT_Multimodal_Dataset
conda env create -f mutlimodal-xrdct.yml
conda activate multimodal-xrdct
```

The above command clones the whole repository then creates and activates the conda environment. 

At this stage, copy any downloaded data into the cloned repository.

To load a notebook (in this case Sinograms.ipynb) run the following:

```bash
jupyter-notebook Sinograms.ipynb
```

This will load the notebook in a browser window with the 'mutlimodal-xrdct' conda environment active.

## Loading the Data

To load the .hdf/.h5 files we recommend using the [DAWN](https://dawnsci.org) software or using [Fiji/ImageJ](https://imagej.net/software/fiji/) and the [BigDataViewer](https://imagej.net/plugins/bdv/) plugin. DAWN is a flexible software and is also used to load in the .nxs files and visualise the experimental metadata.

## Reporting Issue & Bugs

If you have any errors or issues using the notebooks or data, please raise a GitHub Issue or email the corresponding author.

