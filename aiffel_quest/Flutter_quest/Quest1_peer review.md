(https://dartpad.dev/?id=0bfb1144ff824b90072e547af60f5409) 

배운 점: dart:async 라이브러리와 Timer.periodic 함수를 사용하여 반복 타이머를 구현하는 방법을 배웠고 Future.delayed 함수를 사용하여 작업 시간과 휴식 시간을 설정하는 방법을 배웠다.

아쉬운 점: 처음에는 작업 시간과 휴식 시간이 올바르게 번갈아 가며 출력되지 않는 문제가 있었는데 이 문제는 Future.delayed 함수 내부에서 sessionCount++를 호출하고 있어서 발행한 것을 확인했고 이 문제를 해결하기 위해 sessionCount++를 Future.delayed 함수 외부로 이동시켰다. 

느낀 점: 이 프로젝트를 통해 Dart 언어의 비동기 프로그래밍 기능을 활용하는 방법을 배울 수 있었는데 이것은 특히 시간이 오래 걸리는 작업을 처리할 때 유용하다는 것을 알게 되었다. 


AIFFEL Campus Code Peer Review Templete
코더 : 김원영님
리뷰어 : 김소영



<aside>
🔑 **PRT(Peer Review Template)**

- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
</aside>
   
    - 문제에서 요구하는 대로 코드가 작동합니다.
    - 4회차 마다 긴 쉬는 시간을 가지는 것, 25분동안 일을 진행하는것이 잘 작동되었다.
        ![image](https://github.com/timothy2077/1st-Rep/assets/169649051/c8ac4f36-dce4-461e-9cab-e6b19fbddaba)


- [x]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
    
    - 코드마다 한 줄씩 주석을 달아놓아서 작성된 설명만 보고도 해당코드가 잘 이해되었다.
     
    ![image](https://github.com/timothy2077/1st-Rep/assets/169649051/f27f8a2b-2603-487c-aaee-688fdb8dd701)

        
- [x]  **3.** 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는
 
  -회고부분에 오류가 났더누 부분을 디버깅 한 기록을 남기셨다. 
 ![image](https://github.com/timothy2077/1st-Rep/assets/169649051/69b4d71b-b281-45d7-9ef0-980d1c1c8752)

- [x]  **4. 회고를 잘 작성했나요?**
    
    - 회고를 따로 작성해서 코드를 짜면서 에러를 디버깅 했던 경험이나 느낀점에 대해 상세히 적어놓으셨다.

- [x]  **5. 코드가 간결하고 효율적인가요?**
   
    -코드의 중복을 최소화하고 가독성좋게 작성하셨다.
특히 start pomodoro timer 함수는 pomodoro timer 를 시작하는데 필요한 모든 기능을 포함되게 만들어져 있다. 이 함수는 작업 시간과 휴식시간을 설정하고 이를 번갈아가면서 실행하고 4번째 쉬는시간마다 긴 휴식시간을 주는 기능으로 구현되어 있고 특별히 pomodoro timer가 8회차를 반복한 후에는 타이머를 자동으로 취소하는 기능또한 포함되어있다.
