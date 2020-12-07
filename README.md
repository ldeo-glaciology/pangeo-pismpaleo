# pangeo-pismpaleo
Collection of notebooks to convert PISM simulation data to zarr format and to plot data

Zarr ensemble data collection can be found in:

    gs://ldeo-glaciology/paleo_ensemble/present.zarr    : 823M : 'thk','mask','topg','usurf','velsurf_mag','dbdt' at present
    gs://ldeo-glaciology/paleo_ensemble/extra.zarr      : 361M : 'mask' every 1000 years since 125ka BP
    gs://ldeo-glaciology/paleo_ensemble/timeseries.zarr : 522M : 'slvol' and 'ice_volume_glacierized' every year since 125ka BP
    gs://ldeo-glaciology/paleo_ensemble/snapshots.zarr  : 2,3G : 'thk','mask','topg','usurf' every 5000 years since 20ka BP
	    

Use:

    present_reloaded = xr.open_zarr(gcs.get_mapper('gs://ldeo-glaciology/paleo_ensemble/present.zarr')) 
