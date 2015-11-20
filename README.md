# home-heating-control

![네스트](http://qbinson.com/wp-content/uploads/2015/11/nest.jpg)
> Little rough nest를 목표로.

보일러 난방 온수 효율적으로 제어하기. 참고 링크([밸브갓](http://www.slideshare.net/KyuhoKim/20150122-valve-god), [김태훈님 커뮤니티글](http://m.todayhumor.co.kr/view.php?table=bestofbest&no=135305), [김태훈님 슬라이드](http://www.slideshare.net/rlaxogns/ss-41386800))

## 1. 왜 하는가

보일러 요금 때문이다. 작년 겨울에 보일러를 얼마 때지도 않았는데 한 달 가스 요금으로 13만원이 나왔다. 그것도 12, 1, 2, 3월 총 4개월 간. 혼자서 자취하고 있는데 이렇게 나오는건 뭔가 이상하지 않나. 그러던 와중에 김규호님의 발표를 들었고 이거다! 하는 생각이 들었다. 이번 겨울은 이 프로젝트를 통해 따뜻함과 가스비 두 마리 토끼를 모두 잡아보겠다. 전쟁이다.

## 2. 준비물
하드웨어는 [메카솔루션](http://mechasolution.com/shop/main/index.php)에서 구매했다.

- 하드웨어
    + Raspberry Pi 2
    + Relay
    + 와이파이 동글
    + AC21V 전동 밸브
    + 3008 10bit ADC
    + TMP36 온도센서
- 소프트웨어
    + node.js
    + MySQL
    + Wiring Pi

## 3. 목표 구현 기능

- 웹 서비스를 통해
    + 보일러 작동 유무를 알 수 있다.
    + 보일러를 작동, 정지시킬 수 있다.
    + 현재 온수의 온도, 가스 사용량(? 확인해봐야함)을 시각적으로 알 수 있다.
- 온수 온도 최대치를 적용하여 도달하면 보일러 작동이 멈추도록 한다.
- 온수가 집 밖으로 나가는 밸브를 프로그램이 조절한다. 30도 이상의 온수일 경우 밸브는 잠겨질 것이다. 그이하의 온수만 배출될 수 있다.

