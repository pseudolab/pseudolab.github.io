---
layout: post
title:  "Deep Dive Into GNN : Intro"
author: 김진수
categories: [ 8기 아카데미 ]
image: assets/images/post/8th-builder/JinsuKim/graph_pseudo_lab.png
---

안녕하세요! 처음 뵙겠습니다 :) 저는 이번에 Deep Dive Into GNN 스터디를 맡은 8기 아카데미 빌더 김진수입니다.
이번 포스트에서는 2024년 상반기에 진행하게 될 Graph Neural Network에 대한 Stanford CS224W 강의와 논문 리뷰 스터디에 대해 간단히 소개하고자 합니다. 

## 스터디 소개

이 스터디는 Graph Neural Network에 대한 기초적 이해가 스터디의 핵심입니다. Graph에 대한 기본적 이해와 Neural Network에서 어떤 방식으로 구현되는지 자세히 들여다보고, 관련 논문과 과제 코드를 한번 분석해보며 천천히, 그렇지만 짙게 공부를 해보자 합니다. 사실 아카데미 빌더로 활동하는 것은 이번이 처음인지라 아마 여러 시행착오가 있을 수 있겠지만 그래도 참여하는 모든 사람들이 기대했던 수준 이상으로 많이 얻어갈 수 있는, 그런 알찬 스터디가 되었으면 하는 바람으로 구상해보았습니다 :)

스터디를 위한 참고 자료들은 아래 링크를 통해 확인하실 수 있습니다. 
- 강의 자료: [Stanford CS224W - Machine Learning with Graphs](https://web.stanford.edu/class/cs224w/)
- 논문 자료: [Github - GNNPapers](https://github.com/thunlp/GNNPapers)

## 빌더 소개
<img src = "assets/images/post/8th-builder/JinsuKim/graph_pseudo_lab.png">

빌더 프로필 링크
- 노션 링크: [8기 빌더 소개: 김진수](https://www.notion.so/chanrankim/351f0efb2a6a4c9b9c34678b2e7b77af?pvs=4)
- 깃허브 링크: [Github - zinzinbin](https://github.com/ZINZINBIN)
- 링크드인 링크: [Linkedin - zinzinbin](https://www.linkedin.com/in/zinzinbin/)

저는 가짜연구소에서 8기 스터디 빌더로 활동하게 된 김진수 입니다. 사실 저는 데이터 사이언스와는 무관한 핵융합 플라즈마 분야를 연구하고 있습니다. 최근에 제 분야에서 ML application에 집중하면서 데이터 기반 플라즈마 모델링, 강화학습 기반 토카막 플라즈마 제어와 토카막 장치 디자인 최적화와 같은 연구를 진행하고 있습니다. 아무래도 혼자 공부하기 어려웠고 데이터 사이언스 분야에 대한 갈증을 많이 느꼈는데, 우연한 기회에 가짜연구소를 접하게 되면서 이런 갈증을 많이 해소할 수 있었죠. 가짜연구소에서 다양한 스터디를 통해 머신러닝 분야의 다양한 토픽들을 접해보면서 제 분야에서 다양한 시도를 마음껏 해볼 수 있었답니다. 이번에 제가 빌드를 한 이 스터디도 누군가에겐 지식의 성장뿐만 아니라 GNN을 활용해 새로운 시도를 해볼 수 있는 그런 기회를 제공할 수 있는 활동이 되었으면 좋겠습니다.

## 스터디 계획

이 스터디는 기본적으로 Stanford CS224W Lecture 강의를 듣고 논문 리뷰 발표를 1회씩 진행하는 것을 목표로 하고 있습니다. 다만 논문 리뷰의 경우 진도에 따라 참여하시는 분들과 같이 조율할 계획입니다. 핵심적인 논문들은 스터디를 하는 과정에서 모두 다룰 수 있으면 좋을텐데, 각자 필요로 하거나 궁금한 내용을 좀 더 Deep Dive 할 수 있기 위해선 참여자들이 원하는 논문에 대해 스스로 리뷰를 해보는게 좋지 않을까 싶습니다. Stanford CS224 강의는 워낙 유명한지라 잘 듣고 따라가며 내용을 정리해볼 수 있다면 언제든 다시 공부할 순간이 왔을 때 쉽게 따라갈 수 있을거라 기대합니다. 

이외에도 스터디를 진행하는 동안 블로그 포스트 형태로 공식적인 기록물을 남기는 것을 목표로 하고 있습니다. 기록을 통해 스터디를 했던 과정에서 배운 내용들을 정리해볼 수도 있어서 좋은 기회가 되리라 생각합니다. 현재 가짜연구소에서 3회 블로그 포스팅 하는 것을 목표로 하고 있고, 앞으로 2회에 걸쳐 스터디를 통해 알게 된 내용들을 정리해볼 계획입니다. 

정리하자면,
- 매 스터디마다 지정된 강의에 대한 리뷰 및 참여자들이 선정한 논문에 대한 리뷰 + 질문/논의하는 시간을 가져볼 것입니다. 
- 스터디를 진행하는 동안 총 3회 (지금 읽고 계신 포스트가 1회) 블로그 포스팅을 통해 기록물을 남길 예정입니다.

## 주차별 목표
주차별 목표는 [노션 계획표](https://www.notion.so/chanrankim/Deep-Dive-Into-GNN-8deb729d3b534aaba46362ca5c65c74b?pvs=4) 혹은 아래 테이블을 통해 확인하실 수 있습니다. 스터디 주차별 계획은 Stanford CS224W 강의 순서와 동일하며, 1개 챕터만 편성된 주차에 대해 논문 리뷰 혹은 과제 코드 분석을 진행해볼 계획입니다. 

| 주차  | 내용                                |
|-------|-------------------------------------|
| 1주차 | OT (스터디 소개 및 방향 논의), Ice Breaking |
| 2주차 | Introduction, Node Embedding |
| 3주차 | Graph Neural Network / A general perspective of GNN |
| 4주차 | GNN augmentation and training |
| 5주차 | Theory of GNNs |
| 6주차 | Heterogeneous graphs |
| 7주차 | Knowledge graphs |
| 8주차 | 중간 리뷰 타임 - 정모 |
| 9주차 | Reasoning over knowledge graphs |
| 10주차| Fast neural subgraph matching |
| 11주차| GNNs for recommenders |
| 12주차| Deep generative models for graphs |
| 13주차| Advanced topics in GNN |
| 14주차| Graph Transformer / Scaling to large graphs |
| 15주차| Link Prediction and Causality / Algorithmic reasoning with GNNs |

청강도 가능하기 때문에 가짜연구소의 여러 분들이 종종 스터디에 들어와 발표를 들을 수도 있습니다. 그렇다고 부담을 가지실 필요 없이 자연스럽게 공부했던 내용을 정리해서 같이 논의해보는 그런 시간으로 생각해주시면 좋을 것 같습니다. 
