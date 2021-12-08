### Title : Does the officer's race have an effect on racial disparities in police stops ? 

### Abstract :
  As the paper looked at racial disparities in police stops across the United States, we wanted to keep exploring the possible racial disparities in policing. In particular, we would like to investigate whether the race of the officer has an effect on racial disparities in police stops. First, we will assess potential bias in stop decisions by applying the 'veil of darkness' test. We will thus compare the difference before and after sunset for black and white officers and see if there s a discrimination to a specific race.  Next, for each officer race we will look at the racial makeup of the drivers they stopped and compare it to the racial makeup of the county where the stops were made. If there are no disparities in policing the proportion of white drivers stopped in a county by a black officer should match the proportion of whites living in that county for example. Finally, we look at the rate at which an officer from a given race searches drivers with the same race as him versus drivers of a different race. However as possible disparities in search rates are not necessarily the product of discrimation as highlighted by the paper, we will also investigate the potential bias in the post-stop decision to search drivers for contraband. This will be done using outcome analysis, particularly by using the hit rates as defined in the paper. The data that we will use for our different analyses will be the datasets on policing made available by the Stanford Open Policing Project as well as the US census data.

### Research questions : 
1) Does the veil of darkness test for specific officer race shows a racial disparity in the race of the driver stopped ?
2) Does the potential biais in search decision vary accross the different officer races ?
3) Is the difference in number of stops for each race due to a police bias or a different distribution of that race in the population ?


### Proposed datasets : 
1) Stanford Open Policing Project (paper based dataset) : https://openpolicing.stanford.edu/data/ 
2) US census data : https://www.census.gov/data.html

### Methods :
First we will get all the necessary datasets and do the data wrangling on them. We will use data from as many cities / states as there are on the Stanford Open Policing Project, considering they have the fields we are interested in (such as the officer race for example).

Then we would get a dataset from the US census data containing the race distributions in the cities / states where we have policing data on (from the Stanford Open Policing Project). This can be done using queries with the census data API.

To answer question 1), we will separate the data by the race of the officer that made the stop, and see whether the bias in stop decisions is the same across all officers race of if some officers have a more biased way of stopping driver by race. We will use a library to find sunset times across the US and do the Veil-of-Darkness test.

To answer question 2), we will first compare the rate at which officers of a given race search drivers of the same race as them and drivers of a different race. But since a difference in search rates doesn't necessarily mean that there is a bias, we will conduct an outcome test. For white, black and Hispanic officers the outcome test consists in comparing the hit rates on drivers of the same race as them with the hit rate on driver of a different race, where the hit rate is defined as the number of searches that resulted in contraband being found divided by the number of searches. To be able to compare the hit rates on a by county basis, we will keep only counties where an officer made searches on drivers of the same race as him as well as on a different race. This will allow us to produce a figure similar to Figure 3a) of the paper this extension is based on, as it is a good way to visualize potential bias. Moreover we will conduct student t-test to look if the potential difference in hit rates on drivers of the same race as the officer versus drivers of a different race is statistically significant.

To answer question 3), we will look at the racial distribution of the population in a given state and compare it to the distribution of stops for that race. For example, if black represent 30% of the population in a state, do they represent 30% of the drivers stopped in that state ? Any difference would not inherently mean that the cops are racist but would should that there are racial disparities in policing. Again, statistical tests would need to be performed to see if the difference (if there is one) is statistically different. We need to look at stops performed durng the day only since it's when the race of the driver is visible to the officer.

### Proposed timeline :

As we will have around 3 weeks to work on this extension of paper, by the end of the first week we must have collected all the necessary datasets and performed data wrangling on them. Each team member should have ideally started working on his assigned question by the end of the first week too. The second week will be used to finish answering the questions. The third week will be used to review the results, produce the data story and the video. 

### Organization within the team
James: Veil-of-Darkness test, write report

Nicolas: Assessing bias in search decisions (search rate & outcome test), write report

Dahn: Census Dataset and tests, write report
