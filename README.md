# NAIPburp
Model carbon emissions from the North Atlantic Igneous Province

NAIPburp contains multiple stochastic models for carbon-based greenhouse gas emissions from the North Atlantic Igneous Province (NAIP).  These histories were calculated using code in GitHub repositories smj75/sillburp and smj75/LIPburp.  

The primary reference is, "Jones, S. M., Hoggett, M., Greene, S. E. & Dunkley Jones, T.,  Large Igneous Province thermogenic greenhouse gas flux could have initiated Paleocene-Eocene Thermal Maximum climate change, Nature Communications, in press Sept 2019," referred to below as Jea19.

There are 3 types of data here.

## 1. DATASETS of NAIP sill province dimensions used to generate the results 
  
### Measurements of sill surface area, A in km2 
Used in Jea19, Fig. 4a.\
*sill_areas_3D_naip_over10km2.x* (this distribution used for stochastic modelling).\
*sill_areas_2D_naip_corr_over10km2*\
*Judd.txt*\
*FSB.txt*\
*More.txt*\
*IrishRockall.txt*\
*Rockall2D.txt*\
*SlyneErris.txt*.


### Measurements of sill emplacement depth, Z in km.
*emplacement_depth.gmt* contains the data, the approximation used in stochastic modelling and the plotting script for Jea19, Fig. 4b.  
  
### Measurements of maximum thickness, S in m, as a function of measured maximum sill radius, R in km
*thickness_diameter.gmt* contains the data, the approximation used in stochastic modelling and the plotting script for Jea19, Fig. 4c.  
  
### Measurements of sill thickness, s in m, as a function of distance from sill centre, r in km
*thickness_profile.gmt* contains the data, the approximations used in stochastic modelling and the plotting script for Jea19, Fig. 4d.  

### Host rock TOC measurements, w_CH4, in %
*host_toc.gmt* contains the data, the approximation used in stochastic modelling and the plotting script for Jea19, Fig. 4e.  

### Parameterisation of (M_therm, tau_decay, p) as functions of (s, Z) used to simulate emissions from individual sills
*aureole_parameterisation.txt* records the data in the format needed by *smj75/LIPburp/dim2mpt.awk*.  See smj75/sillburp* for calculation method.


## 2. RESULTS of greenhouse gas emissions modelling using the NAIP sill measurements and constant values of tau_repeat, the time between intrusion of successive sills

Files are named const_trec_[A]yr_emissions_model_[B]yr.[N], where [A] is the constant value of tau_repeat, [B] is the time period over which the measurements are averaged, and [N] is the stochastic run number.   


## 3. RESULTS of greenhouse gas emissions modelling using the NAIP sill measurements and time-dependent tau_repeat, specified by a mantle convection model.  

Files are named emissions_model_[B]yr_q[Q].[N] and sills_model_[B]yr_q[Q].[N], where [B]is the time period over which the measurements are averaged, [Q] is the mantle plume area flux, and [N] is the stochastic run number.  

The columns in each *emissions_model* file are:
1.  Time relative to first sill
2.  Total carbon flux at this time step
3.  Carbon flux from thermogenic methane at this time step
4.  Carbon flux from CO2 degassed from sill magma at this time step
5.  Carbon flux from CO2 degassed from lavas at this time step
6.  Fraction of total carbon supplied as thermogenic methane at this time step
7.  Total cumulative carbon mass up to this time
8.  Carbon mass from thermogenic methane up to this time
9.  Carbon mass from CO2 degassed from sill magma up to this time
10.  Carbon mass from CO2 degassed from lavas up to this time
11.  Cumulative Carbon isotope composition of all carbon emitted from province
12.  Carbon isotope composition of thermogenic+mantle emissions at this time step
13.  Sill recurrence time
14.  Absolute age
15.  Long radius of mantle thermal anomaly marker
16.  Time step number (= sill number)
17.  Mean carbon flux from thermogenic methane at this time step

The columns in each *sills_model* file are:
1. INTRUSION TIME (relative to a reference point in the mantle plume head model)
2. TOTAL MASS PER UNIT SURFACE AREA
3. TOTAL MASS OF CO2 DEGASSED FROM MAGMA
4. MATURATION DECAY TIME
5. TIME TO ESTABLISHMENT OF VENT
6. TIME TO SOLIDIFICATION OF MAGMA
7. TIME AFTER PULSE LEFT PLUME CENTRE
8. SILL RECURRENCE TIME
9. MAXIMUM PULSE RADIUS
10. SILL LOCATION RADIUS
11. SILL LOCATION AZIMUTH
12. NUMBER OF OVERLAPPING SILLS
13. OVERLAPPED PERCENTAGE OF AUREOLE FOOTPRINT, THIS SILL
14. OVERLAPPED PERCENTAGE OF AUREOLE VOLUME, THIS SILL
15. OVERLAPPED PERCENTAGE OF AUREOLE FOOTPRINT, WHOLE PROVINCE
16. OVERLAPPED PERCENTAGE OF AUREOLE VOLUME, WHOLE PROVINCE
