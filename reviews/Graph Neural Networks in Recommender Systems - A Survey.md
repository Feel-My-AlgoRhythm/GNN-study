Paper: [[2020] Graph Neural Networks in Recommender Systems: A Survey](https://arxiv.org/pdf/2011.02260.pdf)

# GNN

- GNN은 연결관계와 이웃 노드들의 상태를 이용해 각 노드의 상태를 업데이트하고 마지막 상태를 통해 예측
- node embedding: 각 점의 마지막 상태
- 이웃 노드들 간 정보를 이용해서 특정 노드를 잘 표현할 수 있는 특징 벡터를 잘 찾아내는 것이 GNN의 목표
    
    ![정점 u를 표현하는 d차원의 벡터](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/70572efc-8069-4e9c-ae91-938dd3c0bef2/Untitled.png)
    
    정점 u를 표현하는 d차원의 벡터
    
    - 각 노드가 feature 벡터를 가짐

GNN 관련 논문들은 크게 세 가지로 나눌 수 있음

- Recurrent Graph Neural Network
- Spatial Convolutional Network
- Spectral Convolutional Network

---

# Knowledge Graph

- knowledge: 서로 관계가 있는 대상(entity)들의 관계(relation)를 모아 놓은 것
- knowledge graph: knowledge를 그래프 구조로 표현한 것
    - node: knowledge의 entity
    - edge: knowledge의 relation
        - (head entity, relation, tail entity) 형태로 head entity와 tail entity 간의 관계를 표현
    - knowledge graph를 임베딩화하고 추천시스템에 적용하면
    user나 item에 대한 side information을 포함할 수 있음

## Recommendation and Knowledge Graph

- Collaborative filtering은 user-item interaction
- Content-based filtering은 item-attribute interaction
- knowledge graph는 위 두 가지 관계를 모두 표현 가능하므로 두 방식의 단점 극복
- knowledge graph 기반 대표적인 딥러닝 추천 모델: KGCN, KGAT, RippleNet

---

# Graph Learning-based Recommender Systems

- 노드 간 관계를 모델링하기 위해 그래프 임베딩
    - Factorization-based Methods
    - Distributed Representation-based Methods
    - Neural Embedding-based Methods

## 그래프의 분류

그래프는 다음과 같이 분류 가능

- Directed/Undirected Graph
    - Directed Graph: 모든 간선이 한 노드에서 다른 노드로 향함
    - Undirected Graph: 간선이 역방향까지 한 쌍씩 존재
- Homogeneous/Heterogeneous Graph
    - Homogeneous Graph: 동일 타입의 노드와 간선으로 구성
    - Heterogeneous Graph: 여러 유형의 노드와 간선으로 구성
- Hypergraph
    - 간선이 정점 수에 관계없이 결합할 수 있음

# GNN 기반 추천 모델의 사례

### Session-based Recommendation

- Ruihong Qiu, Jingjing Li, Zi Huang, and Hongzhi YIn. 2019. Rethinking the Item Order in Session-Based Recommendation with Graph Neural Networks. In CIKM. 579-588
- Shu Wu, Yuyuan Tang, Yanqiao Zhu, Liang Wang, Xing Xie, and Tieniu Tan. 2019. Session-based recommendation with graph neural networks. In AAAI. 346-353.

### POI Recommendation

- Buru Chang, Gwanghoon Jang, Seoyoon Kim, and Jaewoo Kang. 2020. Learning Graph-Based Geographical Latent Representation for Point-of-Interest Recommendation. In CIKM. 135-144.
- Nicholas Lim, Bryan Hooi, See-Kiong Ng, Xueou Wang, Yong Liang Goh, Renrong Weng, and Jagannadan Varadarajan. 2020. STP- UDGAT: Spatial-Temporal-Preference User Dimensional Graph Attention Network for Next POI Recommendation. In CIKM. 845-854.
- Shiwen Wu, Yuanxing Zhang, Chengliang Gao, Kaigui Bian, and Bin Cui. 2020. Garg: anonymous recommendation of point-of-interest in mobile networks by graph convolution network. DSE 5, 4 (2020), 433-447.

### Group Recommendation

- Zhixiang He, Chi-Yin Chow, and Jia-Dong Zhang. 2020. GAME: Learning Graphical and Attentive Multi-View Embeddings for Occasional Group Recommendation. In SIGIR. 649-658.
- Wen Wang, Wei Zhang, Jun Rao, Zhijie Qiu, Bo Zhang, Leyu Lin, and Hongyuan Zha. 2020. Group-Aware Long- and Short-Term Graph Representation Learning for Sequential Group Recommendation. In SIGIR. 1449-1458.

### Multimedia Recommendation

- Yinwei Wei, Xiang Wang, Liqiang Nie, Xiangnan He, and Tat-Seng Chua. 2020. Graph-Reined Convolutional Network for Multimedia Recommendation with Implicit Feedback. In ACM MM. 3541-3549.
- Yinwei Wei, Xiang Wang, Liqiang Nie, Xiangnan He, Richang Hong, and Tat-Seng Chua. 2019. MMGCN: Multi-Modal Graph Convolution Network for Personalized Recommendation of Micro-Video. In ACM MM. 1437-1445.

### Bundle Recommendation

- Jianxin Chang, Chen Gao, Xiangnan He, Depeng Jin, and Yong Li. 2020. Bundle Recommendation with Graph Convolutional Networks. In SIGIR. 1673-1676.

# GNN 기술

## GCN

## GraphSAGE

## GAT

## GGNN

## HGNN

# GNN 기반 추천 시스템

## GNN in User-Item Collaborative Filtering

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/66f50bec-3040-426b-b605-25ecc4336a96/Untitled.png)

