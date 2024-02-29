---
layout: post
title:  "가짜연구소와 함께 JAX 입문하기"
author: 박우성
categories: [ 8기 아카데미 ]
image: assets/images/post/8th-builder/seriousran/ship.png
---

안녕하세요, 박우성이라고 합니다. JAX 스터디 빌더로써 글을 쓰게 되었습니다.

## JAX 프로젝트 소개

JAX를 설명하는 글은 아니니, 일단 제가 JAX를 접하고 스터디를 빌드한 이유부터 설명해보겠습니다. 저는 게임을 [**gymnasium(구 gym)**](https://gymnasium.farama.org/index.html) API형태로 강화학습 환경을 구현하고 그것을 클리어하는데 큰 흥미를 느꼈습니다. 하지만 제가 가진 컴퓨팅 자원은 한정적이었고, 이 한정된 자원에서 어떻게 해야 최대한 많은 학습을 할 수 있을까 고민했었는데요, 평소 오픈소스에 관심이 많은 저는 여러 깃허브를 둘러보다가 점점 많은 강화학습 알고리즘들이 JAX로 구현되거나 pytorch와 같이 구현된 것을 보게 되었습니다. 오래동안 지켜봐왔지만 이런 현상들이 점점 증가하는 것을 체감하고 있었고, 강화학습 환경 또한 JAX로 구현하면 더 빨라질 수 있다는 것도 알게 되었습니다. 아래 링크는 JAX 생태계에 엄청난 영향을 준 저장소는 아닙니다. 하지만 제가 공부를 하기로 마음을 먹었던 저장소들이었습니다.

* [JAX로 구현된 강화학습 환경(jumanji)](https://github.com/instadeepai/jumanji)
* [JAX로 구현된 강화학습 알고리즘](https://github.com/vwxyzjn/cleanrl/tree/master/cleanrl)

구글, 딥마인드가 JAX를 쓴다는 것을 알고 있긴 했지만 막연하게 좋나보다 싶던 것들이 아 진짜 바뀌려나? 를 느끼게 되었고 그때부터 공부를 하겠다고 마음을 먹었습니다.

구글 머신러닝 부트캠프에서 만난 분들과 스터디를 진행했었습니다. 하지만 기본적인 공부보다 더한 공부에 대한 갈증을 느꼈고 그렇게 가짜연구소에서의 스터디가 기획되었습니다! 가짜연의 스터디는 보통 3월에 진행되지만 저의 강력한 의지로 1월에 모집하게 되었습니다.

## 그래서 JAX가 뭔데?

[**JAX 공식 깃허브**](https://github.com/google/jax)에서는 JAX를 다음과 같이 표현합니다.

> JAX is Autograd and XLA, brought together for high-performance numerical computing, including large-scale machine learning research. 
> 
> JAX는 대규모 머신 러닝 연구를 포함한 고성능 수치 컴퓨팅을 위해 Autograd와 XLA가 결합한 것입니다.

추상적이어서 잘 와닫지는 않습니다, 어떤 곳에서는 "가속기를 단 넘파이"라고 표현하기도 하는데요, 실제로 거의 모든 API가 numpy와 동일합니다.

하지만 다른 부분도 있는데요, 난수를 생성할 때마다 key(seed랑 비슷한 개념)를 인수로 입력합니다.

side-effect를 지양한 함수형 프로그래밍을 설계하고 JIT을 통해 코드의 속도를 높입니다.

이 밖에도 많은 내용들이 있지만 JAX보다는 JAX 스터디에 대해 소개하는 글이기에 대표적인 것 두개만 설명드렸습니다. 이 밖에도 많은 내용이 있습니다. 자세한 내용은 아래 링크를 참고하면 좋을 것 같습니다.

- [**NeurIPS 2020: JAX Ecosystem Meetup**](https://www.youtube.com/watch?v=iDxJxIyzSiM)
- [**Awesome JAX**](https://github.com/n2cholas/awesome-jax)
- [**JAX Documentation**](https://jax.readthedocs.io/en/latest/tutorials/index.html#jax-tutorials)

## 프로젝트 계획

JAX에 대한 자료가 아직 많이 있지 않다보니 공식 문서를 읽는 방식으로 진행됩니다.

하지만 초심자를 위한 스터디이다보니 임의로 "아직" 중요하지 않다 판단된 것들은 걸러내었습니다.

추후 공식문서의 링크가 바뀔 수도 있으니 직접 들어가시기보다는 참고만 하시는 것을 추천드립니다. (그냥 위에서부터 공부한 것이긴 합니다)

| 주차 | 내용 |
|--------|---|
| 1주차  |  [**Installing JAX**](https://jax.readthedocs.io/en/latest/installation.html) <br> [**JAX Quickstart**](https://jax.readthedocs.io/en/latest/notebooks/quickstart.html) <br> [**How to Think in JAX**](https://jax.readthedocs.io/en/latest/notebooks/thinking_in_jax.html) |
| 2주차  | [**JAX As Accelerated NumPy**](https://jax.readthedocs.io/en/latest/jax-101/01-jax-basics.html) <br> [**Just In Time Compilation with JAX**](https://jax.readthedocs.io/en/latest/jax-101/02-jitting.html) <br> [**Automatic Vectorization in JAX**](https://jax.readthedocs.io/en/latest/jax-101/03-vectorization.html) <br> [**Advanced Automatic Differentiation in JAX**](https://jax.readthedocs.io/en/latest/jax-101/04-advanced-autodiff.html)   |
| 3주차  | [**Pseudo Random Numbers in JAX**](https://jax.readthedocs.io/en/latest/jax-101/05-random-numbers.html) <br> [**Working with Pytrees**](https://jax.readthedocs.io/en/latest/jax-101/05.1-pytrees.html) <br> [**Parallel Evaluation in JAX**](https://jax.readthedocs.io/en/latest/jax-101/06-parallelism.html) <br> [**Stateful Computations in JAX**](https://jax.readthedocs.io/en/latest/jax-101/07-state.html)  |
| 4주차  | [🔪 **JAX - The Sharp Bits** 🔪](https://jax.readthedocs.io/en/latest/notebooks/Common_Gotchas_in_JAX.html#) |
| 5주차  | [**JAX Frequently Asked Questions (FAQ)**](https://jax.readthedocs.io/en/latest/faq.html)  |
| 6주차  | [**Understanding Jaxprs**](https://jax.readthedocs.io/en/latest/jaxpr.html) <br> [**Pytrees**](https://jax.readthedocs.io/en/latest/pytrees.html) <br> [**The Autodiff Cookbook**](https://jax.readthedocs.io/en/latest/notebooks/autodiff_cookbook.html)  |
| 7주차  | [**Training a Simple Neural Network, with tensorflow/datasets Data Loading**](https://jax.readthedocs.io/en/latest/notebooks/neural_network_with_tfds_data.html) <br> [**Training a Simple Neural Network, with PyTorch Data Loading**](https://jax.readthedocs.io/en/latest/notebooks/Neural_Network_and_Data_Loading.html) <br> [**263: JAX PRNG Design**](https://jax.readthedocs.io/en/latest/jep/263-prng.html) |
| 8주차  | Flax, Optax, Chex 맛보기  |
| 9주차  | JAX Pattern, Design : Case-study, 문제 출제/검토/풀기 |
| 10주차 | JAX Pattern, Design : Case-study, 문제 출제/검토/풀기 |
| 11주차 | JAX Pattern, Design : Case-study, 문제 출제/검토/풀기 |

문제 출제/검토/풀기 의 경우는 맨 처음의 계획은 이 스터디가 문제를 서로 풀며 공부를 더욱 열심히 해보자는 취지로 문제를 내기로 하였으나 저(빌더)의 역량부족으로 인하여 중단되었습니다. 나중에라도 문제를 만들고 싶은 마음입니다.