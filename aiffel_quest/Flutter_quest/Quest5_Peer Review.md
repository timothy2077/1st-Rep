## AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김원영
- 리뷰어 : 김주현


## PRT(Peer Review Template)

- ['X']  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 퀘스트 문제 요구조건 등을 지칭
        - 아래 이미지와 같이 피어 리뷰 시점에서는 플러터 앱과 FastAPI 서버간 연결까지는 이루어지지 않은 상태였습니다.
        - 다만, 회고 내용에서도 적었고 피어 리뷰 과정에서도 언급해 주셨듯이 플러터 앱에서 사용하는 이미지를 네트워크 이미지로 구현하는 과정에서 예기치 못한 상황들이 발생하였고, 그 전까지의 테스트에서는 플러터 앱과 FastAPI 서버간의 연결 역시 실제적으로는 이루어졌던 것으로 보입니다. 
 
          ![final output](https://github.com/user-attachments/assets/dbe6f508-3fb9-479d-ac3c-fc7a20d5956f)

        
- [O]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 다음 코드에서처럼 레이블을 예측하는 함수와 확률을 예측하는 함수를 분리해서 좀 더 명확하게 처리하였습니다. 
            ```Dart
              Future<void> fetchData() async {
                // 예측 결과를 가져오는 함수
                try {
                  final enteredUrl = urlController.text; // 입력된 URL 가져오기
                  final response = await http.get(
                    Uri.parse("${enteredUrl}sample"), // 입력된 URL 사용
                    headers: {
                      'Content-Type': 'application/json',
                      'ngrok-skip-browser-warning': '69420',
                    },
                  );
                  if (response.statusCode == 200) {
                    final data = jsonDecode(response.body);
                    setState(() {
                      result = "예측값: ${data['predicted_label']}"; // 예측 결과를 문자열에 저장
                    });
                  } else {
                    setState(() {
                      result = "Failed to fetch data. Status Code: ${response.statusCode}";
                    });
                  }
                } catch (e) {
                  setState(() {
                    result = "Error: $e";
                  });
                }
              }
            
              Future<void> fetchData_1() async {
                // 예측 확률을 가져오는 함수
                try {
                  final enteredUrl = urlController.text; // 입력된 URL 가져오기
                  final response = await http.get(
                    Uri.parse("${enteredUrl}sample"), // 입력된 URL 사용
                    headers: {
                      'Content-Type': 'application/json',
                      'ngrok-skip-browser-warning': '69420',
                    },
                  );
                  if (response.statusCode == 200) {
                    final data = jsonDecode(response.body);
                    setState(() {
                      result_1 = "예측 정확도: ${data['prediction_score']}"; // 예측 확률을 문자열에 저장
                    });
                  } else {
                    setState(() {
                      result = "Failed to fetch data. Status Code: ${response.statusCode}";
                    });
                  }
                } catch (e) {
                  setState(() {
                    result = "Error: $e";
                  });
                }
              }
            ```
        
- [O]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인 또는
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 실험이 기록되어 있는지 확인
        - 문제에서 요구하는 것은 디버그 콘솔에 출력하는 것이었으나, 직접 앱 화면 내에 표시될 수 있도록 새로운 시도를 하였습니다. 
        
- [O]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해 배운점과 아쉬운점, 느낀점 등이 상세히 기록되어 있는지 확인
        - Dart 프로그램 하단에 아주 잘 정리되어 있습니다.
        - 특히, 이번 퀘스트에서의 경험을 통해 앞으로의 학습에서 변화할 부분에 대해서도 아주 잘 정리되어 있습니다.
            ```Dart
            // 그러나, 이러한 특별한 경험을 통해 내일부터는 좀 더 제 자신을 내려놓고 여유롭게, 즐겁게 학습할 수 있는 자세와 성격으로 개선할 수 있도록 노력해야 한다고 다짐해 봅니다.
            // 더 나아가 앞으로는 그 날 학습은 그 날 완료해야 한다는 강박관념에 사로잡혀 심신을 지치게 하기 보다는 부족하더라도 동료들과의 학습과정 자체를 즐기며 성장할 수 있도록 전체적인 mindset을 변화시킬 계획입니다. 
            ```  

- ['X']  **5. 코드가 간결하고 효율적인가요?**
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 모듈화(함수화) 했는지
        - 레이블을 예측하는 함수와 확률을 예측하는 함수를 분리하는 시도가 코드의 가독성 측면에서는 조금 더 유리할 수도 있으나, 그에 반해 중복된 코드는 상대적으로 늘어난 것을 확인할 수 있습니다.
        - 하나의 함수로 유지하고 파라미터를 통해 함수 내부에서 처리를 다르게 하는 것으로 코드를 수정하면 코드 중복도 최소화하고, 향후 다른 유형의 처리가 추가로 필요한 경우에도 유연하게 대처할 수 있을 것으로 생각됩니다.  


## 참고 링크 및 코드 개선

![2](https://github.com/user-attachments/assets/d6f4cbd6-db0f-4882-97b5-d00cfb211841)

![3](https://github.com/user-attachments/assets/57afe115-f450-4ddf-9671-c6ac430a6d3a)

![4](https://github.com/user-attachments/assets/b91da170-29a3-458d-a7aa-9cd9a4fcf4f7)

![5](https://github.com/user-attachments/assets/8f593d79-a582-4db3-9848-cc5d4cf3c3d6)

![6](https://github.com/user-attachments/assets/d789780e-4e29-4cf8-9f96-9f2d525d2043)






```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```




