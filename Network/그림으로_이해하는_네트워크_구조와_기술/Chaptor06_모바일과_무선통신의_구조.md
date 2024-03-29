# DAY16
작성일 : 2024/02/23

> 범위
- 64 모바일 네트워크
- 65 4G/5G
- 66 로컬 5G

---

> 작성자 : Quarang

## 문제. CDMA의 단점인 페이딩 관리의 어려움이 무엇이며, 해결방안에 대해서 생각해보시오.

> CDMA의 특징

1. 다중 경로 페이딩관리가 어려움 -> 노이즈 주파수 끼리의 간섭

- 다중 경로 페이딩이 발생하면 각 신호가 서로 간섭하여 통신 품질을 저하시킬 수 있음.
- CDMA는 이러한 다중 경로 페이딩을 관리하기 어렵기 때문에 품질이 감소할 수 있음.
- 그래서 기존에 FDMA과 CDMA의 장점을 혼합한 OFDMA가 등장

> FDMA의 특징

- 기존의 FDMA는 주파수와 주파수 사이에 보호대역(Guard Band)라는것이 존재함
- 보호대역은 각 주파수 사이에 할당되는 아주 작은 단위의 대역
- 기존 FDMA는 주파수 대역이 부족해진다는 단점이 있었지만 주파수끼리의 간섭은 없었음


> OFDM/OFDMA란?

- 4세대 이동 통신에 사용되는 통신 방식
- 다수의 직교하는 부반송파들에 정보를 실어서 전송하는 방식
- 장점 : 주파수 효율이 좋아 통신속도가 비약적으로 증가

<img width="564" alt="스크린샷 2024-02-23 오후 10 23 24" src="https://github.com/team-imad-study/study-question/assets/31721255/95e9ffab-8bed-4a26-b93b-e50011c6f1a0">


> 참고 : https://rf-yeolmu.tistory.com/63?category=881824

---

> 작성자 : KUN

## Q. 우리는 5년전쯤 핸드폰을 사용했던 시절에 4g = LTE 라고 인식하고 사용했었습니다. 이는 맞는 이야기 일까요? 틀린 이야기일까요? 의견과 그이유를 서술해주세요!

