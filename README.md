########################
# README for LoonCodes
########################

Coauthors:
  
  Katherine E. Lukens       NOAA/NESDIS Center for Satellite Applications and Research (STAR), University of Maryland/Cooperative Institute for Satellite Earth System Studies (CISESS);
  
  Kayo Ide                  University of Maryland;
  
  Kevin Garrett             NOAA/NESDIS Center for Satellite Applications and Research (STAR)

Acknowledgments: 
  
  Erin Jones, Hui Liu, Ross N. Hoffman, Kate Howard, Chris Barnet, Likun Wang, the Loon team (Max Kamenetsky, James Antifaev, Sal Candido, Rob Carver, and Nikolai Chernyy)

########################
Summary: Changes to the GSI source code in order to ingest and assimilate stratospheric superpressure balloon wind observations (from Loon, LLC)

Loon-related Code Explanations:

  converr.f90 - read error table for conventional obs. "loon_id" variable is added to retrieve Loon-related error table.

  global_convinfo.txt.2018022818 - fix file that lists all observation types and their usage in the system (iuse = 1 --> assimilate, iuse = -1 --> monitor, iuse = 0 --> do not use). Line 193 ("uv   599" ...) added for system to recognize Loon wind observations.
  
  exglobal_analysis_fv3gfs.sh.ecf - main analysis script to read in observations. "LOONBUFR" file is added: Loon input BUFR file is add and concatenated to Aircraft profiles input BUFR file.
  
  prepobs_errtable.global - list of error tables for different observation types. Added table for Loon (599 OBSERVATION TYPE).
  
  read_obs.F90 - main script that reads in observations. "loon_id" variable is added so system recognizes Loon wind observations.
  
  read_prepbufr.f90 - script that reads in all observation from input prepbufr file. "loon_id" variable is added to retrieve Loon wind observations.
  
  setupw.f90 - script that computes biases and other statistics at observation locations. "loon_id" variable is added to perform such statistics on Loon wind observations.

----- How to cite this code -----
Lukens, K. E., K. Ide, and K. Garrett, 2023: Investigation into the Potential Value of Stratospheric Balloon Winds Assimilated in NOAA’s Finite-Volume Cubed-Sphere Global Forecast System (FV3GFS), Journal of Geophysical Research: Atmospheres, e2022JD037526, https://doi.org/10.1029/2022JD037526.
