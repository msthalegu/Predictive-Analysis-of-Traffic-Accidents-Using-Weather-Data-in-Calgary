# **<center>Predictive Analysis of Traffic Accidents Using Weather Data in Calgary <center>**

<center>Luisa Alejandra Sierra Guerra (30261956)<center> <br/>
  
<center>Ali Afkhami (30271805)<center> <br/>
  
<center>Evan Losier (30022571)<center> <br/>
  
## **Introduction**
<p style='text-align:justify;'> This project is conducted by a multidisciplinary team: Ali Afkhami, a chemical engineer and data scientist with experience in both industries; Evan Losier, a computer scientist with experience in software development; and Alejandra Sierra, who holds a bachelor’s degree in marketing with experience in consumer behavior research. </p>

<p style='text-align:justify;'> Road safety is a critical issue in Calgary, where every journey reflects a narrative of connection, ambition, and at times, tragedy. In 2022 alone, the city recorded 33,317 traffic collisions, resulting in over 2,000 injuries and the tragic loss of 16 lives in Calgary (Calgary Safer Mobility Plan, 2023). These statistics underscore the urgent need for solutions to enhance user safety, mitigate human suffering, and alleviate the economic burden of accidents. For city planners and policymakers, addressing this challenge requires a multifaceted approach, integrating infrastructure improvements, evidence-based interventions, and public awareness efforts. </p>

<p style='text-align:justify;'> Calgary's extreme climate further complicates the landscape of traffic safety, with temperatures fluctuating from below -40°C in winter to over 35°C in summer. These conditions profoundly impact road dynamics and accident patterns, raising questions about how weather shapes risk across different areas of the city. This project seeks to pinpoint traffic hotspots during days with temperatures above and below 0°C to explore how weather affects accident locations. By identifying these patterns, the findings can guide targeted interventions, such as awareness campaigns and infrastructure enhancements, to create safer roads for everyone. </p>

## **Guiding Questions**

This project aims to explore traffic accident patterns in Calgary under various weather conditions and identify actionable insights. The following research questions provide a clear framework to understand specific challenges and guide targeted safety measures.

1. **What are the hotspots for traffic incidents in Calgary when temperatures are above/below 0°C in 2024?**
   This question identifies locations with the highest risk of accidents under specific temperature conditions, helping to prioritize areas for infrastructure improvements or preventive measures tailored to seasonal needs.

2. **What are the hotspots for traffic incidents in Calgary when there is snowfall or pre-existing snow in 2024?**  
   Snow conditions significantly affect road safety. This question offers insights into how road conditions impact safety, informing strategies for snow removal, road treatment, and driver preparation in winter months.

3. **How do the hotspots for traffic incidents during days below 0°C compare to those on days above 0°C?**  
   This question aims to identify accident hotspots where frequency remains largely unaffected by temperature differences. These areas, where climate plays a minimal role, warrant further investigation into other potential contributing factors, such as infrastructure design, speed limits, insufficient traffic signals, or a lack of preventive awareness campaigns. By pinpointing these locations, the government can prioritize targeted interventions to address underlying issues beyond weather-related causes.

4. **What time of day do most incidents occur in these hotspots?**  
   By analyzing the timing of accidents in high-risk locations, this question supports efforts to optimize traffic management, law enforcement, and public awareness campaigns during peak accident hours.

### **Relevance and Impact of the Study**
<p style='text-align:justify;'> Addressing these questions is crucial for enhancing road safety in Calgary. By analyzing traffic patterns influenced by weather and time of day, this project provides:</p>
<p style='text-align:justify;'>Guidance for State Interventions: The findings will serve as a foundation for governmental actions, such as targeted investigations in high-accident areas. These insights can help determine the most effective solutions, whether through infrastructure improvements or preventive campaigns, ultimately reducing both the human and economic toll of accidents.</p>
<p style='text-align:justify;'>Public Awareness and Preparedness: As publicly accessible information, the results can raise awareness among drivers and stakeholders, fostering greater preparedness and encouraging safer driving behaviors.</p>
<p style='text-align:justify;'>Ultimately, these efforts aim to enhance the quality of life for Calgary’s residents, ensuring safer and more efficient travel across the city under all weather conditions.</p>

## **Dataset**
<p style='text-align:justify;'>For this project, we will use two datasets, both provided in .csv format. These datasets are structured and tabular, with each row representing either a traffic incident or a day of weather data.</p>

