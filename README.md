# navigator_secondpage
플러터 Navigator 사용 -> 페이지 이동

## 실행 화면
![image](https://user-images.githubusercontent.com/77111523/147670870-dae259dd-c195-4fce-97d8-c433ab20a302.png)
![image](https://user-images.githubusercontent.com/77111523/147670888-5da43ffa-bca1-4ca9-932b-718e68fd0634.png)

## 설명
Navigator의 정의
- 모든 앱 페이지들을 관리하면 stack이라는 자료구조 형식으로 Route 객체들을 관리함.
- 또, 이 stack이라는 자료구조를 관리하기 위해서 `push()`와 `pop()`이라는 메서드를 제공함.
- stack은 어떤 물건들을 쌓아 올린다는 의미
- `push()` 로 쌓고 `pop()` 으로 없애야 함

그렇다면 왜 굳이 push() 메서드를 불러올 때마다 MaterialPageRoute()를 사용하고 이 안에서 builder를 통해서 context를 Flutter에 의해서 할당받아야 하지???
- 언제 Route 호출이 일어나는가에 따라서 Route가 빌드하는 과정 중에 다른 context를 사용하게 될 수도 있고, 자칫 잘못된 context를 전달해서 Route의 호출에서 에러를 발생시킬 수도 있음.
- builder를 사용하면 이런 에러를 미연에 방지할 수 있고, builder에서 제공한 context를 사용할 필요가 없으면 사용하지 않아도 됨.
- MaterialPageRoute에서 builder의 사용은 일종의 안전장치라고 생각하면 됨.
