# [COMPAS] YoungIn-Si Bigdata contest.

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
> I wanted to use my statistical knowledge in the real-world dataset. That means I wanted to focus more on the modeling process, the next step of exploratory data analysis. First, I found a lot of papers about spatial analysis and Getis analysis(LISA,Moran) used in the hot-spot analysis. But I didn't know that. So I study the concept myself using google and youtube. 'Spatial Autocorrelation' was difficult for me to understand and I summarized the 'Autocorrelation'. After that, I knew that It's no different with test statistics. Although We failed the award, I learned a lot of things about data analysis than in other competitions I had won the award. I learned not only spatial analysis but also clustering. I had known that the clustering method has only kmeans and knn algorithms but there was another algorithm called as EM algorithm. I applied three algorithms to the same data, EM algorithm based on probability assumption had the best result.  I thought the reason why. Kmeans and KNN put in the high dimension and considered the distance of data. But EM algorithm is based on likelihood proven as a meticulous statistical method. So, This method had high homogeneity within the group and high heterogeneity intergroup. As a result, EM algorithm proposed by me was used in the final analysis. I felt the power of statistics.


## Why we failed the award?
    - Time limitation
> 비록 예선탈락했지만 같이 공모전에 나간 팀원들이 다들 공모전 출전 이후로 갑자기 바빠져서 이 공모전에 시간투자를 제대로 하지 못했다. 대학원생 2명, 인턴1명으로 내가 막내였고 하는 것도 별로 없는 학부생이었기 때문에 열심히 했다. 분석파트를 거의 다 맡아서 진행했다. 분석 파이프라인을 짜는 것 부터 선행연구 찾기 등 많은 일을 했지만 역시 공모전은 시간투자를 많이 한 만큼 수상확률이 높아지는 것 같다. 수상을 하지 못한건 조금 아쉬웠다. 최종 제출파일을 제출하면서 나름 잘 했다고 생각했지만 다시 보니 매우 부족한 부분이 많았다. 비공개 데이터를 활용한 대시보드가 함께 제출되기도 했고, 분석과정에서 논리적인 오류도 많았다. 특히 hot-spot 분석과 로지스틱 회귀분석으로 넘어가는 과정은 심사위원들을 충분히 설득시킬 수 있을 것 같은데 로지스틱 회귀에서 Em 알고리즘 클러스터링으로 넘어가는 타당성이 없었다. 분석에 필요해서 사용한 모델링이 아니라 나 이런것도 알아~ 라는 듯한 느낌의 분석이었다. 어려운 모델링 기법이라고 무조건적으로 사용하기 보다는 주제나 도메인에 맞는 분석기법을 잘 활용해야한다는 것을 깨달았다. 

    - 데이터 확보 부족
> 데이터를 많이 확보하지 못했다. 청년 창업이라는 명확한 타겟층이 있었고 청년이라는 특성상, 자본의 부족으로 인해 가장 중요한 점이 임대료 관련 부분이라고 생각했지만, 용인시 임대료 관련 데이터는 찾을 수 없었다. COMPAS측에서도 임대료 관련 데이터는 제공해주지도 않았고, 부동산 관련 웹사이트에도 용인시의 매물이 잘 나와있지 않았다. 수상작들을 한 번 보면서 데이터를 어떻게 구했는지 보고 싶다. 시간, 공간적 분석을 했어야 했는데 (ex. 시간의 흐름에 따라 창업 트렌드 변화) 데이터가 2017년부터 2019년도 밖에 없어서 시간 분석에 대한 인사이트를 얻지 못했다. 2017에서 2019사이의 창업 트렌드는 많이 변하지 않았고 용인시 내 인구밀도도 크게 변하지 않아서 공간분석만 진행했다는 것이 아쉬웠다.



