# pangeo-pismpaleo
Collection of notebooks to convert PISM simulation data to zarr format and to plot data

Zarr ensemble data from https://doi.pangaea.de/10.1594/PANGAEA.909728 can be found in:

    gs://ldeo-glaciology/paleo_ensemble/present.zarr    : 823M : 'thk','mask','topg','usurf','velsurf_mag','dbdt' at present
    gs://ldeo-glaciology/paleo_ensemble/extra.zarr      : 361M : 'mask' every 1000 years since 125ka BP
    gs://ldeo-glaciology/paleo_ensemble/timeseries.zarr : 522M : 'slvol' and 'ice_volume_glacierized' every year since 125ka BP
    gs://ldeo-glaciology/paleo_ensemble/snapshots.zarr  : 2,3G : 'thk','mask','topg','usurf' every 5000 years since 20ka BP

and from reference simulation in https://doi.org/10.5880/PIK.2018.008:

    gs://ldeo-glaciology/paleo_ensemble/reference18_extra.zarr      : 348M : 'mask,usurf,thk,topg' every 100 years since 35ka BP

	    

Use:

    present_reloaded = xr.open_zarr(gcs.get_mapper('gs://ldeo-glaciology/paleo_ensemble/present.zarr')) 
