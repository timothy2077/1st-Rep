https://dartpad.dev/?id=0bfb1144ff824b90072e547af60f5409
배운 점: dart:async 라이브러리와 Timer.periodic 함수를 사용하여 반복 타이머를 구현하는 방법을 배웠고 Future.delayed 함수를 사용하여 작업 시간과 휴식 시간을 설정하는 방법을 배웠다.

아쉬운 점: 처음에는 작업 시간과 휴식 시간이 올바르게 번갈아 가며 출력되지 않는 문제가 있었는데 이 문제는 Future.delayed 함수 내부에서 sessionCount++를 호출하고 있어서 발행한 것을 확인했고 이 문제를 해결하기 위해 sessionCount++를 Future.delayed 함수 외부로 이동시켰다. 

느낀 점: 이 프로젝트를 통해 Dart 언어의 비동기 프로그래밍 기능을 활용하는 방법을 배울 수 있었는데 이것은 특히 시간이 오래 걸리는 작업을 처리할 때 유용하다는 것을 알게 되었다. 
