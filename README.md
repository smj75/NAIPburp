# NAIPburp
Model carbon emissions from the North Atlantic Igneous Province

NAIPburp contains multiple stochastic models for carbon-based greenhouse gas emissions from the North Atlantic Igneous Province (NAIP).  These histories were calculated using code in GitHub repositories smj75/sillburp and smj75/LIPburp.  

The primary reference is, "Jones, S. M., Hoggett, M., Greene, S. E. & Dunkley Jones, T.,  Large Igneous Province thermogenic greenhouse gas flux could have initiated Paleocene-Eocene Thermal Maximum climate change, Nature Communications, in press Sept 2019," referred to below as Jea19.

There are 3 types of data here.

1.  DATASETS of NAIP sill province dimensions that were used to generate the results.  
  
  1.  Measurements of sill surface area, A in km2 (e.g. Jea19, Fig. 4a).\
File **sill_areas_3D_naip_over10km2.x** (this distribution used for stochastic modelling).\
File "sill_areas_2D_naip_corr_over10km2".\
File "Judd.txt".\
File "FSB.txt".\
File "More.txt".\
File "IrishRockall.txt".\
File "Rockall2D.txt".\
File "SlyneErris.txt".


  1.  Measurements of sill emplacement depth, Z in km.\
File "emplacement_depth.gmt" contains the data, the approximation used in stochastic modelling and the plotting script for Jea19, Fig. 4b.  
  
  1.  Measurements of maximum thickness, S in m, as a function of measured maximum sill radius, R in km.\
File "thickness_diameter.gmt" contains the data, the approximation used in stochastic modelling and the plotting script for Jea19, Fig. 4c.  
  
1.4.  Measurements of sill thickness, s in m, as a function of distance from sill centre, r in km.\
File "thickness_profile.gmt" contains the data, the approximations used in stochastic modelling and the plotting script for Jea19, Fig. 4d.  

1.5.  Host rock TOC measurements, w_CH4, in %.\
File "host_toc.gmt" contains the data, the approximation used in stochastic modelling and the plotting script for Jea19, Fig. 4e.  

1.6.  Parameterisation of (M_therm, tau_decay, p) as functions of (s, Z) used to simulate emissions from individual sills.\
File "aureole_parameterisation.txt".


2. RESULTS of greenhouse gas emissions modelling using the NAIP sill measurements and constant values of tau_repeat, the time between intrusion of successive sills.  

Files are named const_trec_[A]yr_emissions_model_[B]yr.[N], where [A] is the constant value of tau_repeat, [B] is the time period over which the measurements are averaged, and [N] is the stochastic run number.   


3. RESULTS of greenhouse gas emissions modelling using the NAIP sill measurements and time-dependent tau_repeat, specified by a mantle convection model.  

Files are named emissions_model_[B]yr_q[Q].[N] and sills_model_[B]yr_q[Q].[N], where [B]is the time period over which the measurements are averaged, [Q] is the mantle plume area flux, and [N] is the stochastic run number.  
