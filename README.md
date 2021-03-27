# [COMPAS] 용인시 청년창업 지원 대책 도출 공모전

- 준비기간 : 2021.01.07 ~ 2021.01.28

## 분석 과정 

1. 데이터 전처리
    - 외부 데이터 수집<br>
      : COMPAS에서 주어진 데이터 이외의 교통관련, 교육, 의료시설, 문화시설 등 주변 상권에 영향을 줄 수 있을만한 공공데이터 수집.
    - 데이터 통합 <br>
      : COMPAS에서 주어진 데이터와 공공데이터를 함께 활용하기 위해 데이터 통합진행. <br>
        비공개 데이터도 혼합되어 있어 API를 이용해 서버로 코드를 구현하였다. 주어진 데이터를 하나의 데이터 프레임으로 합침.
    - 격자 통합 <br>
      : 250x250 격자와 100x100격자가 혼합되어 있어 더 큰 500x500 격자로 통일하였다. 격자 통합 과정은 QGIS 툴을 사용하였다.
    - 결측 데이터 보완 <br>
      : COMPAS 데이터 중, 행정동 관련 변수에 결측치가 존재해 Google Map 크롤링으로 데이터 추가
    
3. EDA - tableau, python 이용
    - 비공개 데이터 사용으로 인한 예선 탈락 :( <br>
      : 처음 분석 방향을 정하기 위해 tableau를 활용해 대시보드를 만들어보는 과정에서 비공개 데이터를 로컬에 다운받아 활용해서 예선탈락을 맛보았다. 아쉬웠다.
      
4. 분석
    - Getis 검정 통계량을 이용한 hot-spot 분석
    - 로지스틱 회귀분석
    - 가우시안 혼합 모형의 EM 알고리즘


## 느낀점
> 이전의 공모전들은 주어진 주제가 없어서 주제를 잘 설정해 관련 모델링 부분에서 약간 미흡한 점이 있었는데도 불구하고, 수상을 할 수 있었다. 수상은 했지만 개인적으로 모델링 과정에 대한 욕심이 있었고, 이번 공모전을 통해 제대로 된 분석과정을 겪어보고 싶었다. 그래서 일단 공간분석에 따른 자료들을 찾기 시작했고, hot-spot 분석에 많이 사용되는 Getis 분석 (Moran지수, LISA)를 사용했다. 여기서 Spatial Autocorrelation 이라는 용어가 나와서 Autocorrelation 용어부터 정리했지만 Autocorrelation과 Spatial Autocorrelation과는 좀 다른 개념이었던 것 같다. 새로운 분석 기법도 배워보고 적용해봄으로써 많이 배울 수 있었다. 공간 분석 뿐 만이 아니라 그동안 알고 있었던 클러스터링 기법에 대해서도 생각해 볼 수 있었다. 클러스터링에는 kmeans, knn만 있는 줄 알았는데 GMM을 활용한 EM 알고리즘도 새로 적용해봤다. 이번 공모전에서는 같은 데이터에 kmeans, knn, em 알고리즘 모두 시도해보았는데 역시 확률에 대한 가정을 기반으로 한 EM 알고리즘이 클러스터링을 제일 나은 결과를 도출했다. kmeans와 knn은 단순히 다차원 공간에 데이터를 놓고 데이터 점들간의 거리를 고려해 클러스터링을 하는 반면, EM 알고리즘은 조건부 확률을 통해 확률이 가장 높은 클러스터로 할당시켜 집단 내의 동질성과 집단 간의 이질성을 눈에 띄게 높였다. 통계의 중요성을 또 한번 깨달았다!


## 아쉬웠던 점
> 비록 예선탈락했지만 같이 공모전에 나간 팀원들이 다들 공모전 출전 이후로 갑자기 바빠져서 이 공모전에 시간투자를 제대로 하지 못했다. 대학원생 2명, 인턴1명으로 학부생인 내가 분석파트를 거의 다 맡아서 진행할 수 있는 기회를 가질 수 있었다. 분석 파이프라인을 짜는 것 부터 선행연구 찾기 등 많은 일을 했지만 역시 공모전은 시간투자를 많이 한 만큼 수상확률이 높아지는 것 같다. 수상을 하지 못한건 조금 아쉬웠다. 최종 제출파일을 제출하면서 나름 잘 했다고 생각했지만 다시 보니 매우 부족한 부분이 많았다. 비공개 데이터를 활용한 대시보드가 함께 제출되기도 했고, 분석과정에서 논리적인 오류도 많았다. 특히 hot-spot 분석과 로지스틱 회귀분석으로 넘어가는 과정은 심사위원들을 충분히 설득시킬 수 있을 것 같은데 로지스틱 회귀에서 Em 알고리즘 클러스터링으로 넘어가는 타당성이 없었다. 분석에 필요해서 사용한 모델링이 아니라 나 이런것도 알아~ 라는 듯한 느낌의 분석이었다. 어려운 모델링 기법이라고 무조건적으로 사용하기 보다는 주제나 도메인에 맞는 분석기법을 잘 활용해야한다는 것을 깨달았다. 
> 데이터를 많이 확보하지 못했다. 청년 창업이라는 명확한 타겟층이 있었고 청년이라는 특성상, 자본의 부족으로 인해 가장 중요한 점이 임대료 관련 부분이라고 생각했지만, 용인시 임대료 관련 데이터는 찾을 수 없었다. COMPAS측에서도 임대료 관련 데이터는 제공해주지도 않았고, 부동산 관련 웹사이트에도 용인시의 매물이 잘 나와있지 않았다. 수상작들을 한 번 보면서 데이터를 어떻게 구했는지 보고 싶다. 시간, 공간적 분석을 했어야 했는데 (ex. 시간의 흐름에 따라 창업 트렌드 변화) 데이터가 2017~2019년도 밖에 없어서 시간 분석에 대한 인사이트를 얻지 못했다. 2017~2019사이의 창업 트렌드는 많이 변하지 않았고 용인시 내 인구밀도도 크게 변하지 않아서 공간분석만 진행했다는 것이 아쉬웠다.





