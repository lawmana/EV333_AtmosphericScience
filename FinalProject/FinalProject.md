# Sample Python code for final projects

This document provides some example code for the following: 
1.	How to subset a globally gridded dataset to a smaller region
2.	How to calculate a regional time series
3.	How to change the central longitude on a map
4.	How to change the latitude and longitude axes extents for a regional map

## 1. How to subset a globally gridded dataset to a smaller region
**Example 1: Niño 3.4 region**

The example below will subset a globally gridded dataset called ds to the Niño 3.4 region in the central equatorial Pacific [5°S to 5°N and 170°W to 120°W]. 

All the ERA5 data we used in class are on a [0, 360] °E grid. For locations in the western hemisphere, a longitude of 170°W is equivalent to -170°E. To convert to a [0, 360] grid add 360 to the longitude values:

-170+360 = 190

-120+360 = 240

*Note that the longitude conversion only needs to be done for sites in the western hemisphere.*

```
# select region of interest (set equal to a variable called ROI)
# the code below subsets the data to the Niño 3.4 region 
ROI = ds.where((ds.lon >= 190) &
               (ds.lon <= 240) &
               (ds.lat >= -5) &
               (ds.lat <= 5), drop = True)
```

**Example 2: Gulf of Mexico and Caribbean Sea**

To modify the code for other regions, update the latitude and longitude values. Below is another example to subset a dataset to the Gulf of Mexico and Caribbean Sea [5° to 35°N, 65 to 100°W] as shown in Figure 1.
```
# select region of interest (set equal to a variable called ROI)
# the code below subsets the data to the Gulf of Mexico and Caribbean Sea
ROI = ds.where((ds.lon >= -100+360) &
               (ds.lon <= -65+360) &
               (ds.lat >= 5) &
               (ds.lat <= 35), drop = True)
```
<img width="323" height="338" alt="image" src="https://github.com/user-attachments/assets/9dcb5b4e-fabf-42bc-90bb-60acbdd0b5a1" />

**Figure 1.** Mean sea surface temperature subset to the Gulf of Mexico and Caribbean Sea. The central longitude for the map is 82.5°W.

## 2. How to calculate a regional time series

We can take a mean over latitude and longitude to calculate a time series averaged over a region. This is a great way to visualize data because it will allow you to look at an atmospheric variable over time.

```
# calculate weights. For a rectangular grid the cosine of the latitude is proportional to the grid cell area. 
weights = np.cos(np.deg2rad(ds.lat))

# calculate a weighted mean by first applying the weights to the dataset
ds_weighted = ds.weighted(weights)

# then calculate a mean over the latitude and longitude dimensions
# this will yield a time series.
weighted_mean = ds_weighted.mean(("lon", "lat"))

# display output
weighted_mean
```
The `weighted_mean` variable can be plotted. 

## 3. How to change the central longitude of a map

Most maps we generated in class were centered on 180° in the Pacific. To change the central point of the map, update the central_longitude parameter when defining the map projection. Some examples are below:
```
# map projection (Pacific centered map)
proj = ccrs.PlateCarree(central_longitude = 180)

# map projection (Atlantic centered map)
proj = ccrs.PlateCarree(central_longitude = 0)

# map projection (map centered on 82.5°W as shown in Figure 1)
proj = ccrs.PlateCarree(central_longitude = -82.5 + 360)

# map projection (map centered on 45°E)
proj = ccrs.PlateCarree(central_longitude = 45)
```

## 4. How to change the axis extent for a regional map

If you’d like to plot a regional instead of global map, you can update the axes extent using the `ax.set_extent()` method. This should be done after you plot the data but before you save the figure. 

In Figure 1 above the axes were set to [5° to 35°N, 65 to 100°W] using the following line of code: 
```
ax.set_extent([-100+360, -65+360, 5, 35], crs=ccrs.PlateCarree())
```

A more generic example is shown below where you can update longitude1, longitude2, latitude1, and longitude2 to the bopunds you'd like for your region: 
```
ax.set_extent([longitude1, longitude2, latitude1, latitude2], crs=ccrs.PlateCarree())
```

