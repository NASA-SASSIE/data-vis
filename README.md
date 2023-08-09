# Welcome to SASSIE Data Visualization Github! 

<p>Thank you for you interest in the SASSIE campaign data!</p>
    <p>SASSIE is a NASA funded project that aims to better understand the role of salinity stratification in the marginal ice zone. In the fall of 2022, SASSIE conducted a field campaign off the Alaskan coast in the Beaufort Sea. This campaign included shipboard measurements as well as 6 remotely piloted/drifing platforms and an ariel campaign. To learn more, please visit <a href="https://salinity.oceansciences.org/sassie.html">https://salinity.oceansciences.org/sassie.html</a></p>

# Use these notebooks to explore SASSIE data! 
<b>In this repository, you will find Jupyter Notebooks that show ways to download and visualize data collected durring the SASSIE campaign. </b>
 <p>The aim of this notebook is to assist in exploratory data analysis by downloading the SASSIE Data from NASA's PODAAC, opening the datasets and displaying their associated metadata, and creating a few visualizations that can be saved to the user's local disc. This notebook was created by Elizabeth Westbrook. For questions and trouble shooting, please email westbrooke@uncw.edu.</p>

<b> The notebooks are accessible through a Jupyter binder. Please visit <a href = "https://mybinder.org/v2/gh/NASA-SASSIE/data-vis/main">https://mybinder.org/v2/gh/NASA-SASSIE/data-vis/main</a></b>

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/NASA-SASSIE/data-vis/main)

# How to Use

There are a total of 10 notebooks that are currently a part of this data visualization set. Each one covers the download and basic visualization of one dataset that was collected durring the SASSIE campaign. There are four sections in each notebook. <b> The sections must all be run in order from top to bottom for the notebook to work properly</b>

1. Credential Entry
2. Data Download and Metadata Veiwing
3. Supporting Code
4. Figure Making Code

Each of these sections is described in more detail below. 

## Section 1 - Credential Entry

<b>WARNING: DO NOT ENTER SENSITIVE CREDENTAILS INTO JUPYTER BINDER! While binder takes precautions to make the notebooks secure (see <a href="https://mybinder.readthedocs.io/en/latest/about/user-guidelines.html"> usage guidelines </a> here) They are still vulnerable to security breahes. Make sure that the cerdentials you use in these notebooks are not used for any sensitve accounts elsewhere </b>

In this section, you must replace 'username' and 'password' (shown below in red) with your credentials for NASA's Earthdata to gain access to published SASSIE data, as well as AMSR Ice data if you choose to use it in any figures (if you do not have an earthdata account, you can <a href= "https://urs.earthdata.nasa.gov/users/new"> create one here </a> for free). 

<img width="1172" alt="Screenshot 2023-08-07 at 9 48 22 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/13b365ea-dc3b-47d9-84a2-9dad7fad4cd4">

## Section 2 - Data Download and Metadata Viewing  

Within this section, there is code to download the dataset from NASA's PODAAC, as well as look into the file and view the variables inside of it using xarray. First, the packages used throughout the notebook are imported. 

<img width="1168" alt="Screenshot 2023-08-07 at 9 53 04 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/13c4bf5c-1747-4864-a74e-ad6e0b1eb761">

### Downloading the Data

Next, a directory is created within the binder to store the downloaded data using the code below. You can alter this path to change where the data is stored within the notebook. 

<img width="1164" alt="Screenshot 2023-08-07 at 10 02 37 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/b1604064-6d6c-4bd8-8d53-cc321efa8f54">

By default, the notebook will create a new folder called 'Data' and then a sub folder for each dataset. 

For security reasons, you are not able to use the code to download the datasets to your local directory if you are accessing the notebooks using binder. Instead, you must go to the folder within the binder where the data is stored, right click on the file you wish to download, and click 'Download'. 

<img width="478" alt="Screenshot 2023-08-07 at 2 22 15 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/2e4cc9ab-8eb2-4ed2-856e-9a6efaa6a27f">

If you are looking for a simpler way to download SASSIE data to your local disk, without any visualization, you can access them on PODAAC <a href = "https://podaac.jpl.nasa.gov/"> here <a/> or use the SASSIE data download tool <a href = "https://salinity.odyseallc.net/sassie-data"> here </a>

The next block of code in the data download section sends your credentials and a request for the files of interest to NASA's PODAAC. <b> This block of code should not be changed: </b>

