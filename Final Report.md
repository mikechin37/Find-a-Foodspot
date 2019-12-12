Find-a-Foodspot

Author: Michael Chin


1. Introduction

In this project we will try to find an optimal location for a restaurant. Specifically, this report will be targeted to stakeholders interested in opening an Chinese restaurant in Cambridge, Massachussetts. Cambridge is a hot city close to Cambridge that is home to many college students attending Harvard and MIT, and young professionals working largely in the biotech sector. Therefore, Cambridge is a great place to open up a new restaurant to a young demographic that eats out frequently.
Since there are lots of restaurants in Cambridge we will try to detect locations that are not already crowded with restaurants. We are also particularly interested in areas with no Chinese restaurants in vicinity. We would also prefer locations as close to city center as possible, assuming that first two conditions are met.
We will use our data science powers to generate a few most promising neighborhoods based on this criteria. Advantages of each area will then be clearly expressed so that best possible final location can be chosen by stakeholders.

2. Data

Based on definition of our problem, factors that will influence our decision are:
•	number of existing restaurants in the neighborhood (any type of restaurant)
•	number of and distance to Chinese restaurants in the neighborhood, if any
•	distance of neighborhood from city center
We decided to use regularly spaced grid of locations, centered around city center, to define our neighborhoods.
Following data sources will be needed to extract/generate the required information:
•	centers of candidate areas will be generated algorithmically and approximate addresses of centers of those areas will be obtained using Google Maps API reverse geocoding
•	number of restaurants and their type and location in every neighborhood will be obtained using Foursquare API
•	coordinate of Cambridge center will be obtained using Google Maps API geocoding
 

3. Methodology

In this project we will direct our efforts on detecting areas of Cambridge that have low restaurant density, particularly those with low number of Chinese restaurants. We will limit our analysis to area ~5km around the Cambridge city center.
In first step we have collected the required data: location and type (category) of every restaurant within 6km from Cambridge center (Cambridge). We have also identified Chinese restaurants (according to Foursquare categorization).
Second step in our analysis will be calculation and exploration of 'restaurant density' across different areas of Cambridge - we will use heatmaps to identify a few promising areas close to center with low number of restaurants in general (and no Chinese restaurants in vicinity) and focus our attention on those areas.
In third and final step we will focus on most promising areas and within those create clusters of locations that meet some basic requirements established in discussion with stakeholders: we will take into consideration locations with no more than two restaurants in radius of 250 meters, and we want locations without Chinese restaurants in radius of 400 meters. We will present map of all such locations but also create clusters (using k-means clustering) of those locations to identify general zones / neighborhoods / addresses which should be a starting point for final 'street level' exploration and search for optimal venue location by stakeholders.

4. Results

Our analysis shows that although there is a good number of restaurants in Cambridge (~500 in our initial area of interest which was 12x12km around Cambridge), there are pockets of low restaurant density fairly close to city center. Highest concentration of restaurants was detected south from Cambridge, so we focused our attention to areas north, northeast and northwest and central to the city center. Cambridge offers a combination of popularity among tourists, closeness to city center, strong socio-economic dynamics and a number of pockets of low restaurant density.
After directing our attention to this more narrow area of interest (covering approx. 5x5km north, northeast, and northwest from Cambridge) we first created a dense grid of location candidates (spaced 100m appart); those locations were then filtered so that those with more than two restaurants in radius of 250m and those with an Chinese restaurant closer than 400m were removed.
Those location candidates were then clustered to create zones of interest which contain greatest number of location candidates. Addresses of centers of those zones were also generated using reverse geocoding to be used as markers/starting points for more detailed local analysis based on other factors.
Result of all this is 8 zones containing largest number of potential new restaurant locations based on number of and distance to existing venues - both restaurants in general and Chinese restaurants particularly. This, of course, does not imply that those zones are actually optimal locations for a new restaurant! Purpose of this analysis was to only provide info on areas close to Cambridge center but not crowded with existing restaurants (particularly Chinese) - it is entirely possible that there is a very good reason for small number of restaurants in any of those areas, reasons which would make them unsuitable for a new restaurant regardless of lack of competition in the area. Recommended zones should therefore be considered only as a starting point for more detailed analysis which could eventually result in location which has not only no nearby competition but also other factors taken into account and all other relevant conditions met.

5. Discussion

The purpose of this project was to identify Cambridge areas close to the city center with low number of restaurants (particularly Chinese restaurants) in order to aid stakeholders in narrowing down the search for optimal location for a new Chinese restaurant. By calculating restaurant density distribution from Foursquare data we have first identified general zones that justify further analysis, and then generated extensive collection of locations which satisfy some basic requirements regarding existing nearby restaurants. Clustering of those locations was then performed in order to create major zones of interest (containing greatest number of potential locations) and addresses of those zone centers were created to be used as starting points for final exploration by stakeholders.
Final decision on optimal restaurant location will be made by stakeholders based on specific characteristics of neighborhoods and locations in every recommended zone, taking into consideration additional factors like attractiveness of each location (proximity to park or water), levels of noise / proximity to major roads, real estate availability, prices, social and economic dynamics of every neighborhood etc.

