# Lab6: Interactive Map
## Introduction

This tutorial uses a Python library called Folium and pandas to create several interactive maps. The first two maps are:
* A choropleth map which shades in LA County zip codes based on how many Starbucks are contained in each one (and you'll learn why this is a terrible idea!)
* A precise map of all Starbucks' locations in LA County

The third map is the map the unemployment rate by state by 2012.

## Result
The first map shows the number of Starbucks in each zip code.

![](images/zip_starbuck_LA.JPG)

The second map shows the distribution of Starbucks in LA. (I changed the marker to the Starbuck logo).

![](images/distribution_starbuck_LA.JPG)

The Third map shows the unemployment rate by state by 2012.

![](images/unemployment_US.JPG)

## Discussion
In this lab, I learned how to use Folium and pandas to create the interactive maps. 

In the lab, I get the Modifiable areal unit problem. The different size of unit can affects the results. That's why we see the second map is more "real" for the understanding of the distribution. MAUP is a common problem when we are generating a map. We always use the postal code zone as the unit. However, the zip code is designed for mailing. It has little to do with the analysis. So, the final map can be misleading for readers.

Also, I tried several parameters in the library Folium. For example, I changed the marker to Starbucks' logo in the second map. The code is below.

```
for i,row in df.iterrows():
  icon = folium.features.CustomIcon("https://www.issaquahhighlands.com/wp-content/uploads/2020/04/Starbucks-250x253.png",icon_size=(14, 14))
  folium.Marker((row.latitude,row.longitude), icon=icon).add_to(laMap)
```