- 사용자가 상호작용한 아이템과 상호작용한 다른 사용자의 정보를 활용
    - 노드: User, Item
    - 간선: 상호작용

## Sequential Recommendation

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e4768fd0-b0f1-4956-a02f-ae873a073ec6/Untitled.png)

- 최근 활동을 기반으로 사용자의 다음 선호 예측
- 순차적 패턴을 모델링
- [그림4]
    1. user behavior sequence 중 i_2→i_3→i→2를 i_2↔i_3의 그래프로 만듬
    2. GNN 블록을 거쳐 각 노드의 정보가 개별 벡터로 임베딩
    3. RNN Sequence Model의 마지막 hidden state를 사용자의 다음 선호 아이템으로 예측

## Social Recommendation

## Knowledge Graph based Recommendation

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5f90fdf1-7407-422c-b46a-f3e19a76adef/Untitled.png)

### 장단점

- 장점: 지식 그래프의 의미 관계가 항목 표현에 유리 → 결과 해석 용이함
- 단점: 그래프 구조가 복잡함

### 그래프 구성

1. 사용자 노드를 지식그래프에 통합
    - [KGAT, MKGAT, CKAN] 사용자 노드를 하나의 엔티티 유형으로 하고 사용자와 아이템 간의 상호작용 정의
        - 사용자-아이템 엔티티 사이의 최단거리 측정
2. ATBRG [35] exhaustively searches the multi-layer entity neighbors for the target item and the items from the user’s historical behaviors and restores the paths connecting the user behaviors and the target item by multiple overlapped entities. In order to emphasize the information-intensive entities, ATBRG further prunes the entities with a single link, which can also help control the scale of the graph. Although these methods can obtain subgraphs more relevant to the user-item pair, it is quite time-consuming to pre-train the entity embedding or search and prune paths exhaustively. An effective and efficient subgraph construction strategy is worthy of further investigation.
3. Another direction is to implicitly use the user nodes to distinguish the importance of different relations. For instance, KGCN [147] and KGNN-LS [145] take the user nodes as queries to assign weights to different relations. In terms of graph construction, this line of research emphasizes the users’ preferences towards relations instead of the collaborative signal in user-item interactions.

---

여기서부터는 Other Tasks

## POI Recommendation

POI와 사용자의 과거 방문 기록 간 지리적 영향을 사용하여 전이 패턴 모델링

### 그래프 데이터의 종류

- User-POI Bipartite Graph
- Sequence Graph based on Check-ins and Geographical Graph
    - 일정 거리 내의 POI 연결
    - 간선 가중치 가짐
    - Chang et al.[10]: 사용자가 두 POI를 연속적으로 자주 방문할수록 두 POI 간 지리적 영향 큼

---

# References

1. [https://blog.dramancompany.com/2022/06/kgat을-이용한-인재-추천-시스템/](https://blog.dramancompany.com/2022/06/kgat%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%9D%B8%EC%9E%AC-%EC%B6%94%EC%B2%9C-%EC%8B%9C%EC%8A%A4%ED%85%9C/)
2. [https://glanceyes.tistory.com/entry/추천-시스템-GNNGraph-Neural-Network와-이를-응용한-NGCFNeural-Graph-Collaborative-Filtering와-LightGCN](https://glanceyes.tistory.com/entry/%EC%B6%94%EC%B2%9C-%EC%8B%9C%EC%8A%A4%ED%85%9C-GNNGraph-Neural-Network%EC%99%80-%EC%9D%B4%EB%A5%BC-%EC%9D%91%EC%9A%A9%ED%95%9C-NGCFNeural-Graph-Collaborative-Filtering%EC%99%80-LightGCN)
3. [https://dl.acm.org/doi/pdf/10.1145/3535101?casa_token=2oWB_Q_spoYAAAAA:Bw-3o59oiGsZXZmSK5ACGVw8PnG9A-erdFSQoFwgLyXMzB1OH__ZrsuytpXgg_DBhLD2-TTXiqTI](https://dl.acm.org/doi/pdf/10.1145/3535101?casa_token=2oWB_Q_spoYAAAAA:Bw-3o59oiGsZXZmSK5ACGVw8PnG9A-erdFSQoFwgLyXMzB1OH__ZrsuytpXgg_DBhLD2-TTXiqTI)
