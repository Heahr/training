## Entity and Cardinality  

##### 

[뒤로가기](/database/README.md)

이번 장에서는 엔터티에 대한 전반적인 설명과 카디널리티에 대한 설명이 진행될 것이다. 전반적으로 풀어 설명할 것이니 다소 지루할 수 있다.

---

엔터티는 하나의 명사이다. 예를 들어 "우리 회사에는 여러 명의 직원들이 근무한다."라는 명제에서 명사는 '회사'와 '직원'이며, 이는 엔터티가 될 가능성이 있다. 자세한 사항은 아래를 참고하자.  

#### 엔터티 타입 선정 방법  

1. 업무기술서, 장표, 인터뷰 정리문서 등에서 명사를 구분한다.  
2. 개념이 불분명한 것, 광범위한 것은 제거한다.  
3. 엔터티타입의 특성이거나 속성의 값은 제거한다.  
4. 포괄적인 업무 프로세스에 해당되는 명사는 제거한다.  
5. 중복되는 명사는 제거한다.  
6. 누락된  엔터티타입이 존재하는지 유추해 본다.  

위에서 설명한 선정을 활용한 구체적인 엔터티타입의 도출 방법의 과정은 아래와 같다. 아래의 과정을 진행하며 직접 구분하거나 제거해보자.    

##### 시나리오에서 명사를 구분한다.  

인터넷경매, IAuctionCo, 회사, 경매, 물품, 내용, 온라인, 입찰, 접수, 날짜, 경매공고일, 인터넷, 경매공고, 입찰인, 매수신청, 최고가, 신청, 매수신청인, 낙찰, 낙찰일, 1주일, 낙찰대금, 은행계좌, 카드, 직접납부, 자동, 취소, 차순위금액, 낙찰인, 대금납부, 경매성사, 입금, 물품가격, 2%, 수수료, 경매일, 진행, 결과.  

> 여기에 있는 37개의 명사가 모두 엔터티타입이 될 수 있는지 계속해서 작업을 진행한다.

##### 개념이 불분명한 것, 광범위한 것은 제거한다.  

인터넷경매, IAuctionCo, 회사, 경매, 물품, 내용, 온라인, 입찰, 접수, 날짜, 경매공고일, 인터넷, 경매공고, 입찰인,  매수신청, 최고가, 신청, 매수신청인, 낙찰, 낙찰일, 1주일, 낙찰대금, 은행계좌, 카드, 직접납부, 자동, 취소, 차순위금액, 낙찰인, 대금납부, 경매성사, 입금, 물품가격, 2%, 수수료, 경매일, 진행, 결과  

##### 엔터티타입의 특성이거나 속성의 값은 제거한다.  

물품, 온라인, 입찰, 접수, 날짜, 경매공고일, 경매공고, 입찰인, 매수신청, 최고가, 신청, 매수신청인, 낙찰, 낙찰일,  1주일, 낙찰대금, 은행계좌, 카드, 직접납부, 자동, 취소, 차순위금액, 낙찰인, 대금납부, 경매성사, 입금, 물품가격,  2%, 수수료, 경매일, 진행, 결과  

##### 포괄적인 업무 프로세스에 해당되는 명사는 제거한다.  

물품, 온라인, 입찰, 접수, 경매공고, 입찰인, 매수신청, 신청, 매수신청인, 낙찰, 자동, 취소, 낙찰인, 대금납부, 경매성사, 입금, 진행, 결과  

##### 중복되는 명사는 제거한다.  

물품, 입찰, 접수, 경매공고, 입찰인, 매수신청, 신청, 매수신청인, 낙찰, 낙찰인, 진행  

> 매수신청인 입찰인과 동일한 의미를 가지므로 업무에서 자주 사용하는 입찰인을 남기고 매수신청인은 제거한다.  
>
> 매수신청과 신청은 같은 의미를 가지고 있으므로 매수신청을 남기고 신청을 제거한다. 

##### 누락된 엔터티타입정보를 유추한다.  

물품, 입찰, 접수, 경매공고, 입찰인, 매수신청, 낙찰, 낙찰인, 진행, 경매물품  

