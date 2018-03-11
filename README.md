code and model data below are based on this dataset:

[Mapping Canopy Foliar Chemical and Morphological Traits Using Imaging Spectroscopy](https://ecosis.org/#result/04c69525-8f44-4f76-9732-2e66857cf8f6)

## Code
1. 01_Normalize.py: Takes AVIRIS spectra, applies the normalization routine to each row and produces an output CSV file.

2. 02_ApplyModels.py: Takes the normalized spectra, applies the PLSR coefficients to get predictions on a spectrum-wise basis.


## Data
1. Bands.csv: Contains 'bad-band' specifications for AVIRIS data to simulate water absorption features that might need to be excluded.

2. ExampleSpectra.csv: Raw AVIRIS apparent surface reflectance spectra contaminated with water absorption features.

3. PLSR_coefficients_Raw_Aggregated_Nitrogen.csv: CSV file containing PLSR coefficients from Singh et al. (2015), these are coefficients aggregated from 500 randomized model runs.

4. PLSR_coefficients_Raw_Full_Nitrogen.csv: CSV file containing PLSR coefficients from Singh et al. (2015), these are coefficients from all 500 randomized model runs.

## Notes
01_Normalize.py uses Bands.csv and ExampleSpectra.csv to produce vector-normalized spectra which are saved in ExampleSpectra_Normalized.csv


02_ApplyModels.py: uses ExampleSpectra_Normalized.csv and the PLSR_coefficients files to obtain predictions (%N in this example.)


I have included obtaining uncertainties for the sake of completeness, single predictions can be obtained by commenting out relevant lines of code in 02_ApplyModels.py.