![화면 캡처 2024-02-24 123228](https://github.com/team-imad-study/study-question/assets/136051281/9120d869-8e27-4680-bb9d-fdb754b67ff6)

초기 ITU에선 4G 의표준 자격을 높게 설정해 LTE는 기준미달로 4G로 못불릴뻔 하였지만

![화면 캡처 2024-02-24 123243](https://github.com/team-imad-study/study-question/assets/136051281/bda24ece-b6bd-4ca9-b42c-7386be0b357c)

이후 ITU의 4G 기준 하향과 더불어 LTE의 기술 수준 향상으로 4G로 불릴수 있게됨

### 4G 에는 LTE뿐아니라 WiMAX 등의 다양한 기술이 포함되어있는 개념임 하지만 LTE 또한 전세계적으로 가장 널리 사용되는 4G 기술중 하나이기 때문에 LTE는 4G다 등의 동의어로 사용되어도 상관없음

---

> 작성자 : PCYSB

## 5G 왜 사람들이 체감 하지 못하느냐

### 1. 주파수
주파수는 전파가 공간을 이동할때 1초동안 진동하는 횟수 -> 보통 Hz 헤르츠라고 부름
주파수의 대역폭을 보통 도로폭이라고 많이 비유하는데 도로폭이 넓다고 속도가 무조건 빠른건 아니지만 그만큼 많은 데이터 수용이 가능하기에 전송속도가 빠를수는 있다.

저대역 1GHz 이하 중대역 1~6 고대역 24이상으로 분류하는데 주파수에는 직진성 회절성이라는 특징이 있음 주파수가 높아질 수록 주기가 작아지고 빠르게 전파가 진동하며 직진성이 높아짐 직진성이 강해져 전송속도는 높아지지만 회절성이 약해져 먼거리까지 도달하기 어렵다. 즉 주파수가 높아지면 직진성은 강해지지만 커버리지는 낮아진다.

그런데 5G의 경우 높은 주파수를 사용할 수 밖에 없다.

5G 는 일반적으로 주파수가 2개로 나눠지는데
1. 우리가 많이 사용하는 3.5GHz~6GHz
2. 진정한 5G라고 이야기하는 mmWave인 28GHz
3.5GHz만 하더라도 넓은 지역을 커버하기 좋지 않은 커버리지인데 여기서 28GHz를 사용하면? 커버리지는 더 낮아질 것이다. 그리고 황금 주파수라고하는 서비스하기 좋은 주파수 영역대가 있는데 기지국 대비 주파수대역대가 좋은 영역을 말한다.

황금주파수
2g 800MHz -> 15km 반경(주파수)
3G 2.1GHz
4G 1.8GHz
5G 3.5GHz ->1km 반경 커버리지는 줄어들고 속도는 늘어남 그럴러면 기지국을 더 늘려야함 전국적으로 늘리기에는 부담이 있음
-> 3.5GHz도 지금 잘 커버를 못하는데 28은? 쉽지 않음


[참고](https://www.youtube.com/watch?v=QO9v6pu6-QM)

---

# DAY17
작성일 : 2024/02/24

> 범위
- 67 이동통신
- 68 Wi-Fi
- 69 공중 무선 LAN
- 70 LWPA

---

> 작성자 : PCYSB

## Q. WiMax는 어디서 사용이 될까?

- 지역이 외곽이거나 인프라 구축이 어려운 지역에서 WiMAX를 활용하여 무선으로 고속 인터넷을 제공할 수 있다.

- 기업 환경에서 무선 통신이 필요한 경우에 사용될 수 있다. 주로 넓은 범위를 커버하고자 하는 기업 네트워크나 산업용 네트워크에서 활용 된다.

- 초기에는 인프라 구축 비용이 비교적 낮고, 빠른 서비스 제공이 가능하다는 장점이있어 일부 지역에서 사용 되었지만 4G, 5G와 같이 더 높은 성능과 향상된 기술을 제공하는 기술의 등장으로 WiMAX의 사용이 감소 중이다.

---

> 작성자 : KUN

## Q.무선통신의 종류중 하나인 WI-FI 는 규격별로 MIMO 라는 다중안테나 통신방식을 사용할 수있는 개체들이 있다 이러한 방식을 사용하는 개체는 빔포밍이라는 기술도 사용할수있는데 이 빔포밍의 장점과 단점을 서술해주세요

### 장점

1. 신호강도 향상 : 전송되는 신호를 특정방향으로 집중시켜 신호강도를 향상시킴

2. 데이터 전송속도 증가: 데이터를 특정 방향으로 집중시켜서 전송하기에 데이터 전송 속도를 증가시킴

3. 무선 커버리지 향상: 신호를 원하는 지역에 집중시기고 그외에 지역에는 신호를 배제도 가능하기에 무선네트워의 효율성을 높일 수 있음

4. 간섭 감소: 신호를 원하는 방향으로 집중시키기에 다른방향으로 발생하는 간섭을 감소시킴

### 단점

1. 복잡성과 비용: 빔포밍은 신호처리및 안테나 배열이 필요하기 때문에 시스템의 구현이 복잡해지고 비용이 증가함 특히 디지털 빔포밍의 경우에는 신호처리와 안테나 제어를 위한 고성능 하드웨어 및 소프트웨어가 필요함

2. 전력소비: 빔포밍은 기존 통신 시스템에 추가 설비가 필요한 구조로써 추가로 더 전력을 소비함

3. 동적환경에서의 제약: 빔포밍은 주로 정적인 환경에서 가장 효과적으로 작동함 하지만 동적 환경에서는 신호간격이나 방향이변할수 있기 때문에 신호의 집중도나 안정성이 떨어질수있음

---

> 작성자 : NCookie

## 공격용 또는 감염된 액세스 포인트를 피하는 방법

### 무료 Wi-Fi 사용 지양하기

공공 장소의 공개된 WiFi 네트워크는 보안이 취약할 수 있다. 은행 관련 업무와 같이 보안에 민감한 정보를 다룰 때에는 무료 와이파이 연결을 피하는 것이 좋다.

### 네트워크 이름 확인

카페, 호텔 등에서 제공하는 와이파이 이름과 비밀번호가 일치하는지 확인한다.

### 신호 강도 확인

공격용 액세스 포인트는 종종 정상 액세스 포인트보다 신호 강도가 약할 수 있다. 따라서 이동하면서 신호 강도를 확인하여 이상한 위치에서 갑자기 강한 신호를 받는지 확인한다.

Wi-Fi 관련 앱을 사용하여 주변 Wi-Fi 네트워크를 스캔하고 확인할 수 있다. 이 앱은 각 네트워크의 세부 정보를 제공하고, 신뢰할 수 있는 네트워크인지 확인할 수 있도록 도와준다.

### 공중 Wi-Fi에 자동 연결 끄기

이전에 네트워크에 연결한 적이 있다면 자동으로 다시 연결될 수 있다. 해당 네트워크가 안전하다고 판단할 수도 있지만 다시 방문한 사이에 상황이 바뀔 수 있다. 때문에 이전에 사용한 네트워크를 삭제하거나, 최소한 자동으로 다시 연결되지 않도록 설정한다.

### VPN 사용

네트워크가 합법적이고 사용하기에 안전하다고 확신하더라도, 가상 사설망(VPN)을 사용하면 정보를 안전하게 유지하는데 도움이 될 수 있다. 여행을 많이 다니거나 공공 장소에서 정기적으로 Wi-Fi에 연결해야 하는 사람에게 VPN은 온라인 안전을 유지하는 데 유용한 도구이다.

## 참고

- [How to use public Wi-Fi safely: 5 tips you need to know before you connect
](https://www.zdnet.com/article/how-to-use-public-wi-fi-safely/)

---

> 작성자 : Quarang

## 문제. 셀룰러 LPWA와 비셀룰러 LPWA가 무엇일지 예상해보고 차이가 무엇일지 생각해 보시오.

> cellular LPWA (면허 대역)

- 통신사의 기지국 및 통신 네트워크는 일반적으로 무선 방송국 라이센스가 필요한 cellular  LPWA에서 사용
- 그러나 LPWA 모듈이 탑재된 IoT 장치에서 기지국까지의 안정적인 통신 환경이 필요합니다.
- IoT 장치와 기지국 사이의 지역은 도시지역, 주거지역, 산업지역 등 인구밀도가 높은 지역이 되는 경향이 있
- 전기, 예를 들어, 전기, 가스, 수도와 같은 생활 인프라에 대한 데이터 수집, 각 국가의 통신 사업자의 통신 네트워크 로밍 등에 활용됨

> non-cellular LPWA (비면허 대역)

- non-cellular  LPWA는 920MHz 대역을 사용
- 통신사의 통신 네트워크을 이용하지 않고도 LPWA 모듈에서 게이트웨이를 통해 얻은 데이터를 네트워크 서버나 앱 서버로 전송할 수 있음
- 산간 지역, 외딴 섬 등 통신사 사업자의 기지국에 연결하기 어려운 환경에서의 통신, 사설 네트워크 통신과 같이 cellular LPWA가 커버할 수 없는 장거리 통신 애플리케이션에 활용됨

---

# DAY18
작성일 : 2024/02/26

> 범위
- 71 블루투스/NFC
- 72 센서 네트워크

---

> 작성자 : KUN

## Q. 우리는 블루투스 이어폰을 사용하다가 사람이 많은 카페 지하철역등을 들어가면 노이즈가 생기거나 끊김현상을 경험한적이 한번쯤 있을겁니다. 이러한 현상의 이유를 블루투스의 단점과 연관지어 설명해주세요!

### 블루투스는 많은 무선통신기술처럼 주파수를 이용해 통신을 합니다.

블루투스 의 통신 규격인 2.4GHz 주파수 대역은
와이파이, 다른 블루투스기기등이 공유하는 대역대입니다.
이로인해 블루투스 기기가 많이 사용되는 곳이나 와이파이가 밀
집되어있는 곳에서는 전파 장애가 벌어져
연결이 불안정해질수있음

(실제로 버스,지하철등에 설치된 공용와이파이는 대부분
2.4GHz 이다.)

---
> 작성자 : Quarang

## 문제. Wifi와 Zigbee의 차이점 및 장,단점을 생각해보시오.

WiFi와 Zigbee 모두 무선통신 기술에 속하며 2.5GHz를 사용함

> WiFi

```
무선 로컬 네트워크 기술의 하나로, 컴퓨터, 스마트폰, 태블릿 등 다양한 디바이스들이 인터넷에 연결할 수 있도록 해주는 기술
```
- 단일화된 유지보수 가능
- 인터넷이 연결되어있기 때문에 24시간 365일 모니터링 및 제어관리 가능
- 제품들의 단가 및 설치 비용이 Zigbee에 비해 높음
- 보내는 데이터량의 크기가 높아 전력이 많이 소비가 됨

> Zigbee

```
무선 통신 기술 중 하나로, 주로 저전력의 근거리 통신을 위해 설계되었으며, 주로 스마트 홈 기기, 산업용 센서 네트워크, 의료 기기 등의 IoT(Internet of Things) 장치 간에 데이터를 교환하는 데 사용
```

- WiFi에 비해 송수신할 데이터량이 크지 않기 때문에 비교적 전력 소모가 덜하고 간섭과 장애물에 약함
- 인터넷이 연결되어있지 환경에서도 사용가능(단, 인터넷을 사용해야하는 경우 따로 스마트 허브가 필요)
- 독립적인 리피터 기능이 내장되어있는 것이 대부분(첫번째 이유의 문제점 해결)
- 스마트홈 시장 활성화로 대대적인 성장 가능성 보유


첨언으로 와이파이 장비와 Zigbee장비는 같은 주파수 대역을 사용하기 때문에 서로간의 간섭을 최소화하기 위해 거리를 유지하는 것이 좋으며,
IoT 제품이 많은 경우 서로 용도에 따라 혼용하여 사용하는 것이 효율적

> 참고
- https://reddreams.tistory.com/1564
- https://youtu.be/2nrVDXwpclA?si=BnG4Z2AyqPJKc0e1