<img width="1170" alt="Screenshot 2023-08-07 at 12 40 58 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/13c4bfb1-7d75-43d2-95b8-4ced6b5543bb">

If you have already run this block of code and the file is already in the specified directory above, it will not re-download the data. 

### Viewing the Metadata

After the dataset has been downloaded, the metadata viewing subsection will use the xarray package to open up this clickable html table showing the names of the variables in the file. You can expand each section for more details or to preview the data by clicking the arrows on the left hand side of the table and the symbols on the right hand side: 

<img width="1169" alt="Screenshot 2023-08-07 at 12 44 20 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/9e61a08d-7b94-4151-913a-3f0b5e07930c">

## Section 3 - Supporting Code 

The purpose of this section is to act as a precursor to running the figure making code in the next section which makes exploratory data analysis figures. The contents of this section will depend on what functions are appropriate for the visualization of each data set, so not all of the code described below is included in every notebook.  The first block in this section will define a directory within the binder where the figures will be stored: 

<img width="1167" alt="Screenshot 2023-08-07 at 2 19 34 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/0041fdbc-3c8d-48d1-941b-1bfc7edd78cc">

The default path here will create a new folder called 'Figures' with a subfolder for each dataset. Like the data directory created in the previous section, this can be changed depending on the user's preference. Figures can also be manually downloaded onto the local machine the same way datasets can. 

Some of the map figures optionally use AMSR Ice Concentration data and NOAA Bathymetry Data. The following block of code creates a directory within the binder to store AMSR ice data and also remotely accesses the NOAA bathymetry data

<img width="1168" alt="Screenshot 2023-08-07 at 3 04 47 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/bc8ba221-b877-4807-8cd7-4b19dc154abd">

The SASSIE cruise was broken up into five distinct 'plays', and it may be useful to look at shipboad data on a play-by-play basis. Theerefore, for the shipboard data sets, the supporting code section contains a block that defines the start and end date of each play so that they can be easily referenced later 

<img width="1169" alt="Screenshot 2023-08-08 at 11 42 51 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/54dbb4f7-5243-4286-aec4-ec5f6c314b30">

For non-shipboard datasets, there is an option to additionally plot the shiptrack on the maps that are produced as a reference. For this, the shipboard TSG file must be downloaded. The supporting code section contains a block of code that does this. 

<img width="1172" alt="Screenshot 2023-08-08 at 11 54 25 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/fe29f5bb-ac49-41a0-ae90-0c4ee76d30e9">

##  Supporting Code Functions 

This section also defines some functions that will be used in the figure making code. These functions simplify the figure making code. Some of the functions can be customized to change the features of the figures that are made. Below, each of these functions is explained:

### def_variable_attributes(var)

<img width="1164" alt="Screenshot 2023-08-07 at 2 30 22 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/08cc8770-60ef-412b-b998-53b896bb09d1">

The purpose of this function is to define a color palette and a label for each variable found in the file. Because different platforms collected different data, it will change from dataset to dataset. The color palettes are held as consistant as possible thoughout all the notebooks.   

#### Inputs

var (string)  -  The name of the variable within the file that needs a label and a color palette 

#### Outputs

colormap (string)  - The name of the colormap that will be used to represent the variable on a plot

var_label (string) - The label that will be used to label the variable on an axis or a colorbar 

### map_study_area(latmin,latmax,lonmin,lonmax)

<img width="1168" alt="Screenshot 2023-08-07 at 2 56 46 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/5306e8d7-2a09-4ea2-93fd-592b3f6190e9">

This function creates a map of the area in which the SASSIE campaign took place that includes markings for land and the rivers, as well as stars for the cities of Utqiagvik and Deadhorse when they are within the specified lat and lon range. The lat and lon range can be adjusted when the function is called to zoom in or out on the campaign area. 

#### Inputs

latmin (float)  - The minimum latitude limit of the map <br>
latmax (float) - The maximum latitude limit of the map <br>
lonmin (float) - The minimum longitude limit of the map <br>
lonmax (float) - The maximum longitude limit of the map <br>

#### Outputs
fig (global) - The handle for the map figure that will be used as a base for the map being made <br>
ax (global) - The handle for the set of axes on which data will be plotted on the map


### make_3d_grid(latmin,latmax,lonmin,lonmax,dmin,dmax)

<img width="1169" alt="Screenshot 2023-08-08 at 11 46 07 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/57d42df3-8c0c-4308-856f-801ba4fce42e">

