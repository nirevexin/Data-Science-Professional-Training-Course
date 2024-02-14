**During the implementation of the project, the following was done**:

## Preprocessing stage
- Primary information was obtained:

    - total_images — number of photos of the apartment in the ad (int64)
    - last_price — price at the time of removal from publication (float64)
    - total_area — apartment area in square meters (float64)
    - first_day_exposition — publication date (object)
    - rooms — number of rooms (int64)
    - ceiling_height — ceiling height (m) (float64)
    - floors_total - total floors in the house (float64)
    - living_area - living area in square meters (m²)(float64)
    - floor - floor (int64)
    - is_apartment - apartments (boolean type) (object)
    - studio - studio apartment (boolean type) (bool)
    - open_plan - open plan (boolean type) (bool)
    - kitchen_area - kitchen area in square meters (m²) (float64)
    - balcony — number of balconies (float64)
    - locality_name — name of the locality (object)
    - airports_nearest — distance to the nearest airport in meters (m) (float64)>
    - cityCenters_nearest — distance to the city center (m) (float64)
    - parks_nearest — distance to the nearest park (m) (float64)
    - parks_around3000 — number of parks within a 3 km radius (float64)
    - ponds_around3000 — number of ponds within a 3 km radius (float64)
    - ponds_nearest — distance to the nearest body of water (m)(float64)
    - days_exposition — how many days the ad was posted (from publication to removal) (float64)

- We rendered the first 20 rows to get an idea of what the set looks like.
- We visualized histograms for each column to see the distribution of values.

- We have determined which data types need to be changed.

- We ensured that there were no obvious duplicates in the data.

- We visualized the gaps in the data:

      - total_images: 0
      - last_price: 0
      - total_area: 0
      - first_day_exposition: 0
      - rooms: 0
      - ceiling_height: 9195
      - floors_total: 86
      - living_area: 1903
      - floor: 0
      - is_apartment: 20924
      - studio: 0
      - open_plan: 0
      - kitchen_area: 2278
      - balcony: 11519
      - locality_name: 49
      - airports_nearest: 5542
      - cityCenters_nearest: 5519
      - parks_around3000: 5518
      - parks_nearest: 15620
      - ponds_around3000: 5518
      - ponds_nearest: 14589
      - days_exposition: 3181

- We analyzed the gaps using graphs, histograms and information display techniques and filled them accordingly.

- Changed data types to the correct ones.

- We also analyzed the anomalies and eliminated them.

- New columns were created:

      - price per square meter: data['price_per_sqm']
      - publication weekday : data['exposition_weekday']
      - publication month : data['exposition_month']
      - year of publication : data['exposition_year']
      - nearest city center in km: data['cityCenters_nearest_KM']
  
## Analysis stage
Using graphs and methods to display information, we have established that:

The average sales rate has been increasing over the years.

Slow sales are those that take at least 420 days (beyond the Q3+1.5*IQR limit), and fast sales are those that take less than 3 days.

The share of abnormally slow sales from the total is 10.15%.

The share of abnormally fast sales from the total is 0.01%

Most values are located to the right of the median. To determine the usual sales time, let's take the average value of 169 days.

We have created a correlation table and concluded that the factors that most influence the price of housing are the following, classified from most influential to least influential:

1 Total area
2 Living Area
3 Number of Rooms
4 Kitchen area
We also built graphs to trace the relationship between the price of an apartment and other linearly independent parameters:

It can be seen that apartments located on the ground floor are cheaper.

Apartments on the middle floors are usually the most expensive.

Prices for apartments on the top floors are between the prices for the first and middle floors.

Apparently, more expensive apartments are published on Thursdays. From Thursday to Saturday, prices drop sharply. The cheapest apartments are published on Saturday. Prices then rise progressively until Thursday.

Regarding the month, the correlation, as with days, is insignificant, but we can say that apartments published in December are slightly more expensive.

From 2014 to 2016, prices plummeted from about 9 million to just over five and a half million. After 2016, prices continue to fall, but not very significantly. After 2018, they begin to grow again at the same rhythm without significant volatility. In the periods from 2016 to 2019, prices remain in the range of 5.5-6 million.

We have created a table and graph with the average price per square meter for the ten cities where the most apartments are published and we found out that:

The highest price per square meter of housing is in St. Petersburg.
The lowest price is in Vyborg.
We calculated the average price per kilometer and the relationship between the price of housing and its distance from the city center:

The correlation between the price of real estate and its distance from the city center gave a negative value: -0.40. This means that as the price of real estate increases, the distance to the city center decreases, because the correlation value is a tangent with an angle of 40 degrees, which is reflected in the graph.

The graph shows the correlation. However, it coincides that extremely expensive apartments (possibly elite) are located within a radius of 7.5 km from the center.

The average price for KM is 70.96 million rubles.

Since price and distance are indirectly proportional, in order to get the average price at a given distance from the center, we need to divide 70.96 by the distance.
