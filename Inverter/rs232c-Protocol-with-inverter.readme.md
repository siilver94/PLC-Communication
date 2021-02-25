# PLC 와 인버터 간 rs232c 사용자 정의 통신

<br/>

## 인버터 설정
<br/>

**인버터** 에서 오른쪽 화살표를 눌러 CM 으로 감.

**0번**. 무시.

**1번**. 인버터 국번설정으로, 교수님 과 맞춰야 함
  cm1이 다시 나와야 설정 된 것.
  
**2번.** 2번으로 설정.

**3번.** 3번 설정.

**4번.** 0번 설정.

**5번**. 5번 설정

<br/>

**위의 설정들 완료 후 ESC 눌러서 숫자 창이 떠야 함.**

<br/>

## PLC와 연결 확인(485, 이더넷 모듈 추가)
<br/>

온라인 접속.

기본 네트워크 오른쪽 마우스 > 항목추가 > 통신모듈 > **CH2A**와 **EFMT** 설정하는데 슬롯 번호 확인(5,7).

온라인 > 진단 > I/o정보 로 가서 **CH2A, EFMT** 에서 슬롯 번호 확인 가능.

**CH2A** 더블클릭 후 채널2 **RS422 -> 485** 로 변경.

**통신속도 9600bps** 확인.

고급설정은 바꿀필요 없고 8 1 NONE 인지만 확인.

기본은 국번은 0번.(인버터 국번과 겹치면 바꿔야함)

채널2는 **P2P** 사용

![20210224_092156](https://user-images.githubusercontent.com/57824945/108926444-c8673d80-7681-11eb-8fd5-bf7a4fc67486.png)

CH2A 우클릭 > 항목추가 > P2P통신 추가.

![20210224_092249](https://user-images.githubusercontent.com/57824945/108926485-e16fee80-7681-11eb-9443-57d29c1ce0f2.png)


### 통신요구 추가

**프레임 종류 주의**

![20210224_092331](https://user-images.githubusercontent.com/57824945/108926544-fa789f80-7681-11eb-9c84-599386cc16ed.png)

### HEAD
통신요구 우리클릭 > 프레임 추가 > HEAD

![20210224_092358](https://user-images.githubusercontent.com/57824945/108926569-082e2500-7682-11eb-8dd2-1bc0f2db8845.png)


### TAIL

통신요구 우리클릭 > 프레임 추가 > TAIL
바로 BCC 추가 클릭.


![20210224_092427](https://user-images.githubusercontent.com/57824945/108926612-1a0fc800-7682-11eb-971b-8768e815d18f.png)

라인추가

![20210224_092451](https://user-images.githubusercontent.com/57824945/108926648-2a27a780-7682-11eb-8f4a-781891041503.png)

### BODY

통신요구 우리클릭 > 프레임 추가 > 읽기 요구BODY.


![20210224_092519](https://user-images.githubusercontent.com/57824945/108926687-390e5a00-7682-11eb-9535-b9cfef674f07.png)


![20210224_092538](https://user-images.githubusercontent.com/57824945/108926710-462b4900-7682-11eb-9b1b-b0d659ba91e0.png)

**중요! BODY의 데이터의 첫 알파벳(R,W) 앞은 인버터의 국번과 같게 한다. **

## BODY 또 추가

통신요구 우리클릭 > 프레임 추가 > 쓰기 요구 BODY 추가.

![20210224_092607](https://user-images.githubusercontent.com/57824945/108926736-56432880-7682-11eb-9d65-1b1edd3dacc9.png)

문자열 상수 입력 후 라인 추가 해서 밑의 그림처럼 입력.

이것 또한 **문자열 상수의 알파벳 앞의 숫자는 인버터 국번을 따라간다.**

![20210224_092634](https://user-images.githubusercontent.com/57824945/108926761-65c27180-7682-11eb-8aaa-b6a5a5e849ec.png)

그룹명 : 통신응답 / 프레임 종류 : 수신.

통신 응답 우클릭 > 프레임 추가 > HEAD 추가

![20210224_092703](https://user-images.githubusercontent.com/57824945/108926787-770b7e00-7682-11eb-8156-013527ad7228.png)


통신 응답 우클릭 > 프레임 추가 > TAIL 추가
상단의 ‘BCC 추가’ 버튼 클릭.

![20210224_092737](https://user-images.githubusercontent.com/57824945/108926833-8b4f7b00-7682-11eb-9bf9-d08fd6c21ebc.png)

라인 추가

![20210224_092801](https://user-images.githubusercontent.com/57824945/108926877-99050080-7682-11eb-8216-675a8218442f.png)

통신 응답 우클릭 > 프레임 추가 > 읽기 응답 BODY 추가

![20210224_092824](https://user-images.githubusercontent.com/57824945/108926903-a7531c80-7682-11eb-804a-a4dd2ac9adef.png)

이곳 데이터 또한 **국번에 맞추고 ASCII TO Hex 주의!**

통신 응답 우클릭 > 프레임 추가 > 쓰기 응답 BODY 한 개 더 추가


![20210224_092851](https://user-images.githubusercontent.com/57824945/108926930-b6d26580-7682-11eb-9e6b-3890fdba910d.png)

**국번, 메모리 설정 체크 주의.**

![20210224_092912](https://user-images.githubusercontent.com/57824945/108926964-c3ef5480-7682-11eb-840f-95c73ad38fee.png)

### P2P 블록 설정.

![20210224_092939](https://user-images.githubusercontent.com/57824945/108927003-d36e9d80-7682-11eb-8de0-aa2180cfb57b.png)


