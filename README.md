INTRODUCTION
 In the recently conducted elections the Independent Electoral Commission faced multiple legal challenges concerning the integrity and accuracy of the election. The aim of this project is to identify outliers in the recent election data. I will be using geospatial technique for this analysis. Geospatial analysis gathers, manipulates and displays geographic information system (GIS) data.  By leveraging geospatial analysis, we can uncover polling units where the voting patterns diverge significantly from neighboring areas. This will help ensure transparency and integrity in the election data. 
OBSERVATION
DATA PREPARATION/ CLEANING: 
I downloaded the election data for Akwa Ibom state. The data consists of the votes of four main political parties which are the NNDP, LP, PDP and APC. In this data there were no duplicates found. There were no blank spaces. There were outliers found in the data which showed data irregularity. 
But before handling the outliers the instruction was to find the longitude and latitude of each polling unit. I imported the data to google sheets then used the geocoding by awesome table to find the latitude and longitude of each polling unit. There were some polling units with missing coordinates so I had to clean the data by removing those polling units to ensure there is data consistency. There were 343 rows and 21 columns in the data.

NEIGHBOUR IDENTIFICATION: 
In order to identify neighbouring polling units based on geographical proximity. I used the radius 1km because any polling units within that radius are capable of rigging the election which explains the outliers. I imported the data into google colab to get the neighbouring polling units. I installed geopy in python to be able to carry out this task.

Here we can see that APC and PDP have a correlation coefficient of 0.055, which suggests a weak positive correlation between their vote. On the other hand, APC and NNPP appear to have a weak negative correlation, with a coefficient of -0.11.

OUTLIER SCORE CALCULATION: 
In order to get the outlier score i ran the code in google colab to get the outlier score for each polling unit. Outlier is a single data point that goes far outside the average value. So, I used the average vote for each party to find the outlier score.

There is a positive correlation between the average NNPP votes and the NNPP outlier score. This means that as NNPP average votes increases, the outlier scores also increases. 

There is a positive correlation between PDP votes and PDP’s outlier scores. As the sum of PDP average votes increases, the sum of PDP outlier scores also tends to increase. This suggests that higher average PDP votes are associated with higher PDP outlier scores. 
SORTING: 
I imported the data back to google sheets to sort the outlier scores. I calculated the average outlier score of each of the parties and sorted it based on party outliers in descending order to get the most significant outliers.
Here I highlighted the top 3 outliers and their closest polling units. I used conditional formatting to highlight them. The deeper the red color the higher the outlier score. 
It can be seen that Independence High sch, Ukana Ikot Ntuen has the highest average outlier score of 84.75 which explains the fact that there could be irregularities in the vote count for this particular polling unit. 
Village Hall, Ikot Ukpong has the second average outlier score of 56.18. Even though it’s not as high as that of Independence High school, there are still irregularities found in the voting patterns and vote counts for this polling unit.
Pry sch, Ikot Ekpe has the third average outlier score of 52. 25. The outlier score may not be as high as the first two but it still has some irregularities in their vote count or other usual factors.
CONCLUSION 
In conclusion, our geospatial analysis of the recent election data for Akwa Ibom state has successfully identified polling units with voting irregularities. By assigning geographic coordinates to each polling unit and using a 1km radius to define neighboring units, we assessed the correlation between votes of different political parties and identified significant outliers.
Key findings include:
Three polling units with notable outlier scores: Independence High School, Ukana Ikot Ntuen; Village Hall, Ikot Ukpong; and Pry School, Ikot Ekpe.
Weak positive and negative correlations between votes of different parties.
Positive correlation between average votes and outlier scores for NNPP and PDP, indicating possible irregularities.