This function is used as a substitute for a map when there is data taken at multiple levels below the surface. It will only appear in notebooks for datasets with a depth or sea pressure dimension. It creates a set of 3d axis and formats the figure so that it is ready to have data added to it. 

#### Inputs

latmin (float)  - The minimum latitude limit of the grid <br>
latmax (float) - The maximum latitude limit of the grid <br>
lonmin (float) - The minimum longitude limit of the grid <br>
lonmax (float) - The maximum longitude limit of the grid <br>
dmin or pmin (float) - The minimum depth or pressure limit of the grid <br>
dmax or pmax (float) - The maximum depth or pressure limit of the grid <br>

#### Outputs

fig (global) - The handle for the 3d grid figure that will be used as a base for the figure being made <br>
ax (global) - The handle for the set of axes on which data will be plotted on the grid


### add_ice_data(start_date,end_date)

<img width="1168" alt="Screenshot 2023-08-07 at 3 29 41 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/2cf596dd-1210-4160-b6fe-b2684929a5f7">

First, this function will find and download the AMSR ice product that is closest in time to the start and end date specified. Then, it will plot the ice products on the current map figure. The product from the end date will be plotted using the 'Reds' color pallette, and then the product from the start date will be plotted using the 'Blues' color palette on top of it. 

Some notebooks instead have a version of this function that only plots ice data from one specified date, such as the date of a deployment. 

#### Inputs 

start_date (datetime(yyy,mm,dd)) - The date at the beginning of the time range being plotted <br>
end_date (datetime(yyyy,mm,dd)) - The date at the end of the time range being plotted <br> 

### add_bathy_data(latmin,latmax,lonmin,lonmax)

<img width="1164" alt="Screenshot 2023-08-07 at 3 39 54 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/0d827bcf-0717-4d62-8030-fbea975c32b0">

This function will take the bathymetry data that was remotely accessed from NOAA and plot its contours on the map. The data is pre-indexed to include only every fifth data point within the specified lat and lon range to avoid slowing down the mapping code significantly. Contour levels are defined every 300 meters between 1000 and 6000 meters depth. 

### Inputs

latmin (float)  - The minimum latitude limit of the map <br>
latmax (float) - The maximum latitude limit of the map <br>
lonmin (float) - The minimum longitude limit of the map <br>
lonmax (float) - The maximum longitude limit of the map <br>

### add_ship_track()

<img width="1167" alt="Screenshot 2023-08-08 at 11 59 01 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/08e60896-e27a-479c-97bd-5b32b3a25ec1">

When called, this function adds the track of the R/V Woldstad to a map. 

## Section 4 - Figure Making Code: 

Like the Supporting Code section, the Figure Making Section will only include the code that is appropriate for the dataset at hand. The code for figure making is organized as functions which have various input arguments that allow for customization of the figures where appropriate. Further customization will require changes to the code itself. Under each function there is a block of code that shows examples of the function being used, which will produce some example plots when the code is run without any changes. These blocks can be adjusted by the user to fit their needs. 
## Figure Making Functions 

### Show the Time and Location of Data Collection
Each Notebook will have code to map out where in the campaign area the data were collected on a latitude - longitude axis, colored by date collected. 

<img width="1166" alt="Screenshot 2023-08-08 at 7 57 14 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/7171c1ae-49d4-4752-ad8f-bb7820f5c623">


#### Inputs

play (int) or deployment (int)  - Avalible for data that was taken at the surface level (like the TSG, MET, and Jet SSP). Limits the mapped data to only a certain subset of the data within a time range defined by a certain play or deployment (The date range of each play is defined in the supporting code when relevant. Set play=6 to show the whole campaign) <br>

ice_data = False (boolean)  - can optionally be set to True to add AMSR ice data at the beginning and end of the mapped time range. 

bathy_data = True (boolean)  - can optionally be set to False to exclude NOAA bathymetry data from the map 

ship_track = True (boolean) - exists for datasets from remote and drifting platforms. By default, this maps the track of the ship as a solid black line for comparison with the track of the independant platform. Can optionally be set to False to exclude the shiptrack line from the map. 

#### Outputs

Below are some examples of figures produced using this mapping code. 

<img src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/56bce5cd-0a16-4450-8717-4e43e4f4d9d0" alt = "SASSIE_SHIPTRACK_TSG_entire_campaign" width = 262 height=225>
<img alt="cCTD_deployment_map" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/f52adc4a-4bca-4ef5-ad89-40e4d7ee61d2" width = 262
 height=225>
