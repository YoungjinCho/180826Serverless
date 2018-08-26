# 180826 Serverless
I attended to Serverless Architecture Lecture called 'Node.js로 시작하는 Serverless Architecture(Start Serverless Architecture with Node.js)'. Some code related to this lecture would be pushed here.

MOVILEST CTO 변규현(Byun Kyuhyun)
잠금화면 해제 앱, 중남미 타겟
개발자가 많지 않아 개발을 혼자 담당하고, 혼자서 개발을 담당하다 보니 서버리스를 도입하게 됌.
Java, Javascript, French, SQL, Kotlin ...

https://github.com/novemberde
https://novemberde.github.io

이번 강의도 위의 자료에 업로드될 예정

0. 목차

2. NoOps란?
  조대영이란 유명한 분께서 이야기한 것?
  Ops = Operations -> NoOps == No Operations
  전혀하지 않는 것은 아니지만 많은 운영/서버의 리소스를 제어해줌.

  DevOps: 프로젝트 단위 팀으로 큰 효율을 보고 있음, JYP Twice 역시 이런 팀.
  
  Quality Assurance & Operation - Apache JMeter: 오늘 쓸 BlazeMeter의 기원.
  
 #FOCUS ON DEVELOPMENT WITH SERVERLESS
 
3. Public Cloud
  Q. AWS를 시작하게 된 배경 - 아마존이 전자 상거래 시장을 장악했고, 트래픽이 늘다 보니 계속 서버를 삼. IDC에다. 그런데 나중에 서버 점검을 해보니 서버PC 사용 효율이 낮고 90% 이상의 서버가 놀고 있음. 그 남는 서버를 어떻게 쓸까 했더니, 서버를 팔자 해서 Public Cloud가 등장함. 첫 서비스는 EC2. 그전엔 국내 cafe24 같은데서 썼는데, 이젠 AWS에서 클릭만하면 VM을 제공해주니 아마존이 장악 해감. 그래서 이 모델을 보고 따라간게 Azure, GCP(Google) 그리고 국내에 KT, Naver 등에서 따라하곤 있지만, 주목받고 있지는 못하는듯.
  
  장점: 죽지 않음. 
  
  리전: 메인 리전은 버지니아. 모든 서비스를 처음으로 제공함.
  
  사용할 것.
  dynamodb - NoSQL
  cloud9 - 환경 통일
  ... 결국 lambda
  
4. Serverless Architecture
  장점/
  DB는 당연히 운영해야하고 올려야 하는거고, 어플리케이션 서버를 관리할 필요가 없다 -> 비즈니스 로직만 정확히
  인프라 확장 고민 x
  서버 설정 및 최적화 시간 소요 x - 자바면 JVM 튜닝을 하기도 하는데, JVM 홀드 스타트 시간이 더 걸려서 추천하지 않음. 도커 기반임.
  개발 기간 동안 과금 거의 x
  타 서비스와의 결합이 용이함 - Firebase Functions와도 바로 엮을 수 있고, Lambda 서비스를 기반으로 PubSub, 알렉사 등 다양한 곳에 활용할 수 있음.
  서버에 Access 할 필요도, 할 수도 없음. 보안 리스크가 줄어듦.
    DNS를 알 순 있지만 (EC2 본체) 포트도 모르고, 접근할 수가 없음.
    
  단점/
  직접 서버를 구축해서, 사용하던 것을 옮기려면 POC()가 철저하게 필요하다.
  백그라운드가 되지 않음. 람다 단위로 잘 죽이고 끝나야함.
  Vender사 마다 서비스에 대한 이해가 필요함. AWS - Lambda, Azure - Function, GCP - Function
  Case별 Debugging 방법 숙지 필요
  기존과 다른 Architecture
  가상 서버보다 비싸지는 시점이 있음.
    >> 다 해결될 예정
    
// 
5. Cloud9 설정하기
  
