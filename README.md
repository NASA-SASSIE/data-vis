# Welcome to SASSIE Data Visualization Github! 

<p>Thank you for you interest in the SASSIE campaign data!</p>
    <p>SASSIE is a NASA funded project that aims to better understand the role of salinity stratification in the marginal ice zone. In the fall of 2022, SASSIE conducted a field campaign off the Alaskan coast in the Beaufort Sea. This campaign included shipboard measurements as well as 6 remotely piloted/drifing platforms and an ariel campaign. To learn more, please visit <a href="https://salinity.oceansciences.org/sassie.html">https://salinity.oceansciences.org/sassie.html</a></p>

## Use these notebooks to explore SASSIE data! 
<b>In this repository, you will find Jupyter Notebooks that show ways to download and visualize data collected durring the SASSIE campaign. </b>
 <p>The aim of this notebook is to assist in exploratory data analysis by downloading the SASSIE Data from NASA's PODAAC, opening the datasets and displaying their associated metadata, and creating a few visualizations that can be saved to the user's local disc. This notebook was created by Elizabeth Westbrook. For questions and trouble shooting, please email westbrooke@uncw.edu.</p>

<b> The notebooks are accessible through a Jupyter binder. Please visit <a href = "https://mybinder.org/v2/gh/NASA-SASSIE/data-vis/main">https://mybinder.org/v2/gh/NASA-SASSIE/data-vis/main</a></b>

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/NASA-SASSIE/data-vis/main)

## How to Use

There are a total of 10 notebooks that are currently a part of this data visualization set. Each one covers the download and basic visualization of one dataset that was collected durring the SASSIE campaign. There are four sections in each notebook. <b> The sections must all be run in order from top to bottom for the notebook to work properly</b>

1. Credential Entry
2. Data Download and Metadata Veiwing
3. Supporting Code
4. Figure Making Code

Each of these sections is described in more detail below. 

### Section 1 - Credential Entry

<b>WARNING: DO NOT ENTER SENSITIVE CREDENTAILS INTO JUPYTER BINDER! While binder takes precautions to make the notebooks secure (see <a href="https://mybinder.readthedocs.io/en/latest/about/user-guidelines.html"> usage guidelines </a> here) They are still vulnerable to security breahes. Make sure that the cerdentials you use in these notebooks are not used for any sensitve accounts elsewhere </b>

In this section, you must replace 'username' and 'password' (shown below in red) with your credentials for NASA's Earthdata to gain access to published SASSIE data, as well as AMSR Ice data if you choose to use it in any figures (if you do not have an earthdata account, you can <a href= "https://urs.earthdata.nasa.gov/users/new"> create one here </a> for free). 

<img width="1172" alt="Screenshot 2023-08-07 at 9 48 22 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/13b365ea-dc3b-47d9-84a2-9dad7fad4cd4">

### Section 2 - Data Download and Metadata Viewing  

Within this section, there is code to download the dataset from NASA's PODAAC, as well as look into the file and view the variables inside of it using xarray. First, the packages used throughout the notebook are imported. 

<img width="1168" alt="Screenshot 2023-08-07 at 9 53 04 AM" src="https://github.com/NASA-SASSIE/data-vis/assets/127342598/13c4bf5c-1747-4864-a74e-ad6e0b1eb761">







