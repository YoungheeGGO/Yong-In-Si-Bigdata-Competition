# [COMPAS] YoungIn-Si Bigdata contest.

- Present ideas for youth entrepreneurship or business settlement
- Period : 2021.01.07 ~ 2021.01.28
- We failed the award.

## Data analysis process

**1. Data preprocessing**

- Data Collection</br>
    -  We used not only given data by the organizer,COMPAS, but also other data.</br>
    - We collected data impacting neighbor shops about traffic, education, medical facility,  cultural facility, etc. (Usually public data)</br>
- Data Concatenation </br>
    -  We concatenated the given data with external data.
    -  We implemented the code with API. Because they included nondisclosure data.
    -  One data frame is produced.
-  Grid Integration
    - The data was mixed with both 250x250 grid and 100x100 grid. They were integrated into a 500x500 grid. This process was carried out using the QGIS tool.

- Missing Values
    - In COMPAS data, The administrative district column had a lot of missing values.
    - So, we crawled Google Map and supplemented the missing data.


**2. EDA**
- We visualized with data with Tableau and Python


**3. Analysis**
- Hot-spot analysis with Getis test statistic.
- Logistic Regression
- EM algorithms for Gaussian Mixture Model
  
  
## What I felt.
> I wanted to use my statistical knowledge in the real-world dataset. That means I wanted to focus more on the modeling process, the next step of exploratory data analysis. First, I found a lot of papers about spatial analysis and Getis analysis(LISA,Moran) used in the hot-spot analysis. But I didn't know that. So I study the concept myself using google and youtube. 'Spatial Autocorrelation' was difficult for me to understand and I summarized the 'Autocorrelation'. After that, I knew that It's no different with test statistics. Although We failed the award, I learned a lot of things about data analysis than in other competitions I had won the award. I learned not only spatial analysis but also clustering. I had known that the clustering method has only kmeans and knn algorithms but there was another algorithm called as EM algorithm. I applied three algorithms to the same data, EM algorithm based on probability assumption had the best result.  I thought the reason why. Kmeans and KNN put in the high dimension and considered the distance of data. But EM algorithm is based on likelihood proven as a meticulous statistical method. So, This method had high homogeneity within the group and high heterogeneity intergroup. As a result, EM algorithm proposed by me was used in the final analysis.:smile:


## Why we failed the award?
    - Time limitation
> Our team member was so busy after joining this competition. They were participants in an internship program and another was a graduate student. I spent a lot of time doing all of the work in the data analysis from finding prior research to designing the analysis pipeline. I'm little bit sad that we couln't win the award. But I thought about why we failed the award. And I thought there are logical errors in the analysis process. Especially, We didn't enough explanation why conduct both of logistic regression and EM method. It felt like "I know this difficult method!"  not method for adequate data analysis. I realized that appropriate analysis techniques should be used according to data background knowledge. I shouldn't use the technique unconditionally because it's a difficult method.

    - Lack of data
> We didn't collect the data that we want to.  It was an analysis targeting youth who plan to open a business and We knew the important thing for a youth's startup is capital. But We couldn't find the data about rental fees or land costs in YoungIn-si. The organizer did not offer that data and not exist data on a website about real estate. We should have considered both time and space data.(ex. Change startup trend according to time) But the data is only from 2017 to 2019, in that time there was no changing startup trend and the population at YoungIn-si was not changed. So only we could do analysis is spatial analysis.



