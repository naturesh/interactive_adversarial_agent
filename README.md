# Interactive_Adversarial_Agent 고등학교 3학년 발표 요약 
Interactive_Adversarial_Agent ( 대화형 적대 에이전트 )


### 목표
  
- 대화형 적대 에이전트는 쉽게말해 비판하는 두개의 LLM 이라고 생각할수 있습니다.
- 이를 통해 환각 현상을 줄이고 더욱 구체적인 답변을 받는것을 목표로 합니다.
---


### 아이디어

- GAN 이라는 생성형 적대 모델을 탐구하면서 두개의 모델이 서로 경쟁하며 성능을 높이는 방식을
- LLM에 적용해 환각 현상을 해결해보면 어떨까 하는 생각에 제작을 시작했습니다.


<br>

### 제작 과정

- 대화형 적대 에이전트는 지속적인 비판 과정을 거치기 때문에 많은 토큰 소모가 따를수 있습니다.
- 따라서 이를 해결하기 위해서 Llama3 모델을 이용하여 비용 문제를 해결하였습니다.
<br>

- Llama3 모델을 이용하는데 있어서 가장 큰 문제는 naming 입니다. Gpt 모델과는 달리
- 프롬프트가 user, assistant 두가지만 존재하기 때문에 user을 `real user`, `비판자`로 나누었습니다.
<br>

- 저는 이러한 대화형 적대 에이전트를 주식 분석가로 만들어 보았습니다. 기본적인 분석가와
- 모든 의견에 사실적,비판적으로 다가서는 Dave라는 LLM으로 총 2개의 LLM을 준비했습니다.
- 또한 tools를 분석가에게 제공함으로서 인터넷 서칭, 여러가지 추가 정보 탐색이 가능토록 하였습니다.

<br>
<p align="center">
  <img src="https://github.com/user-attachments/assets/c26bc83d-8753-4bd6-9ee9-eeae992f4d87">
</p>
<br>

- Dave와 분석가는 다음과 같은 프롬프트를 통해 서로의 비판자 역할을 가능하도록 했습니다.
<p align="center">
  <img src="https://github.com/user-attachments/assets/ceecc645-b490-41d6-a23a-98e9cf3abc34">
</p>

<br>

- 결과적으로 구상한 워크플로우는 다음과 같습니다.
<p align="center">
  <img src="https://github.com/user-attachments/assets/2cf72c4a-7abe-4dc1-98cd-cc8f5e64b7f2" width=300>
</p>



### 실행 및 결과 

<img width="743" alt="image" src="https://github.com/user-attachments/assets/f1826386-6517-491a-959e-8219e97464d7" />


- user을 `real user`, `비판자`로 프롬프트 엔지니어링을 통해 나누는 과정, 비판자와 Dave가 비판하는 과정은 문제가 없었지만
- 서로 토론하는 과정이 길어지면서 LLM 최대 길이에 도달하여 오류가 발생하고 말았습니다.


### 고찰 

- 현재 이러한 인공지능의 토큰 한계점은 인공지능이 더욱 깊게 사고하는 방향을 막는 큰 장애물이라고 할수 있을것 같습니다.
- 현재 인공지능 학습 과정에는 토큰 수를 늘릴수록 연산량이 배로 불어나기 때문에 길게 늘릴수 없다는 문제는 인지하고 있지만
- 이를 해결할 새로운 지도학습 방법에 대해 탐구를 해보겠습니다.








