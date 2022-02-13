# BGC-ARGO_analysis

This repo is used to download and analyze BGC-ARGO data focusing on adjusted dissolved oxyen data (DOXY_ADJUSTED)

- 1. Download 'synthetic profiles' netCDF file from Coriolis GDAC ftp site. [search_bgcargo.ipynb](https://github.com/takaito1/BGC-ARGO_analysis/blob/main/search_bgcargo.ipynb)
- 2. Scan 'oxygen calibration comments' and examine what calibration methods are used for delayed-mode data quality control. Group profiling floats according to the dominant calibration method [oxy_calibration_groups.ipynb](https://github.com/takaito1/BGC-ARGO_analysis/blob/main/oxy_calibration_groups.ipynb)
- 3. QC step 1. Perform a screening of floats using deep ocean climatology. Compare deep part (+1,000m) of O2 profiles against World Ocean Atlas (2009) climatology. To do so, first float O2 data is interpolated on to the standard z-levels (33 levels). Then for profile, WOA monthly climatology is interpolated to the position of the float. Then RMSE (root mean square error) score is calculated and recorded.  
- 4. QC step 2. Match-up profiles with OSD/CTD profiles from the World Ocean Database. This step is not used to exclude profiles. Rather, individual match-up comparison is visualized and saved as PDF file. Ensemble mean offset (mean, median) is calculated. 
- 5. Binning. Select the profiles (deep ocean RMSE < 10 micro-mol/kg) and bin the data into global 1x1 monthly grid according to the calibration type. 
