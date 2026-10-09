# Weather Analysis with ERA5

This project explores the atmospheric conditions on day in 2003 by using ERA5 reanalysis data from the Copernicus Climate Data Store. I used Python to process the data and create meteorological maps for a selected city and date.

## Project Goals

The project focuses on visualizing atmospheric conditions at different pressure levels and near the Earth's surface. It also provides a starting point for interpreting the weather situation using the generated maps.

## Maps

The project produces five maps:

1. **Wind at 250 hPa**
2. **Geopotential-height contours and isotherms at 500 hPa**
3. **2 m air temperature**
4. **Smoothed mean sea-level pressure with 10 m horizontal wind**
5. **Accumulated precipitation**

The selected city's location is marked on the maps using its geographic coordinates.

## Data

The data come from the Copernicus Climate Data Store's ERA5 reanalysis datasets:

- [ERA5 pressure-level data](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-pressure-levels?tab=download)
- [ERA5 single-level data](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels?tab=download)

The project uses pressure-level fields for geopotential, temperature, and the U- and V-components of wind, alongside single-level fields for near-surface temperature, wind, mean sea-level pressure, and precipitation.

The data files are stored in NetCDF format. To reproduce the analysis, download the data for the date and geographic region you want to study, then update the filenames and paths in the code accordingly.

## Tools and Libraries

- **Python**
- **NumPy** — numerical calculations
- **xarray** — loading and working with NetCDF datasets
- **Matplotlib** — plotting
- **Cartopy** — geographic maps and map features
- **SciPy** — Gaussian smoothing of mean sea-level pressure

Install the dependencies in your Python environment:

```bash
python -m pip install numpy xarray matplotlib cartopy scipy netCDF4
```

## Running the Project

1. Download the required ERA5 pressure-level and single-level data.
2. Extract the single-level download and locate the NetCDF files.
3. Put the data files in the project directory, or update their paths in the code.
4. Run the Python script or Jupyter notebook to generate the maps.
5. Refer to the plots to examine the atmospheric conditions on the selected date.

Expected input filenames follow this pattern:

```text
plYYMMDD.nc
sfYYMMDD.nc
tpYYMMDD.nc
```

Here, `YYMMDD` represents the selected date.

## Notes on the Data

The ERA5 fields use their dataset-defined units. Before plotting, the code should account for the relevant unit conversions, including temperature, pressure, precipitation, and geopotential where necessary. The dataset variables and metadata should be inspected before processing.

The mean sea-level pressure map can also be plotted with and without Gaussian smoothing to compare the effect of smoothing on the pressure contours.


## References

- [Copernicus Climate Data Store — ERA5 pressure-level data](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-pressure-levels?tab=download)
- [Copernicus Climate Data Store — ERA5 single-level data](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels?tab=download)
- [Cartopy documentation](https://scitools.org.uk/cartopy/docs/latest/reference/index.html)
