# Data Visualization Project

## Data

The data visualized for my project is the global tree coverage data from the Global Forest Service. This dataset details the change in tree cover across the globe between 2000 and 2021 for different countries. It was taken from satellite data by Hansen et. al (2013) with changing data collection methodology after this year. For this dataset, questions I was be interested in investigating included: are there differences in deforestation in different areas of the globe? Can these differences be related to economic status? Can they be related to starting forest density? What areas show reforestation?

Sources: https://www.globalforestwatch.org/dashboards/global/?category=forest-change

https://www.science.org/doi/10.1126/science.1244693

From the data coversheet: "This data set includes tree cover extent, aboveground live woody biomass (AGB) stocks and densities, annual tree cover loss, annual forest greenhouse gas (GHG) emissions, average annual forest CO2 removals (sequestration), and average annual net GHG flux at the country and first (state, province) sub-national levels. 
- Tree cover loss and emissions are available as annual data for 2001-2021. 
- Emissions, removals and net flux are available as annual averages for 2001-2021. 
- Tree cover is available for 2000 and 2010. 
- Aboveground biomass stocks and densities are available for 2000. 
The tree cover data was produced by the University of Maryland's GLAD laboratory in partnership with Google (Hansen et al. 2013). Carbon densities, emissions, removals, and net flux (megagrams CO2e/yr) are from Harris et al. 2021. The emissions data quantifies the amount of carbon dioxide emissions to the atmosphere where forest disturbances have occurred, and includes CO2, CH4, and N2O and multiple carbon pools. Removals includes the average annual carbon captured by aboveground and belowground woody biomass in forests. Net flux is the difference between average annual emissions and average annual removals; negative values are net sinks and positive values are net sources. 
Tree cover loss, tree cover extent, and AGB stock and density are presented for percent canopy cover levels >10%, 15%, 20%, 25%, 30%, 50% and 75% in 2000. Emissions, removals, and net flux are presented only for percent canopy cover levels >30%, 50%, and 75% in 2000, plus areas with tree cover gain regardless of percent canopy cover. We recommend that you select your desired percent canopy cover level before your analysis and use it consistently throughout analyses. The Global Forest Watch website uses a >30% canopy cover threshold as a default for all statistics."

The attributes of the dataset are:
| Column No. | Attribute Name | Data Type | Description |
| --- | --- | --- | --- |
| 1 | country | Categorical | Country |
| 2 | threshold | Ordinal | Percent canopy cover level in 2000 |
| 3 | area_ha | Quantitative | Country Area |
| 4 | extent_2000_ha | Quantitative | Forest extent in 2000 |
| 5 | extent_2010_ha | Quantitative | Forest extent in 2010 |
| 6 | gain_2000-2012_ha | Quantitative | Forest gain between 2000 and 2012 |
| 7-27 | tc_loss_ha_year | Quantitative | Tree cover loss per in specified year |

All data given in hectares.

## Prototypes

I’ve created a couple proof of concept visualizations of this data. The first is a scatter plot which makes use of color mapping in order to indicate the value of particular y-values. This was useful in finding a color scheme which would be useful in protraying the final data set and mapping it to data values.

<a href="https://vizhub.com/LaurenStanley/2129c09c6aad4dfdbd075f0e30ad42de">
  <img src="Pseudo1.PNG" width="50%" />
</a>

The next proof of concept was to use the real data set to create scatterplot of a similat structure. This allowed me to test the color scheme on the real dataset, as well as filter out the data of interest.

<a href="https://vizhub.com/LaurenStanley/348ea45f7c1844dabb44aa85975b5af3">
  <img src="Pseudo2.PNG" width="50%" />
</a>

I added axes labels to the scatter plot to increase clarity. The delta values, which are derived from the raw data, were be used in the final implementation.

<a href="https://vizhub.com/LaurenStanley/cc38ae77d9244fa0a46e1646886eff74">
  <img src="Pseudo3.PNG" width="50%" />
</a>

## Questions & Tasks

The following tasks and questions will drive the visualization and interaction decisions for this project:

 * What areas of the world are experiencing the most deforestation?
 * Are we losing denser forest at the same rate as more sparse forest?
 * Are there any countries exhibiting anomolous behavior in their deforestation habits?

## Sketches

These sketches illustrated my ideas for visualizing this data set. The first sketch shows how the different years will show the differences in tree level.

<img src='Trees.gif'  width="30%" height="30%">

This second sketch shows a basic idea for interaction, where the user could use their cursor to highlight a particular country and then see details about the deforestation data.

<img src='Trees (1).gif'  width="30%" height="30%">

Lastly, this sketch shows the intended interactive sliders, which will allow the user to see the data filtered by year and by forest density threshold.

<img src='Trees(2).gif'  width="30%" height="30%">

## Milestones

* 2/19 - Work on porting data from scatterplot to map
* 2/26 - Finish implementing map for one year and threshold value
* 3/5 - Controllable filtering by year
* 3/12 SPRING BREAK
* 3/19 - Controllable filtering by threshold
* 3/26 - Implement sliders to manage all filtering
* 4/2 - Implement mouseover detail view
* 4/9 - Implement additional plot detail for mouseover country, i.e. line plot of tree cover
* 4/16 - Buffer Week
* 4/23 - Wrap up and Report Writing 

## Results
My final visualization can be found here: https://vizhub.com/LaurenStanley/a18ca5caa2024910b1db12654fb41ad8
<img src='Final.png'>
The features of this final implementation include a drop down menu where the starting forest density can be changed. Each country shows the percentage change in forest cover between 2000 and 2010. By highlighting a specific country with the mouse, a user can see a detailed view of how much the forest coverage has changed for that threshold level.

For instance, at 30% threshold highlighting one country would show the forest coverage area in 2010 at 30% density or high - the forest coverage area in 2000 at 30% density of higher/ the total area of the country. Shown below, we can see that Canada has a .33% increase in total forest coverage that is at least 30% dense.

<img src='FinalMouse.png'>

Lastly, as a proof of concept, the data is shown at threshold 0% - no change is registered anywhere on the planet because all landmass qualifies as forest at or above 0% denisty.

<img src='Land.png'>
