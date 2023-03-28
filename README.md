# sc1. 다음 분기에 어떤 게임을 설계해야 할까
1980년부터 2020년까지 이름, Platform, Genre, Publisher, 나라별 게임 Sales를 포함하는 데이터를 분석해 다음 분기에 어떤 게임을 설계할지 결정하는 프로젝트

pandas, matplotlib를 이용해 분석

## 1. 지역에 따라서 선호하는 게임 장르

1. 나라, 장르별 판매량 표와 그래프
<img width="786" alt="image" src="https://user-images.githubusercontent.com/110436172/228224991-d4f23552-6dbf-47db-bbd4-d507e9756199.png">
2. 나라, 장르별 판매량 비율 표와 그래프
<img width="791" alt="image" src="https://user-images.githubusercontent.com/110436172/228225076-5c5fc58f-3fb1-42ef-887d-c43fda512f80.png">

## 2. 연도별 게임 트렌드

1. 연도별 게임 트렌드
<img width="700" alt="image" src="https://user-images.githubusercontent.com/110436172/228225626-3c5968ac-0879-4e9a-8dc4-9280e7a29c3c.png">

## 3. 출고량 높은 게임에 대한 분석

1. 2000만장 이상 출고된 게임 중 platform 비율
<img width="735" alt="image" src="https://user-images.githubusercontent.com/110436172/228225899-5b94a8d7-789a-47eb-bd91-734ff6e81a2a.png">
2. 2000만장 이상 판매된 게임 중 Genre 비율
<img width="726" alt="image" src="https://user-images.githubusercontent.com/110436172/228226093-3eb09840-8e3a-414a-80ad-f74f5b42c5b0.png">

## 4. 결론
1. 년도별 Platform 추세
<img width="703" alt="image" src="https://user-images.githubusercontent.com/110436172/228226482-b14b23ad-d867-4658-b672-15ec0cd82515.png">
2. 나라별 판매량 비율
<img width="676" alt="image" src="https://user-images.githubusercontent.com/110436172/228226621-5c455f63-42e5-4a18-933c-52980fafccef.png">
3. 미국의 장르별 판매량 비율 
<img width="590" alt="image" src="https://user-images.githubusercontent.com/110436172/228226743-c510ffca-dbfb-4d10-9d39-3e713389f55e.png">

1) 전체적으로 판매량이 줄어드는 추세이나 데이터 수를 감안했을 때 PS4로 출시하는 게임의 수가 많음
2) 미국의 게임 판매량이 총 판매량의 50%정도로 북미의 게임시장이 큼
3) 미국에서 Action의 인기가 가장 많으나 출고량이 높은 게임의 장르와 교집합으로 Sports가 제일 안정적
### 결론
<img width="382" alt="image" src="https://user-images.githubusercontent.com/110436172/228227161-f65f195d-4eca-4d77-889e-59c25c8f9b5f.png">



# sc2. 냉매사용기기의 충전량 통계를 이용한 냉매사용기기 충전량 산정
2020년 관리번호, 시도, 시군구, 냉매종류, 용도, 압축유형, 냉동능력, 최대충전량, 회수량, 누출량, 재충전량, 보관량, 인도량, 폐기량, 구매량, 충전량을 포함한 데이터를 이용해 냉매사용기기 충전량을 산정

pandas, matplotlib, seaborn 등을 이용해 분석

## 1. 전처리 후 데이터 분석 
![image](https://user-images.githubusercontent.com/110436172/228227937-ba5b6f70-b5fc-401b-9d1c-328515307867.png)

1. 냉매 종류 : R-134a가 다른 냉매보다 충전량이 높은 경향을 보인다.
2. 압축기종류 : 터보식 압축기가 다른 압축기보다 충전량이 높은 경향을 보인다.

## 2. 순열 중요도
<img width="743" alt="image" src="https://user-images.githubusercontent.com/110436172/228228570-d74f1b81-8689-4d29-888c-9cedb3db88dd.png">

모델마다 약간의 차이는 있었지만 Permutation Importance는 RT > Log_RT > Compression_type > Refrigerant > Purpose > State 순

### 3. 결론
1. 네 종류의 회귀 모델을 사용보았는데 Ridge Regression을 사용했을 때 가장 좋은 결과를 얻을 수 있었다.
2. 냉매 종류가 R-134a일 때 다른 냉매보다 충전량이 높은 경향을 보인다.
3. 압축기종류가 터보식 압축기일 때 다른 압축기보다 충전량이 높은 경향을 보인다.
4. 모델마다 약간의 차이는 있었지만 Permutation Importance는 RT > Log_RT > Compression_type > Refrigerant > Purpose > State 순이었다.
5. 더 많은 데이터를 얻을 수 있다면 조금 더 정확한 예측을 할 수 있을 것 같다.


# sc3. 트랙 데이터 분석을 통해 음악의 계절 예측
스포티파이 api를 이용해서 노래 이름을 입력하면 어떤 계절 느낌이 나는 음악인지 보여주는 프로젝트

pandas, Metabase(대시보드) 등 사용

## 1. 파이프라인
<img width="779" alt="image" src="https://user-images.githubusercontent.com/110436172/228229342-3a2e84ee-37b3-4161-91c3-14897ce91d96.png">

## 2. 데이터 분석
<img width="396" alt="image" src="https://user-images.githubusercontent.com/110436172/228230537-a0d4ff03-0744-4c65-82cc-2749f2bdf7b1.png">

1. Danceability, Energy, Valence는	여름> 봄 > 겨울 > 가을인 경향
2. Instrumentalness는 봄만 특히 높은 경향
3. Acousticness은 여름만 특히 낮은 경향
 

## 3. 서비스 시연
<img width="666" alt="image" src="https://user-images.githubusercontent.com/110436172/228230072-38c4b2bf-63ff-4745-8923-a38d7ff3297b.png">
<img width="676" alt="image" src="https://user-images.githubusercontent.com/110436172/228230166-5732eeeb-31b2-473a-bb4e-740cf951f1c5.png">

