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
