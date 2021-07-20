# Summary
2020년 6월9일부터 9개의 금융공공기관이 보유한 정보를 복합 및 표준화 과정을 통해 가공한 금융공공데이터를 무료로 개방한다. 이 노트는 해당 데이터의 구조와 주요 데이터의 내용을 살펴보고, 카테고리별로 기업 및 개인이 어떤 방향으로 데이터들을 활용 및 가공할 수 있는지 예측해보고 평가해보기 위해 작성되었다.
***
# Detailed Explanation

## Background
최근 코로나19 관련 사례(코로나맵, 마스크알리미 개발 사례 등)와 같이 공공데이터는 국민 실생활에 활용 가능한 높은 가치를 가졌으나, 금융부문 데이터는 보수적인 업무 관행 등으로 개방이 부진한 상황이었다. 이를 해결하고자 2019년 7월부터 금융위원회 주도로 9개 금융공공기관이 참여하여 시작되었으며, 약 9개월간 개발과정을 통해 2020년 4월부터 시범서비스를 시작하였다. 데이터는 5개의 핵심 분야 테마정보
-통합기업정보
-통합금융회사정보
-통합공시정보 
-통합자본시장정보
-통합국가자산공매정보
로 구성되어 있으며 총 50개 서비스, 5500개 항목, 4450만건의 데이터로 이루어져 있다.

## Why is this research important to pursue?

금융 공공데이터를 통해 얻을 수 있는 다양한 이점들은
-	금융 공공기관이 제공하는 것보다 객관적이고 정확한 정보 획득이 가능해진다.
-	개별적으로 확인해야 했던 정보를 한 번에 확인 가능하다 
-	금융 회사의 경영안정성에 대해 확인해볼 수 있다. 
-	기업분석제공 서비스 및 개발이 가능해진다.

등을 들 수 있으며, 특히 투자자/학계,연구기관,민간 사업부문/정부 위 세 집단에게 매우 유용하게 활용될 수 있는데, 그 이유들은 다음과 같다.
-	투자자
투자 시 떠안았던 불확실성 관련 리스크를 감소시킬 수 있고 보다 나은 선택을 할 가능성을 증가시킨다
-	학계,연구기관,민간 사업 부문
보다 정확한 결과 도출이 가능하며 새로운 시장을 개척하는 성과 가능성이 증가한다
-	정부
금융 정책을 세울 때 활용하여 보다 현실적이고 즉각적인 대책 마련이 가능해진다.
***

# What do we want to achieve through this research? 

금융공공데이터를 포함한 마이데이터들의 종류에 대해 알아보고 특정 정보를 활용하여 금융업체 및 핀테크 업체에서 이를 활용할 수 있는 방안 및 원리에 대해 분석하여 보고 이 research의 본 목적이었지만 보안을 이유로 많은 정보를 얻기 힘든 ‘금융권 및 핀테크 업체의 자산관리어플의 원리 및 서비스 제공방식’의 원리를 예상해보기 위해 진행하였다. 
***
# How to achieve ? 

  활용하고자 하는 데이터로는 통합 공시에 해당하는 기업의 재무제표와 금리를 선택하였다. 그 이유는
-	구체적인 주식종목 추천의 가능성
-	저축 권유 등 구체적인 투자방안 제시 서비스 개발 자의 활용도

를 근거로 금융 상품 추천 및 서비스 제공에 필수적인 정보라 여겨졌기 때문이다. 
데이터를 활용하여 금융 상품 추천을 위한 데이터 모델링 과정에 대한 예시 및 재무제표 분석 기법들은 아래의 reference에 기재된 논문들을 참고하였다.
***

## 재무제표 및 금리를 통한 주가 및 파산 예측

### 주가예측

   주가 예측 방법은 기계학습을 기반으로 하고 있으며  SVM(support vector machine)의 입력으로 사용하여 기본적 분석, 즉 기업의 내재 가치를 나타내는 재무 정보에 따른 분석을 하고 이 결과로 주식의 향후 등락을 예측하거나
   + 데이터 전처리 방법
   + 유전자 알고리즘
   + FNN학습을 위한 LM 알고리즘
  
   의 조합으로 이루어진 Hybrid intelligent model 등이 매우 효과적이며 
   + 주당순이익(EPS)
   + 주당순자산(BPS)
   + 순이익증가율(NPGR)
   
   을 중점적으로 분석하면 주식 종목 추천에 활용될 유용한 정보들을 예측해낼 수 있을 것이다. 
   
   기계학습 기법에 기반을 둔 방법들은
   + 다차원 공간에 복잡한 비선형 분류를 할 수 있다.
   + 다양한 실험적 시도가 가능하다 
   + 효율적 시장가설의 실증 분석을 위한 사건 연구로서 기업의 재무 정보 발표를 사건으로 본다
   
   는 점들과 그로 인한 주식 가격 등락을 예측한다는 것에 주목할 가치가 있다.
   
