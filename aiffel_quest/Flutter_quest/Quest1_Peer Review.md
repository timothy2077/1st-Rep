import 'dart:async'; // Dart의 비동기 라이브러리를 가져옵니다.

void main() {
  startPomodoroTimer(); // Pomodoro 타이머를 시작하는 함수를 호출합니다.
}

void startPomodoroTimer() {
  int cycleCount = 0; // 전체 Pomodoro 타이머의 회차를 추적하는 변수입니다.
  int sessionCount = 25 * 60; // 작업 시간을 초 단위로 설정하고, 역순으로 시작합니다.
  const workDuration = Duration(minutes: 25); // 작업 시간을 설정합니다.
  const shortBreakDuration = Duration(minutes: 5); // 짧은 휴식 시간을 설정합니다.
  const longBreakDuration = Duration(minutes: 15); // 긴 휴식 시간을 설정합니다.

  // Timer.periodic을 사용하여 매 초마다 반복되는 타이머를 생성합니다.
  Timer timer = Timer.periodic(Duration(seconds: 1), (timer) {
    // 남은 시간을 분과 초로 계산합니다.
    int remainingMinutes = sessionCount ~/ 60;
    int remainingSeconds = sessionCount % 60;
    // 남은 시간을 문자열로 변환합니다.
    String timeLeft = '${remainingMinutes.toString().padLeft(2, '0')}:${remainingSeconds.toString().padLeft(2, '0')}';

    if (cycleCount < 4) { // 4회차 이전이라면
      if (sessionCount > 0) { // 작업 시간 동안
        print('작업 시간: $timeLeft'); // 남은 작업 시간을 출력합니다.
        sessionCount--; // 1초마다 시간을 감소시킵니다.
      } else { // 작업 시간이 끝나면
        print('작업 시간이 종료되었습니다. 휴식 시간을 시작합니다.'); // 작업 종료 메시지를 출력합니다.
        sessionCount = shortBreakDuration.inSeconds; // 휴식 시간을 설정합니다.
        cycleCount++; // 회차를 증가시킵니다.
      }
    } else { // 4회차라면
      if (sessionCount > 0) { // 긴 휴식 시간 동안
        print('긴 휴식 시간: $timeLeft'); // 남은 긴 휴식 시간을 출력합니다.
        sessionCount--; // 1초마다 시간을 감소시킵니다.
      } else { // 긴 휴식 시간이 끝나면
        cycleCount = 0; // 회차를 초기화합니다.
        sessionCount = workDuration.inSeconds; // 작업 시간을 다시 설정합니다.
      }
    }

    if (cycleCount == 8) { // 전체 Pomodoro 타이머가 8회차를 반복하면
      timer.cancel(); // 타이머를 취소합니다.
    }
  });
}
//분석 A: 
//1. 작업 시간과 휴식 시간이 올바르게 번갈아 가며 출력되지 않는 문제가 발생
//2. 이 문제는 Future.delayed 함수 내부에서 sessionCount++를 호출하기에 발생
//3. 문제해결을 위해 sessionCount++를 Future.delayed 함수 외부로 이동
//4. startPomodoroTimer 함수를 사용하여 하나의 함수 내에 필요한 로직을 구현

//회고 B:
//1. 배운 점: dart:async 라이브러리와 Timer.periodic 함수를 사용하여 반복 타이머를 구현하는 방법을 배웠고 Future.delayed 함수를 사용하여 작업 시간과 휴식 시간을 설정하는 방법을 배웠다.
//2. 아쉬운 점: 처음에는 작업 시간과 휴식 시간이 올바르게 번갈아 가며 출력되지 않는 문제가 있었는데 이 문제는 Future.delayed 함수 내부에서 sessionCount++를 호출하고 있어서 발행한 것을 확인했고 이 문제를 해결하기 위해 sessionCount++를 Future.delayed 함수 외부로 이동시켰다.
//3. 느낀 점: 이 프로젝트를 통해 Dart 언어의 비동기 프로그래밍 기능을 활용하는 방법을 배울 수 있었는데 이것은 특히 시간이 오래 걸리는 작업을 처리할 때 유용하다는 것을 알게 되었다.

     
