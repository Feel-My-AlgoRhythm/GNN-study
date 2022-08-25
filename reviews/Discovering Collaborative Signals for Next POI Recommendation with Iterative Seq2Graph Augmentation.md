Paper: [Discovering Collaborative Signals for Next POI Recommendation with Iterative Seq2Graph Augmentation](https://arxiv.org/abs/2106.15814)

![Untitled](https://github.com/Feel-My-AlgoRhythm/GNN-study/blob/main/images/Discovering%20Collaborative%20Signals%20for%20Next%20POI%20Recommendation%20with%20Iterative%20Seq2Graph%20Augmentation%201.png)

- 카테고리와 POI의 쌍을 학습시킴으로써 카테고리의 순차가 반영된 POI 추천을 할 수 있음
1. 사용자의 최근 방문 기록을 시퀀스로 구성
2. 여러 시퀀스를 Directed Graph로 구성 - POI 임베딩
3. Epochs 반복하며 그래프 증강
4. 각 POI가 가지는 카테고리의 시퀀스(전이관계)를 임베딩
5. POI 임베딩을 카테고리 임베딩과 연결
    - 각 노드는 [POI, 카테고리]로 구성됨
6. Position-aware 어텐션 메커니즘 - 사용자의 short-term 선호도를 인코딩
    - 여기서 Position은 지리적인 것이 아니라 최근 방문 순 index를 의미함
7. 각 POI를 방문할 확률 예측
8. top-K 샘플링하여 가장 높은 확률을 가지는 K개 POI 추출
