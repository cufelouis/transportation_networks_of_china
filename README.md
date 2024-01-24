# Transportation Networks of China
This data repository hosts datasets covering China's road and rail transportation networks. These datasets are compiled in *The Distributional Impacts of Transportation Networks in China* by Lin Ma and Yang Tang, published in the *Journal of International Economics*. To use the data, please cite:

"Lin Ma and Yang Tang. *The Distributional Impacts of Transportation Networks in China.* Journal of International Economics (2024): 103873."

This dataset contains three components: 
  1) prefecture-to-prefecture commuting time,
  2) year of construction and design codes for each road and railroad and
  3) pixel-level design speed and travel time data.
   
The authors are still in the process of cleaning up parts (2) and (3), and you can access the raw data via the [Dropbox Link](https://www.dropbox.com/scl/fo/6cey5kdtqsfqyatn6xa43/h?rlkey=ycklu6jgstjlkiu2fa740iv21&dl=0) 

## Prefecture-to-Prefecture Travel Time

This data set records the prefecture-to-prefecture travel time in units of hours for three modes of transportation: road, railroad (freight), and railroad (passenger). The current version covers the years 1994 to 2017 and contains 279 prefectures. 

The travel time is computed using the Fast Marching algorithm based on the pixel-level design speed. Ma and Tang (2024) provide more details on how to infer the pixel-level design speed and prefecture-to-prefecture travel time. 

The dataset contains the following files.
1. `cityinfo.csv` is the file that contains the basic information about the 279 prefectures. [variable definition](pref_pair/cityinfo.md).
2. `pref_pair/time_cost_prefecture_pair_rail_good.csv` is the travel time for **freight** transportation on the **rail network**.
3. `pref_pair/time_cost_prefecture_pair_rail_pass.csv` is the travel time for **passenger** transportation on the **rail network**.
4. `pref_pair/time_cost_prefecture_pair_road.csv` is the travel time for both **freight** and **passenger** transportation on the **road network**.

The travel time data files share the same structure. Each file contains 38781 rows, which is the lower triangle of the $279\times279$ symmetric distance matrix without the diagonal elements. The variables in these files are:  
1. The first two columns, `origin` and `destination,` are the four-digit admin codes of the origin and destination prefectures.
2. `year_yyyy`: the travel time between the two prefectures in the year `yyyy` in hours.

## Year of Construction and Applicable Design Code

This data set records the years of construction and the applicable design codes for all segments of roads and railroads in the dataset. In addition, the dataset also contains the coordinates of the roads and railroads.

## Pixel-Level Design Speed and Travel Time

This data set contains the design speed and the travel time to trespass each pixel in the $12669\times 8829$ raster map of China by year and transportation mode. The prefecture-to-prefecture travel time is computed based on this data set.
