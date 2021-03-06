- [Project Overview](#project-overview-is-world-happiness-affected-by-gdp-per-capita-population-density-or-covid-lockdown-severity)
  - [Version Control](#version-control)
  - [Important steps before running the code](#important-steps-before-running-the-code)
  - [Repository Overview](#repository-overview)
  - [Project Conclusions](#project-conclusions)
  - [Project Limitations](#project-limitations)
  - [Future Directions](#future-directions)

# Project Overview: Is World Happiness Affected by GDP per Capita, Population Density or Covid-19 Lockdown Severity?
This project creates a shiny dashboard, programmed in R. It aimed to visualise global levels of happiness ratings, GDP per capita, population density per km squared and Covid-19 lockdown severity, using an interactive map. It then sought to combine these, by visualising scatter-plots for the relationship each of these demographic factors had with global happiness levels, as an overlay to the interactive map. To allow the reader to further explore these scatter-plots, full-size interactive graphs were provided. Finally, an interactive table was included for further customised exploration of the dataset.

This project was for a university assignment on data management and visualisation in R.

Link to the published dashboard can be found [here](https://c6gp2m-luke-jenner.shinyapps.io/PSY6422_Project/).

Link to the project's published rmarkdown can be found [here](https://lukejenner6.github.io/PSY6422_Project/).

The dashboard's interface can be seen in this screenshot:
![](www/happiness_dashboard_screennshot.png)

## Version Control
This project was written using **R script**, **version 4.1.2 (2021-11-01)**.

The following packages were used:
* **tidyverse** version 1.3.1
* **here** version 1.0.1
* **rvest** version 1.0.2
* **rgdal** version 1.5.29
* **leaflet** version 2.1.1
* **RColorBrewer** version 1.1.3
* **dplyr** version 1.0.8
* **ggplot2** version 3.3.5
* **plotly** version 4.10.0
* **readr** version 2.1.2
* **ggthemes** version 4.2.4
* **htmlwidgets** version 1.5.4
* **sysfonts** version 0.8.8
* **shiny** version 1.7.1
* **shinydashboard** version 0.7.2
* **htmltools** version 0.5.2
* **DT** version 0.22
* **shinythemes** version 1.2.0

## Important steps before running the code

**Ensure you manually install the fonts from the 'font_download' folder before running the scripts.**

### Working Directory
The working directory should be formatted to include the R scripts and styles.css file in the main folder, with the **graphs**, **data** and **www** subfolders saved here.
Ensure the **here()** function is set correctly to your working directory, by first restarting R and then setting the working directory to the source file location. 

## Repository Overview 
**data:** All data required for the dashboard.

**graphs:** This contains the generated graphs from the **app.R** script. When downloaded as a sub folder, the **app.R** script  will automaticallyy update this folder when run. 

**font_download:** This contains *'Source Sans Pro'* .ttf files to be installed onto the computer. These need to be **installed manually** before executing the code.

**www:** This contains the screenshots that are used in this README file and the project_overview file. It is named www inline with shiny app documentation.

**styles.css:** This contains the css elements for styling the hover over settings and panel sizing.

**index.rmd:** This is an rmarkdown file which contains the codebook and outlines the project's meta-data, goals, and coding process. 

**index.html:** This is the knitted rmarkdown document.

**app.R:** R script for running the dashboard. This is split into three sections: importing and cleaning the data, creating graphs and variables for the dashboard, and executing the dashboard. It is best to view the dashboard in a browser window, as the aesthetics are tailored towards this.

## Project Conclusions
Although the reader is encouraged to freely interpret the data and draw their own conclusions, the author's own inferrences, from this data, are outlined below. The first conclusions were that western countries are happier, richer and more densely populated. However, Covid-19 lockdown severities seemed to differ drastically within continents, with South America seeming to have consistently stricter lockdown measures.

This project also concluded that GDP per capita may have a strong relationship with a country's happiness (where richer countries are happier), Covid-19 lockdown severity a moderate relationship (where stricter countries are happier) and population density has no relationship when the effects of outliers are reduced. However, no definitive conclusions can be made without further statistical analysis.

## Project Limitations
* The entry dates for the Covid-19 lockdown stingency scores (2020-2022) proceed World Happiness Index Scores (2021), so the true effects of Covid-19 lockdowns may be missed.
* There are many NA values for small or developing countries, so the data may be biased away from these countries.
* Population density was massively skewed by highly dense city states (Hong Kong and Singapore), so a log transformation was decided to reduce their influence. This was also conducted to the colour palette of the leaflet map for both population density and GDP per Capita, as to allow for a greater range of polygon colour, and thus better interpretation and information of differences in population density and GDP between countries. However, log transformations make it harder to convey linear relative differences in population density and GDP per capita.

## Future Directions
The community is welcome to improve this code. Some suggestions are:
* This code could be modified to substitute NA values with prior years of records. Data point record years could then be recorded within the interactive data explorer.
* Pop-up labels could be added to the leaflet map to highlight the highest and lowest scoring country for each value. A short explanation on why that country is the richest ect could be given.
* The green text highlights could be altered towards orange, as to be more consistent with the dashboard's style.
* Subtitles and captions could be added to the ggplotly graphs.
* An NA key could be added to the leaflet map legend.
* Statistical analysis could be conducted and write-up included to better infer the relationships between the variables.
* Code to programatically open and install the .ttf font files could be included.

