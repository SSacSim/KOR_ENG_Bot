## KOR-ENG Bot(코잉봇)

주최/주관 : 제주 테크노파크, 제주특별자치도 / 데이콘

진행 기간 : 2022.05.02 ~ 2022.06.07
팀 구성  : 5명

프로젝트 설명:
  * 
  
프로젝트 진행 배경:
  * ‘한국 교육 통계 서비스’에 따르면, 초등학생에게 월별 영어 사교육비의 부담이 가장 높은 걸로 파악.
  * 영어 사교육 부담이 가장 높다는 의미 > 어릴때부터 영어를 자연럽게 접할 수 있는 환경을 얻기위해 사교육비 지불.
  * 자녀가 영어에 익숙해지길 원하는 부모들의 수요를 충족시켜 줄 수 있는 챗봇을 만들어 서비스 제공.
  
제공 서비스 :
  * 자녀가 영어에 익숙해지길 원하는 부모들의 수요를 충족시켜 줄 수 있는 챗봇을 만들어 서비스 제공.
  * 아이와 챗봇의 대화 내용을 바탕으로 부모에게 아이 대화 내역을 요약해주는 서비스를 제공하여 아이 케어에 도움을 주는 서비스
  * 아이의 대화 내용을 이용하여 아이의 감정상태를 분류하여 부모에게 알려주는 서비스
 * * *
 ## 대회 진행 환경 & 역할
 프로젝트 진행 환경 : Google Colab, Visual_Studio, AWS, React_Native, django ...
 
 역할 :
  * 모델 구축
    * 대화 생성에 필요한 데이터 전처리
    * Bart, Bert 모델 Pipline 구축 및 Transfer Learning 진행
    * mimic studio를 이용한 음성 데이터 수집 ( pyautogui을 이용한 자동화 )
    * Glow-TTS , HiFi-Gan을 사용한 TTS 학습 진행
* * *
## 진행 상세 과정
1.데이터 전처리
  * AI 허브의 데이터는 성인 대화 내용 > 아이에게 불필요한 단어가 있는 것을 확인하여 제거
  
2.생성 모델링 (대화 생성 & 대화 요약)
  * Pre-Trained 된 KoBart 모델을 이용하여 전처리한 데이터를 Transfer-learning을 통해 보다 아이에게 적합한 응답을 할 수 있도록 학습 
  * 대화 생성, 요약 2개를 모델을 같은 KoBart모델로 제작 ( 학습 데이터만 상이 )

3.분류 모델링 ( 감정 분류 )
  * 네이버 영화 평가 데이터로 학습된 KoBert를 베이스로 Transfer-learning을 진행하여 대화를 6가지 감정으로 분류
  
4.TTS 모델링 ( 음성 ) 
  * 특정 목소리(한글) 수집
  * Glow-TTS + HiFi-GAN을 통해 TTS 학습

5. 앱 서비스
  * React-Native을 이용하여 Front 구성
  * Model 예측을 API화 시켜 서버 배포
  * 아이의 정보 / 대화내용 RDS 구축