<img alt = "ALTO_ALAMO_paths" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/a617857f-9609-439a-97c3-7f1b2fa218ae" width = 262 height = 225>



### Mapping Datasets Colored by a Variable in the File

This function is very similar to the function described above, except that it colors the track of the data set by some ocean or atmospheric variable taken at the water's surface. If there are not surface level variable in a data set, such as in the uCTD and cCTD this function is not included. 


<img width="1167" alt="Screenshot 2023-08-08 at 9 43 02 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/77b1ed11-31ea-4d6f-8d03-afdc7adc0d42">

For the datasets that include wind speed and direction data (jetSSP and Shipboard Meteorology), there is a special variation of this function that maps the data as a quiver plot with arrows with the direction and magnitude representing the wind. An example is shown below. 


#### Inputs 

var (string)  - The name of the variable, as it appears in the netCDF file, that is to be coloring the track on the figure. 

var_min (float) - The lower limit of the colorbar that will measure the variable described by var. 

var_max (float) - The upper limit of the colorbar that will measure the variable described by var. 

play (int) or deployment (int)  -  Limits the mapped data to only a certain subset of the data within a time range defined by a certain play or deployment (The date range of each play is defined in the supporting code when relevant. Set play=6 to show the whole campaign) <br>

ice_data = False (boolean)  - can optionally be set to True to add AMSR ice data at the beginning and end of the mapped time range. 

bathy_data = True (boolean)  - can optionally be set to False to exclude NOAA bathymetry data from the map 

ship_track = True (boolean) - exists for datasets from remote and drifting platforms. By default, this maps the track of the ship as a solid black line for comparison with the track of the independant platform. Can optionally be set to False to exclude the shiptrack line from the map. 

#### Outputs 

Below are some examples of figures produced using this mapping code. 

<img alt = "SASSIE_jet_SSP_Deployment5_temperature_surface" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/1feebdc1-7f05-47eb-94a2-f0c0cb5e88ce" width = 262 height = 225>
<img alt = "SASSIE_SHIPBOARD_MET_entire_campaign" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/c1584436-1d22-4df5-bf7d-88a10d6d9cdc" width = 262 height = 225>
<img alt = "SASSIE_SHIPBOARD_TSG_play_4" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/90fc757e-5e20-4f8f-b690-a5972be92cb3" width = 262 height = 225>

### Make a 3d Representation of Trajectory Profile Data 

These functions will vary slightly between all the notebooks that include them, which are the notebooks for datasets that have vertical profile data. The example below is for the ALTO/ALAMO floats. 

<img width="1169" alt="Screenshot 2023-08-08 at 12 06 43 PM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/2a96e103-ade0-4ef4-829c-58a10214aa70">

#### Inputs 

