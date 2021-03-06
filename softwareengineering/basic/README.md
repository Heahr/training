## Software Engineering Basic

##### 

[뒤로가기](/softwareengineering/README.md)

일반적으로 소프트웨어 개발 프로세스는 계획, 요구분석, 설계, 구현, 테스트, 유지보수 6단계로 구성되어 있다.  

---

#### 계획  

**1단계 계획**에서는 COCOMO모델과 기능점수(FP)모델을 사용하여 비용을 산정하고, 작업분할구조도(WBS), CPM을 사용하여 일정을 계획하며 위험을 방지하는 위험 관리가 진행된다.  

#### 요구분석  

**2단계 요구분석**에서는 기존 시스템이 존재할 경우에는 기존 시스템의 문제점을 파악해 새로운 요구사항을 도출해 다이어그램을 작성한다.  

이 경우에는 실행에 앞서 구현 가능성, 일정에 대한 조율이 필요하다(무조건 진행하면 잘못될 수 있다). 마지막에 언급한 다이어그램은 '비 개발자'를 대상으로 설명할 때 사용된다.  

이 단계에서는 구조적 방법론(DFD, DD, Mini Spec) 정보공학 방법론(ER-D), 객체지향 방법론(UML의 유스케이스 다이어그램) 등을 활용해 최종 산출물인 요구 분석 명세서를 작성한다. 각 방법론은 이후에 자세하게 설명하도록 하겠다.  

#### 설계

**3단계 설계**에서는 분할과 정복, 추상화, 단계적 분해, 모듈화, 정보은닉 등의 설계 원리를 고려해 소프트웨어 아키텍처, 객체지향을 설계한다. 아키텍처 스타일을 조정하고, GoF의 디자인 패턴을 사용한다.

> 객체지향 설계는 분석을 하면서 설계를 같이한다.  

GoF는 "어떤 프로그램은 어떤 클래스가 필요하고, 어떤 모양으로 만들어지더라"와 같은 패턴을 가지고 설계를 진행하는 것이다. 예를 들어 이런 프로그램을 만들기 위해서는 유사한 패턴을 이용한다고 생각하면 좋다.  

모듈을 평가할 때에는 응집도와 결합도를 고려한다.  

> 예를 들어, 한 모듈 안에 기능들을 넣는 것이 좋아 응집도는 높을 수록 좋고, 모듈과의 관계는 적을 수록 좋아 결합도는 낮을 수록 좋다는 것이다.  

#### 구현  

**4단계 구현**에서는 표준 코딩 규칙을 고려해 구현을 진행한다. 이 단계에서는 소프트웨어 공학적인 내용이 적은 부분이다.  

#### 테스트  

**5단계의 테스트**에서는 테스트의 절차를 정하고, 아래 4가지 분류에 따라 테스트를 진행한다.  

1. 개발자 또는 사용자 시각에 따른 분류 - 베타 테스트와 알파 테스트  
2. 사용되는 목적에 따른 분류  
3. 품질 특성에 따른 분류  
4. 소프트웨어 개발 단계에 따른 분류    

#### 유지보수

마지막으로 **6단계 유지보수**가 4가지 형태로 진행된다.  

1. 수정 유지보수  
2. 적응 유지보수  
3. 기능보강 유지보수  
4. 예방 유지보수  

## 소프트웨어 개발 프로세스  

추가적으로 소프트웨어 개발 프로세스에 대해 간단하게 소개하자면 아래와 같은 모델들이 존재한다.  

1. 주먹구구식 개발 모델  
2. 선형순차적 모델(폭포수 모델)  
3. V 모델  
4. 진화적 프로세스 모델(프로토타입 모델)  
5. 나선형 모델  
6. 단계적 개발 모델  
7. 통합 프로세스 모델(UP)  
8. 애자일 프로세스 모델  
  
품질 관리 부분에서는 ISO/IEC에서 제정한 여러 모델이 존재한다. 이에 대해서는 알고만 넘어가도록 하자.  

> 마지막으로 프로젝트 관리는 형상 관리가 진행되고, PMBOK의 9가지 관계에 대해 고려되어야 한다.  

