<교수님 PLC 와 우리PLC 간 이더넷 모드버스 통신>
주의! 시작 전 레더 비실행문으로 만들기.
EFMT더블 클릭 후 설정

![20210304_100732](https://user-images.githubusercontent.com/57824945/109894808-7c477900-7cd1-11eb-82b5-7f165d82a259.png)
 
국번, IP주소 설정 하기.
모드버스 설정
 
![20210304_100744](https://user-images.githubusercontent.com/57824945/109894810-7d78a600-7cd1-11eb-9ca7-e255eb2d05be.png)
M0 으로 통일
EFMT 우클릭 > 항목추가 > P2P통신 추가
 
![20210304_100638](https://user-images.githubusercontent.com/57824945/109894812-7d78a600-7cd1-11eb-99a2-8350da3fdaf0.png)

P2P 채널 설정
 
![20210304_100654](https://user-images.githubusercontent.com/57824945/109894814-7e113c80-7cd1-11eb-9814-27234838e732.png)
상대방 국번(교수님) 설정.


P2P 블록 설정
 
![20210304_100703](https://user-images.githubusercontent.com/57824945/109894816-7ea9d300-7cd1-11eb-88cf-362effaa8c1f.png)
READ 변수 설정
 
![20210304_100712](https://user-images.githubusercontent.com/57824945/109894817-7ea9d300-7cd1-11eb-9c3a-2f6015dcb9f1.png)
읽을 영역 뒤의 세글자는 레더는 자기 저장 영역을 16진수로 변환한 것(예M500 -> 1F4).
WRITE
 
![20210304_100722](https://user-images.githubusercontent.com/57824945/109894818-7f426980-7cd1-11eb-9bcd-936fef462c79.png)

저장영역은 교수님이 정해주신 것 의 16진법으로 변환
(교수님 PLC의 어느 메모리에 보내라)
