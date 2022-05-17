#  other companies's recommendation system

## Naver AiTEMS
[Naver Shopping's rec sys](https://13.209.180.197/blog/274/): Topic Modeling + Embedding(연관도 분석)
  추천 과정
  1. 사용자 선호 정보(클릭, 구매, 찜) → 사용자의 스타일 토픽 분포
  2. ’함께 볼 만한’ 상품 후보들의 스타일 분포를 구함
  (상품의 상세 설명, 상품의 상품명, 상품의 카테고리 정보 : 텍스트 정보 변환 후, 정보들을 합해 하나의 문서로 가정하고 토픽 모델링을 수행)
  3. 이들  간 유사도가 높으면 상품이 더 상위에 랭킹되게 하는 방식 → 사용자의 스타일에 맞는 추천
  
 [Naver Shopping's second rec sys](https://blog.naver.com/naver_search/221086300708):  rec_sys with CNN
 
 ---------------------------------------------------------------------------------------------------------------------------------
 ## Naver Myplace
 
 [Naver Myplace's User-User recommandar](https://devchopin.com/blog/326/): BERT(유저 평점, 좋아요 + 장소 Dong Code + 식당 Category)
   유저의 좋아요 데이터 → 유저의 평균점수보다 높은 점수를 준 장소: 유저의 취향인 장소
   
  유저의 평점, 좋아요 데이터는 결과적으로, 평점 수치를 사용하는게 아니라, ‘유저 취향 장소’ 찾는 용으로 삼는것이다.
  
  유저 취향인 장소에는 장소에 대한 여러 데이터 (토픽 모델링으로 뽑아낸 혹은 여러 방법을 이용한 플레이스의 특징 단어 임베딩)가 있다. 이것을 유저의 ‘취향’이라 보다. 이것을 bert에 학습시키는 것이다.  
  
  새로운 유저의 경우, 가입전 사전에 선호하는 음식, 식당 등등을 선택하라고 하다. 그게 유저의 좋아하는 플레이스 이력이 된다. 

  사용자로 부터
  1. 내 선호 지역 선택
  2. 내 선호 음식 태그 선택
  3. 내 선호 리뷰어 팔로우 선택(리뷰어들은 음식 태그와 위치태그 기반으로 사용자에게 우선순위 보여줌) 

  → 사용자의 (위치, 선호 음식 태그 ) 데이터 확보할 수 있다.
  
 [Naver Myplace's recommandar ML pipeline](https://medium.com/naver-place-dev/naver-g%ED%94%8C%EB%A0%88%EC%9D%B4%EC%8A%A4ai%EA%B0%9C%EB%B0%9C-%EB%B6%80%EC%84%9C%EC%9D%98-ml-pipeline-%EC%9C%A0%EC%A0%80%EC%B6%94%EC%B2%9C-%EA%B3%BC%EC%A0%9C-%EC%82%AC%EB%A1%80-%EC%A4%91%EC%8B%AC%EC%9C%BC%EB%A1%9C-e5a596f80d7)
 
 [Naver rec_sys_bert_DEVIEW](https://deview.kr/2021/sessions/523)
 
 ---------------------------------------------------------------------------------------------------------------------------------
 ## Naver AirSPACE 
 [Naver AirSPACE's place rec_sys](https://blog.naver.com/naver_search/221240314802)
 
 이용자의 현위치, 시간 , 연령, 성별 등 정보 → 그 순간 가장 가볼만한 장소 추천
 
 
 [Naver rec_sys with GNN](https://tv.naver.com/v/23652392/list/753227)
 
 ---------------------------------------------------------------------------------------------------------------------------------
 
 ## Kakao AI Recommander Team
 [Kakao's personal AI rec_sys](https://tech.kakao.com/2021/06/25/kakao-ai-recommendation-01/):TopicModeling + MAB(reinforcement learning, 실시간 최적화)
  추천 과정

  1. 사용자와 아이템 간의 클릭 로그를 기반으로 토픽 모델링을 진행
  2. 사용자와 아이템 각각에 대한 주제 벡터를 계산

   사용자의 주제 벡터는 사용자가 각 주제를 얼마나 선호하는지를 의미, 
   아이템의 주제 벡터는 아이템이 각 주제에 얼마나 속하는지를 의미

  3. 주제별로 MAB를 하나씩 할당

  ex) 사용자와 아이템이 [‘패스트푸드’, ‘제과’, ‘육류’] → 사용자의 주제 벡터가 [0.06, 0.10, 0.84] →  사용자가 육류에 관심이 많음

  mealion 추천 알고리즘으로써 내 평가: 아이디어는 좋으나, 개발 난이도가 높으며, 개발 양이 많이 보인다.
  
   ---------------------------------------------------------------------------------------------------------------------------------
  
  ## idus
  [idus's sequence rec_sys](https://medium.com/idus-tech/bert4rec%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%8B%9C%ED%80%80%EC%8A%A4-%EA%B8%B0%EB%B0%98-%EC%B6%94%EC%B2%9C-%EC%8B%9C%EC%8A%A4%ED%85%9C%EA%B0%9C%EB%B0%9C-7933d8d3a839): bert4rec -> 시퀸스 기반 추천 시스템
  
   ---------------------------------------------------------------------------------------------------------------------------------
   
   ## Daangn Market
   [Daangn Market's feed filtering sys](https://medium.com/daangn/%EB%94%A5%EB%9F%AC%EB%8B%9D%EC%9C%BC%EB%A1%9C-%EB%8F%99%EB%84%A4%EC%83%9D%ED%99%9C-%EA%B2%8C%EC%8B%9C%EA%B8%80-%ED%95%84%ED%84%B0%EB%A7%81%ED%95%98%EA%B8%B0-263cfe4bc58d): bert -> 게시글 필터링
   
   ---------------------------------------------------------------------------------------------------------------------------------
   
   ## Pinterest
   [Pinterest's image rec_sys](https://brunch.co.kr/@andrewhwan/60)
   
  ---------------------------------------------------------------------------------------------------------------------------------
  
  ## Tinder
  [Tinder's Geo-based rec_sys](https://brunch.co.kr/@andrewhwan/58)

  ---------------------------------------------------------------------------------------------------------------------------------
      
   
   ## DingDong (food delivery app company)
   [DingDong's restaurant rec_sys](https://medium.com/honeybees-engineering/%EB%9D%B5%EB%8F%99-%EC%9D%8C%EC%8B%9D-%EC%B6%94%EC%B2%9C-%EC%8B%9C%EC%8A%A4%ED%85%9C-restaurant-recommender-system-6eef4b5de68b) : SVD + complementary work 
    
   보완작업이란? (Funnel approat(정밀도 향상) + Reinterpretation of ratings(반복 주문 가중치 부여) +  Exclusive pool(history없는 고객, 음식점 분리))