> 특정날짜에 어느 물품을 경매에 내놓을 것인지 분명히 업무에 핵심적인 사안이지만 위 시나리오에는 명사화 되어 있지 않다. 이러한 경우는 업무를 예상하여 경매물품이라는 엔터티타입을 유추할 수있다.  
>
> 이 시나리오에서 분석된 엔터티타입의 최종 후보는 물품, 입찰, 접수, 경매공고, 입찰인, 매수신청, 낙찰, 낙찰인, 진행, 경매물품 이다.  

이러한 선정과 도출을 이용해 결과적으로 엔터티타입 정의서를 작성하고, 이 정의서에 따라 ER-D를 그릴 수 있다.  

이후에는 엔터티타입 정의서와 ER-D를 가지고 엔터티타입의 관계를 정의할 수 있다.  

관계를 정의하는 과정은 아래와 같다.  

1. 업무기술서, 장표, 인터뷰 정리문서 등에서 동사를 구분한다.  
2. 도출된 엔터티타입과 관계를 이용하여 관계정의서를 작성하도록 한다.  
3. 고객에게 질문하여 관계에 대해 더 세분화하고 정확하게 도출하는 작업을 한다.  
4. 데이터모델링 툴(TOOL)이나 칠판, 포스트잇을 이용하여 직접 모델을 그려본다.  
5. 고객과 질문하고 협의하여 모델을 검토하는 시간을 갖는다.  

이후에는 정의된 관계를 가지고, 관계 정의서를 작성할 수 있다.  

데이터베이스에서 이러한 엔터티타입 정의서와 관계 정의서는 필수적이다. 정의서가 없는 ER-D는 존재할 수 없기 때문이다.  

추가적으로 엔터티들의 구분에 대해 설명하면, '키 엔터티'는 부모 엔터티가 존재하지 않는다. 행위가 일어나는 부분이 '메인 엔터티'가 된다. 마지막으로 '엑션 엔터티'는 이력, 이력을 관리하는 부분이다.  

#### 카디널리티  

카디널리티는 1:1, 1:M, M:N의 3가지 형태로 나타낼 수 있다.  

##### 1:1 관계

1:1의 경우에는 예를 들어 10,000명의 사원이 있는 회사가 있다. 이 중에는 계약직도 존재하고, 계약직은 계약 정보에 따라 임금이 달라지게 된다.  

따라서 일반 정직원이 아닌 계약직만을 위한 계약 정보를 속성으로 추가시켜야 한다. 그런데 예를들어 계약직 200명을 위해 정규직 9800명이 계약 정보를 가지게 된다면, 필요없는 정보를 가지고 있는 것이다.  

이건 null값을 허용해, 빈 데이터를 많이 가지고 있어야 하므로, 데이터의 정확성이 떨어질 수 있다.  

이럴 경우에 1:1관계로 정규 사원과 계약 사원을 묶어, 두 집단을 따로 관리할 수 있다. 이러한 1:1 관계는 잘 일어나지 않는다. 왜냐하면 1:1관계의 두 집단을 하나로 묶을 수 있는 개념이기 때문이다.

##### 1:M 관계  

1:M 관계를 이야기하자면, 한 부서와 직원들 사이의 관계이다. 가장 흔한 관계이고, 대부분 1:M 관계를 지닌다.  

> 예를 들어 "한 명의 사원은 하나의 부서에만 소속된다."라고 이해하면 된다. 이때 관계 정의서는 주는 쪽과 받는 쪽, 두 줄이 필요하다.  

각 관계는 참여 방법이라는 단어로 '필수관계'와 '선택관계'로 나뉜다.  

> 예를 들어 '각각의 사원은 한 부서에 속한다.'는 필수 참여 방법이고, '각 부서에는 여러 명의 사원이 존재할 수 있다.'는 선택 참여 방법이다.  

더불어 관계는 바커 표기법에서는 다음과 같이 관계를 선으로 표현한다.  

각 관계는 `----0-`, `----|-`, `----<-` 의 세 형태로 표기한다.  

첫 번째의 경우는 '선택'에 해당하고, 두 번째 경우는 필수, 세 번째의 경우에는 1:M 관계를 의미한다.  

위에서 언급한 예제에서는 부서와 사원의 관계는  

```
(부서)-|----0|<-(사원) 
```
  
이다(부서는 무조건 존재해야하고, 사원은 없을 수도 있고, 한 명만 있을 수도, 여러 명의 사원이 있을 수 있기 때문이다).  

