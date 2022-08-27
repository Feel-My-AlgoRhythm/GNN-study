Paper: [Region-aware POI Recommendation with Semantic Spatial Graph](https://doi.org/10.1109/CSCWD49262.2021.9437810)

지리적 위치와 사용자의 선호 POI 카테고리 간 상관관계가 있음을 전제

### 지식 그래프 구축

![Untitled](https://github.com/Feel-My-AlgoRhythm/GNN-study/blob/main/images/Region-aware%20POI%20Recommendation%20with%20Sementic%20Spatial%20Graph%201.png)

1. set of users, set of POIs, set of POI categories 세 개의 집합 구성
2. 각 POI는 좌표와 연결되며 하나의 범주에 속함
3. user-POI interaction matrix 구성 - 사용자의 평가를 기반으로
4. semantic spatial graph 구성
    - 특정 POI에 대해 (h, w, a)
    - h ∈ξ, a ∈ A, w ∈ W
        - ξ: POI 집합
        - A: POI 속성 집합
        - W: POI 속성의 값 집합

### 모델 학습

![Untitled](https://github.com/Feel-My-AlgoRhythm/GNN-study/blob/main/images/Region-aware%20POI%20Recommendation%20with%20Sementic%20Spatial%20Graph%202.png)

### 데이터셋

- Dianping check-in data
    - 중국 난징 대상
- [Yelp check-in data](https://www.kaggle.com/datasets/yelp-dataset/yelp-dataset)
    - 미국, 캐나다 8개 도시 대상
    - 리뷰, 장소, 사용자, 방문시간 등의 데이터 포함
    - 유사한 데이터를 만들 수 있을 것으로 추정