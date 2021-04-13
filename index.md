# Data products

Gridded mooring data is availabe for download on the SAMS [THREDDS](https://thredds.sams.ac.uk/thredds/catalog/catalog.html)server [here](https://thredds.sams.ac.uk/thredds/catalog/lewysd/catalog.html)

*Table 1. Variable names from T_S_gridded.nc*

|     Variable    |     Description                                                      |     Unit                             |
|-----------------|----------------------------------------------------------------------|--------------------------------------|
|     TIME        |     Time                                                             |     days since 1st   January 1950    |
|     PRES        |     Sea water pressure                                               |     Decibar                          |
|     TG_EAST     |     Sea water temperature at   eastern boundary                      |     o C                              |
|     TG_WEST     |     Sea water temperature at   western boundary                      |     o C                              |
|     SG_EAST     |     Sea water salinity at   eastern boundary                         |     g kg-1                           |
|     SG_WEST     |     Sea water salinity at western   boundary                         |     g kg-1                           |
|     U_WEST_1    |     current speed u-direction   at western boundary (0-1600 m)       |     cm s-1                           |
|     V_WEST_1    |     current speed v-direction   at western boundary (0-1600 m)       |     cm s-1                           |
|     W_WEST_1    |     current speed w-direction   at western boundary (0-1600 m)       |     cm s-1                           |
|     U_WEST_2    |     current speed u-direction   at western boundary (1000-1800 m)    |     cm s-1                           |
|     V_WEST_2    |     current speed v-direction   at western boundary (1000-1800 m)    |     cm s-1                           |
|     W_WEST_2    |     current speed w-direction   at western boundary (1000-1800 m)    |     cm s-1                           |
|     U_EAST      |     current speed u-direction   at eastern boundary                  |     cm s-1                           |
|     V_EAST      |     current speed v-direction   at eastern boundary                  |     cm s-1                           |
|     W_EAST      |     current speed w-direction   at eastern boundary                  |     cm s-1                           |


## 1. Mooring data

### Temperature and salinity data from microCATS
The microcat data is made up of Conductivuty, Tempertaure (° C), and Pressure (db) records calibrated using seawater samples and in-situ CTD profiles and corrected for sensor drift. The instrument data is fitted on to a regular 2-hour time grid using linear interpolation.  Conductivity data is converted first to Practical Salinity (PSU) then Absolute Salinity, SA (g kg-1). Temperature (° C) is converted to Conservative Temperature, CT (° C). Salinity data is de-spiked for each instrument by excluding data outside of a cut-off of deployment-median salinity ± 10 g kg-1. Remaining data is further de-spiked up to n(=5) times through a loop where the cut off is one standard deviation from the deployment-median during each pass.  Contemporaneous temperature data are also excluded. SA, CT, and P are low-pass filtered with MATLABs zero-phase digital filtering function; filtfilt, using a Butterworth filter design, 6th order, with cut-off frequency of ½(days). Gaps in the filtered data of more than 10 days are populated with fill values. The resulting data is fitted to a regular 2-hour time grid using linear interpolation. SA, CT, and P from all deployments are concatenated and then fitted to a regular 12-hour horizontal time grid and 20 db vertical pressure grid using linear interpolation. Salinity data is de-spiked n(=5) times through a loop where the cut off is 3.5 standard deviation from the time-series median during each pass.  Contemporaneous temperatures are also excluded. Linear Interpolation across vertical pressure grid of data values since de-spiking.  

![png](img/EAST_TS.png)

*Gridded and merged temperature, salinity, and density from the eastern boundary *

![png](img/WEST_TS.png)

*Gridded and merged temperature, salinity, and density from the eastern boundary *

### Current data from aquadopps

![png](img/WEST_1_NOR_U.png)

*Gridded current in u direction from the eastern boundary *

![png](img/WEST_1_NOR_V.png)

*Gridded current in u direction from the eastern boundary *

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/ScotMarPhys/ScotMarPhys.OSNAP-Mooring-Processing.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ScotMarPhys/ScotMarPhys.OSNAP-Mooring-Processing.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