> 또, 실선의 경우 '반드시 가져야 한다'를 의미하고, 점선의 경우는 '가질 수도 있다'를 나타낸다.  

모든 사원은 반드시 한 부서에 소속되어야 한다(이는 실선으로 표기하며, 사원 엔터티는 부서 번호를 식별자(FK)로 가지고 있어야 한다).  

이것이 엔터티 무결성이다. 이때 어떤 사원은 어떤 부서인지 식별할 수 없어 식별자를 두지 않는 경우에는 점서으로 표현한다.  

> 추가적으로 부서는 '부서번호'를 키 값으로 가지고, 사원은 '사원번호'를 키 값으로 가진다.
>
> 정보 공학 표기법에서는 '|'가 존재하면, 상속 관계에 있다는 것이다. 각 엔터티의 필수 속성은 '#', 선택 속성은 '0'으로 표기한다.  

##### M:N 관계  

일반적으로 M:N은 개념 모델에서만 존재한다. 이것이 논리 모델로 가면 행위에 대한 엔터티가 생성되어 각 엔터티와 행위에 대한 엔터티가 1:M 관계로 바뀌게 된다.  

예를 들어 '고객 `>-<` 상품'의 경우는 M:N 관계지만, 논리 모델에서 '고객 `-<` 주문 `>-` 상품'이 될 것이다.  

관계형 데이터베이스의 가장 강력한 기능은 '관계(Reltion) 연산'이다. Releation 사이의 연산(Union, Intersection 등)을 수행하면 새로운 Relation이 생긴다. 이를 수학적으로 ['닫힘'성질][닫힘]을 만족한다.  

실제 DB에서는 물리적으로 따로 관리하는 것처럼 존재한다. 논리적으로는 하나의 테이블처럼 운용할 수 있다. 이를 ['결합 구문(Join)'][조인]이라 한다. 예를 들어 고객명과 배송지 주소를 검색하려고 할 때, 둘은 다른 테이블(고객, 배송지 테이블)에 존재하기 때문에 이 둘의 엔터티 사이에 Join을 수행하는 것이다.
  

```
Select 고객명, 배송지주소
from 고객, 배송지
where 고객.고객번호 = 배송지.배송지번호
```
  
이는 해당 고객의 배송지주소를 보여준다. 이 과정에서 DBMS의 매개 역할을 하는 것이 'foreign key'이다.  

물론 이는 가벼운 DB에서는 필요 없지만, 크기가 큰 DB에서는 아주 유용하게 사용된다. 이러한 연산자는 아래의 그림을 참고하자.  

![realtion_op](https://raw.githubusercontent.com/rjs1197/rjs1197.github.io/master/img/database_programming/relation_op.jpg)
  

이러한 연산자의 사용은 '분할(divide)'된 DB에서 유용하다. 또한, DB의 분할은 관리가 유용하고, 확장성이 높으며, 무결성이 보장된다.  

> 추가적으로, 바커 표기법의 모델링은 엔터티 속에 수퍼타입과 서브타입이 들어가고, 수퍼 타입은 일반적으로 작성되고, 서브타입은 따로 관리된다(DA#에서의 형태).  

```
슈퍼타입 = 서브타입1 ∪ 서브타입2
서브타입1 ∩ 서브타입2 = ø
```
  
DB 테이블의 관리에서 테이블의 갯수는 상황과 요구에 따라 다르게 관리될 수 있다.  

> 예를 들어 고객이라는 엔터티가 존재하고, 개인고객과 법인고객으로 나뉠 때, 하나의 고객 테이블로 관리할 수도 있다.  
>
> 또한, 두 개의 개인고객과 법인고객으로 테이블을 관리할 수도 있고, 세 개인 고객, 개인고객, 법인고객 테이블로 관리할 수 있다.  

이는 정합성과 성능의 차이에 따라 일장일단을 지닌다.  

즉, 하나의 테이블로 관리하면 성능이 높고, 세 개의 테이블로 관리하면 성능을 떨어지나, 정합성이 높은 것이다(실무 대부분의 경우 정합성이 떨어지더라도 성능이 높은 적은 테이블로 관리하고 있다).    

[닫힘]: http://www.ktword.co.kr/abbr_view.php?m_temp1=5001
[조인]: https://ko.wikipedia.org/wiki/Join_(SQL)