### 파산예측
   
   또한, 통합공시의 재무제표를 활용하여 기계 학습을 바탕으로 한 기업 파산 예측도 가능해진다. 기계 학습의 대표적 응용 분야인 패턴 인식을 기업의 파산 예측에 응용한 것이다. 기업의 재무 정보를 바탕으로 패턴을 작성하고 이 패턴이 파산 위험 군에 속하는지 안전한 군에 속하는지 판단하는 것이다.
   기계학습은 
   + 비선형적인 관계를 추론할 수 있다.
   + 통계적 방법에 비해 복잡한 유추가 가능하다.
   
  는 특성들이 있으며,  예측모형 생성을 위한 입력변수를 분석하면 파산 유발 조건에 대해 많은 지식을 얻을 수 있다. 
  실제로 파산 예측에 사용되는 대표적인 기계 학습으로는 
  + 인공 신경망(Artificial Neural Networks)
  + 적응형 부스팅(AdaBoost)
  + SVM(Support Vector Machine)
  들이 있으며 이 기법들을 모두 결합한 하이브리드 연구도 다양하게 진행 중이다. 
  
  위에서 분석들에서 얻은 정보들을 분석 및 종합하는 과정을 거친다면 구체적인 주식 종목을 추천하는 알고리즘을 구현해낼 수 있을 것이라 생각한다.
  
  
  또한 통합공시의 재무제표에 국한되지 않고, 금융회사의 데이터베이스에 저장되어있는 고객의 평소 소비습관, 투자습관 등을 위와 같은 분석법을 통해 패턴을 도출해내고 이를 종합하는 모델링 과정을 거친다면 고객의 성향에 따른 금융 상품 추천 서비스를 개발하는 원리를 도출해낼 수 있을 것이라 생각한다.
  ***
  
  # How to modeling? 
  
  ## 1.Sampling
   위 part에 사용되는 그림 및 내용들은 <김석수. "금융 상품 추천에 관련된 빅 데이터 활용을 위한 개발 방법." 한국컴퓨터정보학회논문지  19.8 (2014): 73-81.>를 참조 및 인용하였다.
   먼저 데이터베이스에서 필요한 정보들을 추출해내는 샘플링의 과정을 거쳐야한다.
  ![category별로 sampling된 데이터](https://user-images.githubusercontent.com/77109803/126346699-67171398-f52c-4947-b665-fce60529d8df.png)
  
  위 그림은 category별로 샘플링된 데이터들을 나타낸다. 
  
  ## 2.Exploration
    
   ANOVA 분석 및 기본적인 데이터 시각화를 통해 데이터의 속성을 파악한다. 서로 간의 영향도를 조사하기 위해 상관성 분석을 실행한다.
   상관성이 높다면
   + 각각 변수 간에 서로 간에 어떠한 영향을 주고받는지에 대한 개략적인 정보를 얻을 수 있다.
   + 새로운 정보를 발견할 수 있다.
   + 고객의 성향을 분명히 나누는 요소를 발견할 수 있다.
  
   는 장점들이 있다. 
   
   ![Exploration](https://user-images.githubusercontent.com/77109803/126347991-cd1bf034-b973-4291-b1e8-73533de1843e.png)
   
   
  ## 3.Modification
  
   분석할 데이터를 선택하고, 파생변수를 생성한다. 
   
   ![Modification](https://user-images.githubusercontent.com/77109803/126349249-42313497-6c94-470b-914e-a9dde9c2bbce.png)


   위 그림의 검은색 상자로 표시 된 부분이 파생변수이며 결과해석이 용이하도록 일정한 수식에 의해 생성 및 분석한다. 파생변수들 또한 기초적인 분포분석 및 상관성 분석을 진행한다.
   ***
   
  ## 4.Modeling
   분석된 결과에 다양한 모델을 적용하였다. K-Means 알고리즘을 사용할 경우, 군집의 개수와 특성에 큰 영향을 미친다. K에 따른 Sum of squares는 군집끼   리의 Centroid가 서로 얼마나 떨어져 있는지를 보여주는 값이다. 군집의 개수를 늘렸을 때, Centroid가 일정 이상 가까워지거나, 갑자기 가까워지는 변곡점이 있는 경우의 군집 개수를 활용하는 것이 가장 합리적이라 판단한다. 이를 활용해 Recommendation(Collaborative Filtering) 알고리즘을 사용하여 고객별 맞춤 상품을 추천한다. 
  
   ![Modeling](https://user-images.githubusercontent.com/77109803/126352512-476c302f-5033-48e8-b394-459f4490a84d.png)
   ***
   
  ## 5. Assessment 
   Cluster간의 유의미한 변수에 대하여 대립되는 Cluster간의 귀무가설을 토대로 T-검정을 시행한다. 이때 각각의 군집들을 비지니스 적으로 재정의 하고 특성을 Profiling하는 것이 매우 중요하다. 
   각각의 군집을 파생변수 및 일정기준에 따라
   + 핵심 고객군
   + 관리 사각지대 고객군
   + 장려 고객군
 으로 재 정의하고, 해당 군집의 대표적 특성을 T-검정을 통해 검증한다. T-Test를 통해 P-value가 0.05미만으로 나온다면 해당 귀무가설을 채택하여 분석결과가 의미가 있었음을 증명한다. 
 
 ![Assessment](https://user-images.githubusercontent.com/77109803/126355239-5a1a4893-c858-4290-8ef5-dbc80415b1e0.png)
 
 고객의 특성에 따른 군집분류 및 모델링 과정을 거친다면, 고객에게 맞는 금융상품을 추천해줄 수 있을 뿐만 아니라 향후 특정 군집에 속한 고객층들에게 필요한 접근법이나 서비스 등을 미리 강구하고 보강할 수 있는 경쟁력을 기업에게 가져다줄 수 있을 것으로 기대한다. 
 ***

  # Expectations
  
  금융공공데이터의 개방은 위에서 다룬 금융서비스로써의 활용도 뿐만 아니라 여러 방면에서의 활용도를 지니고 있다. 
  
  신용정보업체
  
  + 체계적으로 정리되어있는 금융 공공데이터를 활용하여 신용정보업체가 보유한 데이터와 정합성 확인
  + 기존 및 신규 데이터와 융복합을 통해 새로운 분석모델 개발 등 시너지효과 

  핀테크업체
  
  + 통합기업정보,통합공시정보 등을 통해 기업 재무현황 파악 및 서비스 개발
  + 유로로 제공된 CB 데이터 대신 금융 공공데이터를 적극 활용 가능 
 
  연구기관
 
  + 기업자금조달 비용 관련 연구에 활용 예정
  + 금융기관 통계정보, 공시정보 등 필요한 정보 취득 예정

  위 내용처럼, 금융공공데이터는 금융사뿐만 아니라 여러 분야 및 기관에서 활용도가 매우 높을 것으로 전망된다. 빅데이터 및 마이데이터의 중요성이 나날이 커져가는 현 시대에서, 금융공공데이터는 도태되지 않기 위해 필수적으로 사용될 데이터로 자리 잡게 될 예정이다. 
  
  ***

# Reference

1.양진용. "기업 재무 정보를 활용한 머신 러닝 기반 경영 예측 시스템." 국내박사학위논문 한성대학교, 2017. 서울

2.허준영, & 양진용. (2015). SVM 기반의 재무 정보를 이용한 주가 예측. 정보과학회 컴퓨팅의 실제 논문지, 21(3), 167-172.

2.김석수. "금융 상품 추천에 관련된 빅 데이터 활용을 위한 개발 방법." 한국컴퓨터정보학회논문지  19.8 (2014): 73-81.

3.이동은, 이건창. (2021). 비지도 기계학습 기법과 베이지안 네트워크를 결합한 확률구조방정식 모형(PSEM)을 이용한 국내 1인 창조기업 당기순이익 영향요인 분석에 관한 실증연구 . Information Systems Review, 23(2), 49-66.이동은, 이건창. (2021). 비지도 기계학습 기법과 베이지안 네트워크를 결합한 확률구조방정식 모형(PSEM)을 이용한 국내 1인 창조기업 당기순이익 영향요인 분석에 관한 실증연구 . Information Systems Review, 23(2), 49-66.



 
  
  
  