float_number/play/buoy/deployment (int)  - Defines which data out of the whole set needs to be plotted (ex: which float's profiles to plot or data from which play of a shipboard data set like the uCTD or cCTD) 

var (string)  - The name of the variable, as it appears in the netCDF file, that is to be coloring the profiles on the figure. 

#### Outputs 

Below are some examples of 3d grid plots that can be made using these functions 

<img alt = "uCTDsalinity202209190000_202209230000" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/f4ecb6d8-dbe8-402f-a37f-d53b0504dc7f" width = 262 height = 225>

<img alt = "SASSIE_jet_SSP_Deployment3_temperature" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/93c5999d-f22e-45f4-9553-5e5da0a9ab27" width = 262 height = 225> 

<img alt = "ALTO_ALAMO_temperature_Float_9098" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/389e35e1-21de-48d5-b02f-acf90872e812" width = 262 height = 225>

### Make a 2D Representation of Trajectory Profile data 

Rather than put the trajectory profile data on a 3D lat-lon-depth axis, there is another function included for the trajectory profile datasets that plots this data on a 2D time-depth axis. 

<img width="1168" alt="Screenshot 2023-08-09 at 9 14 33 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/9ed059c5-234f-4587-85f5-052a81015370">

#### Inputs 

start_time (datetime.datetime) - The minimum time of the date range covered by the plot 

end_time (datetime.datetime) - The maximum time of the date range covered by the plot

var(string) - The name of the variable, as it appears in the netCDF file, that the data points on the 2D plot should be colored by 

CTD_unit (int)  - In the case of the Under Ice Float data, this specifies which data from the multiple CTDs on the platform should be used. 

#### Outputs 

<img width="589" alt="Screenshot 2023-08-09 at 9 18 27 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/51cf9b90-43c7-4b2c-b48e-13ad0b75034a">


### Plot Variables from the Dataset on a 2D Time Series Axis 

This function will vary widely between datasets because the figure it produces is meant to provide a summary of the most important variables in the file. Some of the functions will produce 1 or 2 subplots while others produce more compliated figures with 3 or 4 subplots. The example below is a less complicated function for the TSG data timeseries. 


<img width="1168" alt="Screenshot 2023-08-08 at 9 54 18 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/cd09ac99-ddd9-474e-a928-cc94d6799149">

#### Inputs

play (int) or deployment (int)  -  Limits the plotted data to only a certain subset of the data within a time range defined by a certain play or deployment (The date range of each play is defined in the supporting code when relevant. Set play=6 to show the whole campaign) <br>

var1,var2,...etc (string)  - Some of the timeseries function, like that of the SWIFT buoy dataset, allow the user to choose which variables they want plotted. These inputs are the string names of the variables as they appear in the netCDF file
 
#### Outputs

Below is a simple example (TSG) and a more complicated example (SWIFT buoys) of a figure produced using this code. 

<img alt = "SASSIE_SHIPBOARD_TSG_entire_campaign" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/485ccddd-90b7-42d8-a9b9-5b24e70cbcfe" width = 350 height = 300> 

<img alt = "SWIFTall_Playall_salinity_water_temperature_wind_speed" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/db894808-c9ad-453d-8057-09e982eabd06" width = 350 height = 300>


### Plot Individual Profiles from a profile dataset 

For the datasets that include vertical profiles, a function is includes that can plot individual profiles, either by the profile number(if it is included in the file) or by finding the closest profile to a particular date. Some notebooks have two versions of this function to create the figures in two different formats - one where temperature and salinity are on two seperate subplots and one where they share the same set of axis. 


<img width="1165" alt="Screenshot 2023-08-09 at 8 30 20 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/791a16fd-1baa-454f-ac9d-d4fd56864208">

<img width="1166" alt="Screenshot 2023-08-09 at 8 37 24 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/778cb727-a6ab-4c70-aaff-9d474cc2bfab">

#### Inputs

cast_number (int) or date (datetime.datetime) - the input argument that tells the function which profile to plot. If cast_numbers are not included in the data files, a date can be used which will find the closesst profile in time to that date. 

float_number (int) or other platform number  - If there are multiple platforms int eh dataset (ex. multiple alto alamo floats which are deployed int he same time range) it is necessary to specify which of these platforms the data should come from with this argument. 

#### Outputs 

Below is an example of the ALTO_ALAMO profiles in a same axis format and an example of the uCTD profiles in the two subplot format. 

<img alt = "float9101_profile_20220921025300" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/716bb460-8e99-4e86-a67d-192b0309674e" width = 350 height = 300>

<img alt = "uCTD_profile1000_20220921143317" src = "https://github.com/NASA-SASSIE/data-vis/assets/127342598/28878b0c-144f-4c20-81fd-2051b56a2b90" width = 350 height = 300>



### T-S Plots of CTD data 

The uCTD and cCTD notebooks each have  a function that scatters data from a given time range on a temperature - salinity axis and colors the points by a coordinate variable (time, depth, latitude, longitude) of the user's choice. 

<img width="1167" alt="Screenshot 2023-08-09 at 8 47 42 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/253e0bee-cecd-4cc2-87f1-4cba4650bbcc">

#### Inputs

start_time (datetime.datetime)  - The beginning of the time range to be covered by the scatter plot. 

end_time (datetime.datetime) - The end of the time range to be covered by the scatter plot. 

var (string)  - The name of the coordinate variable, as it appears in the netCDF file, that the scatter points will be colored based on. 

#### Outputs 

<img width="606" alt="Screenshot 2023-08-09 at 8 51 29 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/d19bb71d-77ba-4123-9fd4-95ce3a264755">

### Histogram of Delta 18O Bottle Data

The bottle data notebook has an option to create a histogram of the temperatures and delta 18O ratios collected throguhout the campaign

<img width="1168" alt="Screenshot 2023-08-09 at 8 56 37 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/d7c71fb9-0f4f-40a0-a918-e19d79902ac0">

#### Inputs

var (string) - Should either be 'temperature' or 'd18O' depending on which variable from the netCDF file the user is making a histogram of. 

#### Outputs 

<img width="454" alt="Screenshot 2023-08-09 at 8 58 37 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/984ff6ed-499b-4f47-ba42-8c9bcb0f7028">

### 
