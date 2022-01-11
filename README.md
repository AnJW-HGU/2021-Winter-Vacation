# 2021-Winter-Vacation
2021년도 동계방학 인턴십 기록

_Even tried, Even failed, No matter._  
_Try again._  
_Fail again._  
_Fail better._  

---

1 week
* GetX
* Freezed
* Json serialize
* Shared Preferences
* Get Storage
* Hive
* Local Notification
* Cloud Messaging

<!--
BLoc에 대해서 더 공부해봐야할 필요성
다수의 개발자가 함께 개발하기에 좋음. UI개발은 UI만, 데이터? 로직? 건들기 전에 완전히 차단 가능.

로컬에 데이터를 저장...?!
Android와 iOS 세팅
Xcode로 먼저 빌드해 준 다음 안스 run
-->

---

2 week  
* Cloud Function
* [FCM] Scheduling / Periodic 연구
* [FCM] Advanced Navigation 연구 (Holding)

<!--
> fluttet의 한계<br>
Background Notification Scheduling을 공부하면서 Local Notification과 다른 패키지만 사용하는 조건으로 내용이 바뀌는 periodic을 구현하려고 했다. Android는 Workmanager나 background fetch로 충분히 구현이 가능했지만, iOS는 아직 제대로 지원하지 못했다. 결국 iOS는 네이티브 개발로 구현이 가능하다는 결론이 나왔다. 이전까지는 크로스 플랫폼 프레임워크로 빠르게 모든 것이 개발가능하다고 생각했었는데, 이때 한계를 본 것 같았다. 크로스 플랫폼 프레임워크가 하나 둘씩 나오는 와중에 네이티브 앱 개발이 계속해서 있는 이유에 대해서 말이다. 이 결과로 Cloud Scheduler 없이 Cloud Function을 트리거 하는 방법도 아직 없는 것으로 결론지어졌다. 네이티브에서 기능이 하나 만들어지면 크로스 플랫폼 개발자들이 만들어 줄 때까지 기다려야한다는 것이 이런 거였다는 걸 몸소 체험할 수 있었다...

> Stack, URL<br>
앱은 항상 스택으로 생각했었다. 푸시 알림을 클릭했을 때, page1?p1=title2/page2?p2=title3/page3으로 가야했다. 스택으로 쌓기 위해 많은 고민을 했었고, GetX의 middleware를 사용했었는데 결국 Get.to를 두 번 쓰는 꼴이었다. 90퍼센트 완성도로 구현은 가능했으나 코드만 봐도 뭔가 잘못된 느낌이 느껴졌다. 그래서 스택의 한계, URL 접근의 필요성을 느꼈다. 1에서 3으로 건너뛸 때 스택은 1, 2, 3을 다 쌓아야하지만 URL은 3에서 parsing만 해주면 되기 때문이다. 물론 이 task에서 듣는 사람들 중에서는 굳이 그렇게까지 해야하나?라는 생각을 할 수 있다. 하지만 지난 여름방학 프로젝트를 하면서 Get.offAll을 써서 이런 방식을 구현했는데 루트가 다 꼬여버리는 느낌이었다. 어떤 부분만 offAll을 하기엔 이전 스택까지 다 지워지기 때문에 모든 푸시를 offAll로 해야하는... 현재는 holinga 했지만 Nested GetPage와 GetMaterialApp.route (URLParsing, routeDelegate?)을 활용해볼 예정이다.
-->

---

3 week  
* Cloud Run (Cloud Code)
* Dart Pad
* Dart Services
* Custom Dart Pad

<!--
도커...? 쿠버네티스...? 컨테이너...? -> Go language [https://www.s-core.co.kr/insight/view/%EB%AC%BC%EC%96%B4%EB%B3%B4%EB%8A%94-%EC%82%AC%EB%9E%8C%EC%9D%B4-%EB%A7%8E%EC%95%84%EC%84%9C-%EC%A0%95%EB%A6%AC%ED%96%88%EC%8A%B5%EB%8B%88%EB%8B%A4-go%EC%96%B8%EC%96%B4/]
Cloud Run으로 서비스(서비스>revision) 제공, 웹 호스팅 가능

dart pad
dart service (분석, 컴파일)

custom dart pad = dart pad의 포트 <- dart service 포트 일치
-->

<!--
SCRUM
안녕하세요, HEM 인턴 안지원입니다.
크게 Cloud Run과 Dart Pad, Dart Service로 나누어 3주차를 진행하였습니다.
지금부터 간단한 예제와 함께 이 세 가지가 무엇인지, 그리고 어떤 관계가 있는지에 대해서 말씀드리고,
4주차 계획을 언급하며 마무리하겠습니다. 

Dart Pad란 SDK나 IDE 설치 없이도 Dart 또는 Flutter 코드를 Web browser 환경에서 실행할 수 있는 무료 오픈소스 온라인 에디터입니다. 하지만 Dart Pad는 기존에 추가되어있는 라이브러리나 패키지 외에 자신이 따로 또 추가를 할 수 없습니다. 
그래서 Custom Dart Pad를 구현하려고 합니다. 

우선 Dart Pad와 Dart Services의 관계에 대해서 설명드리겠습니다. 
Dart Pad는 Dart Services를 사용하여 작동합니다.
이 영상은 local로 이 두 가지를 연결해본 것입니다. 
Dart Pad로 작성된 코드는 컴파일을 위해 Dart Services로 text로 전송됩니다. 
Dart Services는 이를 컴파일 한 후, Dart Pad로 javascript를 반환합니다.
Dart Pad는 이를 렌더링하여 결과를 화면에 보여줍니다. 

만약 여기서 제공되는 패키지가 아닌 다른 패키지를 사용하게 되면 이렇게 지원하지 않는 것이라고 합니다.
이는 dart-services의 파일을 수정하여 dependency를 추가해주면 해당 패키지를 사용할 수 있게 됩니다. 
이렇게 패키지를 추가하려면 기존의 코드를 수정하고 이를 서비스할 수 있어야 합니다.

그래서 저희는 Cloud Run를 사용하기로 했습니다.
Cloud Run이란 요청 또는 이벤트를 통해 호출 가능한 컨테이너를 실행할 수 있게 해 주는 관리형 컴퓨팅 플랫폼입니다.
컨테이너 기반으로 서비스를 제공해주는 서버리스 서비스로, 
Dart Services를 Cloud Run으로 배포하여 Dart Pad로부터 온 요청에 따라 알맞게 처리하려고 합니다. 

3주차에 공부한 것들을 관계 중점으로 설명해보았습니다.
이 세가지와 관련된 내용과 예제들 또한 노션에 정리되어 있으니 관심있는 분은 노션에서 확인해주세요! 

4주차부터 김신님과 프론트와 백으로 나누어 작업을 할 예정입니다.
Dart Pad는 모든 사람이 사용할 수 있게, Dart Services는 커스텀 가능하게 서비스하는 것을 1차적인 목표로,
이후 이 둘을 연결한 뒤 여러 기능을 추가하려고 합니다. 
-->

---

4 week
* Dart Pad Code 분석
* Embedding dart pad in web 정리 (Github 관련)
* 웹 서버 구축
* 웹 배포
