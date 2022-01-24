# pangeo-pismpaleo
Collection of notebooks to convert PISM simulation data to zarr format and to plot data

Zarr ensemble data from https://doi.pangaea.de/10.1594/PANGAEA.909728 can be found in:

    gs://ldeo-glaciology/paleo_ensemble/present.zarr      : 682M : 'thk','mask','topg','usurf','velsurf_mag','dbdt' at present
    gs://ldeo-glaciology/paleo_ensemble/extra.zarr        : 120M : 'mask' every 1000 years since 125ka BP
    gs://ldeo-glaciology/paleo_ensemble/timeseries.zarr   : 366M : 'slvol' and 'ice_volume_glacierized' every year since 125ka BP

and some additional data from https://doi.org/10.1594/PANGAEA.940149 in:

    gs://ldeo-glaciology/paleo_ensemble/snapshots1ka.zarr : 50G  : 'thk','mask','topg','usurf','velbar_mag','dbdt','bmelt' every 1000 years since 125ka BP
    gs://ldeo-glaciology/paleo_ensemble/vels5ka.zarr      : 7G   : 'u_ssa','v_ssa','velbar_mag' every 5000 years since 125ka BP


and from reference simulation in https://doi.org/10.5880/PIK.2018.008 (with additional variables):

    gs://ldeo-glaciology/paleo_ensemble/reference18_extra.zarr    : 407M : 'mask,usurf,thk,topg,velbar_mag' every 100 years since 35ka BP
    gs://ldeo-glaciology/paleo_ensemble/reference18_present.zarr  : 6,6M : 'mask,usurf,thk,topg,velbar_mag,dbdt' at present


Use: (see jupyter notebook)

    present_reloaded = xr.open_zarr(gcs.get_mapper('gs://ldeo-glaciology/paleo_ensemble/present.zarr')) 

Glossary:

    'thk'    : ice thickness
    'topg'   : bed topography
    'usurf'  : surface elevation
    'mask'   : floating/grounded mask
    'dbdt'   : change in bed topography
    'bmelt'  : basal melt rate

    'velsurf_mag' : surface velocity (SIA+SSA)
    'velbar_mag'  : vertically averaged velocity (SIA+SSA)
    'u_ssa'       : SSA velocity in x direction 
    'v_ssa'       : SSA velocity in y direction
   
    'slvol'                  : sea-level relevant ice volume
    'ice_volume_glacierized' : total ice volume
