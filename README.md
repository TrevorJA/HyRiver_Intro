This tutorial highlights the [HyRiver](https://github.com/hyriver/hyriver.github.io) software stack for Python, which is a very powerful tool for acquiring large sets of data from various web services. 

# HyRiver Introduction
The [HyRiver](https://github.com/hyriver/hyriver.github.io) software suite was developed by [Taher Chegini](https://github.com/cheginit) who, in their own words, describes HyRiver as:

>"... a software stack consisting of seven Python libraries that are designed to aid in hydroclimate analysis through web services."

This description does not do justice to the capability of this software. Through my research I have spent significant amounts of time wrangling various datasets - making sure that dates align, or accounting for spatial misalignment of available data. The HyRiver suite streamlines this process, and makes acquistion of different data from various sources much more efficient. 

Here, I am going walk through a demonstration of how to easily access large amounts of data (streamflow, geophysical, and meteorological) for a basin of interest. 

Before going through the code, I will highlight the three libraries from the HyRiver stack which I have found most useful: `PyGeoHydro`, `PyNHD`, and `PyDaymet`.

### PyGeohydro
[`PyGeoHydro`](https://github.com/hyriver/pygeohydro) allows for interaction with eight different online datasets, including: 
* [USGS National Water Information System (NWIS)](https://nwis.waterdata.usgs.gov/nwis)
* [NCAR Catchment Attributes and Meteorology for Large-sample Studies (CAMELS)](https://ral.ucar.edu/solutions/products/camels)
* [USGS Water Quality Portal](https://www.waterqualitydata.us/)
* [US ACE National Invetory of Dams (NID)](https://nid.sec.usace.army.mil/#/)

In this tutorial, I will only be interacting with the USGS NWIS, which provides daily streamflow data. 

### PyNHD
The [`PyNHD`](https://github.com/hyriver/pynhd) library is designed to interact with the [National Hydrography Dataset (NHD)](https://www.usgs.gov/national-hydrography/national-hydrography-dataset)and the [Hydro Network-Linked Data Index (NLDI)](https://labs.waterdata.usgs.gov/about-nldi/index.html).

#### NHDPlus (National Hydrography Dataset)
The NHD defines a high-resolutioon network of stream linkages, each with a unique idenfier (ComID).  

#### NLDI (Network-Linked Data Index)
The NLDI aids in the discovery of indexed information along some NHD-specified geometry (ComIDs). The NLDI essentially tranverses the linkages specified by the NHD geometry and generates data either local or basin-aggregated data relative to a specific linkage (ComID).

As will be seen later in the tutorial, the NLDI is able to retrieve atleast 126 different types of data for a given basin...

### PyDaymet
The [PyDaymet GirHub repository](https://github.com/hyriver/pydaymet) summarizes the package as:

>"\[providing] access to climate data from Daymet V4 database using NetCDF Subset Service (NCSS). Both single pixel (using `get_bycoords` function) and gridded data (using `get_bygeom`) are supported which are returned as pandas.DataFrame and xarray.Dataset, respectively."


## Tutorial outline:
0. Installation
1. Retrieving USGS Water Data
2. Retrieving Geophysical (NLDI) Data
2. Retrieving Daymet Data

[The HyRiver repository](https://github.com/hyriver/hyriver.github.io) contains various examples demonstrating the use of the various libraries. I would definitely recommend digging in deeper to these, and other [HyRiver](https://github.com/hyriver/hyriver.github.io) documentation if this post piques your interest.  
