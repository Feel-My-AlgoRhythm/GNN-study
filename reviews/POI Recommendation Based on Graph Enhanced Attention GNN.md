Paper: [POI Recommendation Based on Graph Enhanced Attention GNN](https://ieeexplore.ieee.org/document/9642167)

![Untitled](https://github.com/Feel-My-AlgoRhythm/GNN-study/blob/main/images/POI%20Recommendation%20Based%20on%20Graph%20Enhanced%20Attention%20GNN%201.png)

- 방문기록의 콜드스타트 문제를 보완하기 위해 POI의 속성을 활용함
- POI 속성은 텍스트로부터 추출함
- User-POI Interaction 그래프, POI 속성, User의 단기적인 선호도를 사용함
- Graph-enhanced Attention 메커니즘
    - 위의 3개 정보 간 연관성을 계산
    - 그래프 구조의 데이터와 텍스트 데이터의 연관성을 계산하기 위해 본 논문에서 제안
- 단기적인 선호도는 12시간 내 상호작용한 POI의 시퀀스를 GRU를 사용하여 ???로 구성하고, 어텐션 메커니즘을 사용하여 시퀀스 내 각 POI의 가중치(attention score)를 계산
    - 여기서 GRU 네트워크의 Output은 무엇을 의미하는지?
- Gowalla, Foursquare 데이터셋을 사용함
    
![Untitled](https://github.com/Feel-My-AlgoRhythm/GNN-study/blob/main/images/POI%20Recommendation%20Based%20on%20Graph%20Enhanced%20Attention%20GNN%202.png)
