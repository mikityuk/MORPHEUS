# MORPHEUS
----------------------------------------------------------------------
Matlab-based Open-source Reactor PHysics EdUcation System
----------------------------------------------------------------------
Goal: Provide practical exercises to learn main phases of the nuclear reactor analysis.
----------------------------------------------------------------------
Step 1. Download nuclear data from IAEA site. 

Folder: 01.Micro.XS.421g

Download the GENDF files for the required isotopes from the open-access IAEA website: https://www-nds.iaea.org/ads/adsgendf.html

----------------------------------------------------------------------
Step 2. Convert data from GXS to CSV format. 

Folder: 01.Micro.XS.421g

Run the function convertGXStoCSV. The function scans the current folder for the files with the extension .GXS which are microscopic cross sections in 421 energy % group structure in the GENDF format and convert them to the CSV ("Comma Separated Values") file format readable by Excel and therefore easily readable by Matlab. Note that semicolons are used in the script instead of commas, therefore, check that your Windows regional settings are set to use semicolons instead of commas as the list separator symbol.

----------------------------------------------------------------------
Step 3. Convert data from CSV to M format.

Folder: 01.Micro.XS.421g

Run the function convertCSVtoM. The function scans the current folder for the files with the extension .CSV which are microscopic cross sections in 421 energy group structure in the CSV ("Comma-Separated Value") format, obtained from the GENDF format, and convert them to the Matlab format.

For every temperature available in the GENDF file, separate Matlab file is created.

The Matlab format file for an isotope includes:
- atomic weight (amu);
- number of energy groups (=421);
- energy group boundaries (eV);
- set of background cross sections, sigma-zeros (b)
- temperature (K);
- radiative capture cross sections (b) for each sigma-zero;
- (n,alfa) reaction cross sections (b) for each sigma-zero;
- (n,2n) matrix (b) for the first Legendre component;
- scattering matrix (b) for the three Legendre components and each sigma-zero;
- fission cross sections (b) for each sigma-zero;
- nubar (-);
- fission spectrum (-);
- total cross sections (b) for each sigma-zero (b);

Note that (n,3n), etc. reactions are NOT included in the current version.