1. **City of Calgary Traffic Incidents**
    This dataset, provided by the City of Calgary, contains data on traffic incidents. It includes 52,210 rows and 10 columns, but for our analysis, we will focus on a filtered subset from 2024, consisting of at least 7,493 rows (representing incidents from 2024 only) and a minimum of 3 columns: START_DT, Longitude, and Latitude. We have permission to use this data under the following license [Open Calgary Terms of Use](https://data.calgary.ca/stories/s/Open-Calgary-Terms-of-Use/u45n-7awa). The dataset can be accessed at [City of Calgary Traffic Incidents](https://data.calgary.ca/Transportation-Transit/Traffic-Incidents/35ra-9556/about_data).

2. **Historical Climate Data for Calgary (2024)**
    The weather dataset is sourced from Environment Canada and includes 366 rows and 31 columns. For our analysis, we will primarily use all 366 rows, focusing on a minimum of 4 columns: Date/Time, Mean Temperature, Total Snow (cm), and Snow on Ground (cm). We have permission to use this data under the following license: [Environment Canada Terms of Use](https://climate.weather.gc.ca/prods_servs/attachment1_e.html). The dataset can be accessed at [Historical Climate Data for Calgary](https://climate.weather.gc.ca/climate_data/daily_data_e.html?StationID=50430).

3. **Open Street Map (2025)**:
    The map used for all geographic visualizations was sourced from [Open Street Map](https://www.openstreetmap.org). Geopandas and Plotly automatically sourced the data from Open Street Map when constructing the visualizations.

## **Analysis and Visualizations**
Followings are the result of our analysis:

### Time-Based Visualizations (Hour)
#### Visualize incidents by hour with peaks highlighted.

![image](https://github.com/user-attachments/assets/c312e0b2-2fee-49f7-8229-a3b803dce8d0)

Figure 1, shows the total number accidents occured in 2024 on every hour of the day. As we can see the number of accidents see a dramatic rise in the number of accidents during the morning and afternoon rush hours when people go and come back from work. This is further backed by [Calgary city website](https://www.calgary.com/blog/driving-calgary-ab/) in which according to it "traffic congestion peaks between 7:00–9:00 a.m. and 4:00–6:00 p.m.".

#### Visualize incidents During Rush Hour vs. Non-Rush Hour
|    | Hour          |   Total |
|---:|:--------------|--------:|
|  0 | Not rush hour |    4314 |
|  1 | Rush Hour     |    3179 |

![image](https://github.com/user-attachments/assets/1c0f0330-fbca-44f7-ab89-4c020cd572dc)

On figure 2, we further focus on number of accidents during the rush our. As mentioned before, according to the city of Calgary website, 6 hours of the day is considered the rush hour and acording to this pie chart, **42%** of the incidents during the day, occur in the **6h rush hours**.

### Time-Based Visualizations (Day)
#### Visualize incidents by day.

|    | Day       |   Daily_counts |
|---:|:----------|---------------:|
|  0 | Monday    |           1050 |
|  1 | Tuesday   |           1187 |
|  2 | Wednesday |           1238 |
|  3 | Thursday  |           1211 |
|  4 | Friday    |           1214 |
|  5 | Saturday  |            898 |
|  6 | Sunday    |            695 |

![percentage of incidents](https://github.com/user-attachments/assets/6da53001-70b8-4428-b021-bfaa0a54d266)

Figure 3, focuses on the number of daily accidents during the week. According to the pie chart, during the workdays, approximately 14 - 16% of the accidents occure, however, on the weekends, these numbers drop to 9.3 and 12% for Sundays and Saturdays, respectively. This could be due to the fact that more people tend to stay home during the weekend days.


### Time-Based Visualizations (Month)
#### Visualize incidents by month.

![image](https://github.com/user-attachments/assets/5fa6d2d4-ea78-45b9-a902-8560907b53dc)

According to figure 4,  November (876 incidents), followed by January (767) and October (733) have the highest number of accidents. Month of April with 448 incidents shows the lowest number driving accidents, suggesting that traffic incidents decrease during early spring.

##### Visualize incidents by season.

![image](https://github.com/user-attachments/assets/7f70306d-b050-4dbb-aabc-9ab1b90b060d)

Figure 5, depict the number of accidents occure every season. According to figure 5, **fall season** has the highest number of trafic incidents (29%) which could be due to changing weather conditions such as rain, fog or early snow. **Winter** is the second season with the highest number of incidents, which could be due to icy roads and lower road visibility.

###  Time-Based Visualizations (Others)
#### Visualization of Incidents by Quadrant.

|    | QUADRANT   |   Total_count |
|---:|:-----------|--------------:|
|  0 | NE         |          2229 |
|  1 | NW         |          1600 |
|  2 | SE         |          2294 |
|  3 | SW         |          1370 |

![image](https://github.com/user-attachments/assets/24cab622-3085-4980-bef7-6608ee72510b)

Figure 6, compares the number of accidents based on the 4 quadrant of the city. According to figure 6, NE and NW part of the city have the highest number of accidents. This could be due to the **quality of the roads** and **density of population** in these two areas.


## Advanced Analysis with Weather Data

![day vs temp](https://github.com/user-attachments/assets/2268182f-774b-4dc6-846f-69c78af40438)


According to the pie charts above which compare the number of incidents by temperature condition of above or below zero and the number of days in 2024 when the temperature was above or below zero, even though, the temperature in 42.3% days of the year 2024 was below zero, only 32.3% of the incidents accoured in this temperature condition. This could mean that the drivers are **more careful** when the weather condition is sub-zero.

### Number of accidents on days with rainfall above a certain threshold.

|    | Snowfall Category   |   Days |   Percentage % |   Incidents |   Incidents Per Day |
|---:|:--------------------|-------:|---------------:|------------:|--------------------:|
|  0 | Heavy Snow          |      4 |           0.01 |         142 |               35.5  |
|  1 | Moderate Snow       |     15 |           0.04 |         443 |               29.53 |
|  2 | Light Snow          |     30 |           0.08 |         744 |               24.8  |
|  3 | No Snow             |    317 |           0.87 |        6164 |               19.44 |

### Correlation Analysis
Analyze correlations between:
- Temperature and incidents.
- Rainfall and incidents.
- Snowfall and incidents.

#### Correlation between the temperature and the number of accidents

|            |   sum_counts |   mean_temp |
|:-----------|-------------:|------------:|
| sum_counts |     1        |   -0.260096 |
| mean_temp  |    -0.260096 |    1        |

#### Effect of weather conditions on the number of incidents

|                   |   monthly_incidents |   monthly_snow_cm |   monthly_rain_mm |
|:------------------|--------------------:|------------------:|------------------:|
| monthly_incidents |            1        |           0.28204 |         -0.336212 |
| monthly_snow_cm   |            0.28204  |           1       |         -0.60573  |
| monthly_rain_mm   |           -0.336212 |          -0.60573 |          1        |

![image](https://github.com/user-attachments/assets/87631a5b-0d9f-46d7-9033-bec2286f52c8)

According to figure 9 and the correlation table, there is a positive but weak correlation between the number of accidents and the amount of snow on the ground, indicating that when the snowfall is significant, the probability of accidents increases.

### Geographic Analysis

![image](https://github.com/user-attachments/assets/124812e4-9bf1-461f-aadf-4eb95e35fc4f)

The above map shows all incident locations in the dataset. The darker each point is, the more incidents occurred at that specific location. From the distribution of the points, we see that there are a high number of incidents in the Downtown Core, on Deerfoot Trail, and on Glenmore Trail. The remaining points were all distributed fairly randomly around the city, with more incidents occurring on major highways and areas closer to the center of the city.

# Conclusion

**From our analysis of City of Calgary traffic incidents, we observed the following:**

We observed that the hotspots for traffic incidents in Calgary were primarily grouped around three key areas/roadways. The main hot spots by far were: The Downtown Core, Deerfoot Trail, and Glenmore Trail. These locations were all hot spots.  

In terms of the impact of weather on traffic incidents, we observed that counter to what intuition might suggest, there were fewer incidents on days with significant rainfall. We could explain this by suggesting that drivers are more careful when their vision is obstructed by the rain. However, on days with significant snowfall, incident rates did increase by a notable amount. This is possibly because snow will affect the road driving conditions much more than rain.  

For the effect of temperature on incidents, there was a weak correlation. As temperatures decrease, incidents increased slightly.  

Finally, the times of the day when most incidents occurred were the expected rush hour times of: 8am, 3pm, 4pm, and 5pm. This matches that an increased presence of traffic results in more incidents.

## References

The City of Calgary (2023) Calgary Safer Mobility Plan – Annual Briefing 2023.  
Available at: https://www.google.com/search?q=Calgary+Safer+Mobility+Plan+%E2%80%93+Annual+Briefing+2023&oq=Calgary+Safer+Mobility+Plan+%E2%80%93+Annual+Briefing+2023&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIKCAEQABiABBiiBNIBBzU1NWowajeoAgiwAgE&sourceid=chrome&ie=UTF-8#:~:text=Safer%20Mobility%20Plan%20Annual%20Briefing%202023%20%2D%20The%20City%20of%20Calgary (Accessed: 17 January 2025).

Government of Canada (n.d.) Historical Weather and Climate Data.  
Available at: https://climate.weather.gc.ca/climate_data/daily_data_e.html?StationID=50430 (Accessed: 17 January 2025).

Historical Weather and Climate Data.  
Available at: https://climate.weather.gc.ca/climate_data/daily_data_e.html?StationID=50430 (Accessed: 17 January 2025).  

Khandekar, M.L. (2002) Trends and Changes in Extreme Weather Events: An assessment with focus on Alberta and Canadian Prairies. Available at: Trends and Changes in Extreme Weather Events: (Accessed: 17 January 2025).

Open Calgary (2025) Traffic Incidents.  
Available at: https://data.calgary.ca/Transportation-Transit/Traffic-Incidents/35ra-9556/about_data (Accessed: 17 January 2025).

OpenStreetMap (2025) Open Street Map.  
Available at: https://www.openstreetmap.org (Accessed: 17 January 2025).

Syed Tauhid Ullah Shah (2025) Data601W25
Available at: https://github.com/SyedTauhidUllahShah/DATA601W25 (Accessed: 11 February 2025)

Traffic Incidents | Open Calgary.  
Available at: https://data.calgary.ca/Transportation-Transit/Traffic-Incidents/35ra-9556/about_data (Accessed: 17 January 2025).
