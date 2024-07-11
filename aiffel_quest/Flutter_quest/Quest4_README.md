
## 플러터 구현 
https://dartpad.dev/?id=0b5623823b85e5067cff0826c746f48f


## 지금까지 진행한 과정(정보 구조 분석, 와이어프레임, 프로토타이핑, 플러터 구현)을 하기 Fima를 통해 하나의 문서로 정리 (링크 및 embed code를 클릭해 주시고 Ctrl와 +를 통해 확대해 주세요~!)

Figma

https://www.figma.com/board/vbc1e8elI1pTRcvuwmJ2gm/Zoom-App-Structure?node-id=0-1&t=fZ9HqTNbioY3Zp4e-1

<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fboard%2Fvbc1e8elI1pTRcvuwmJ2gm%2FZoom-App-Structure%3Fnode-id%3D0-1%26t%3DfZ9HqTNbioY3Zp4e-1" allowfullscreen></iframe>


## 회고:

// 사용자 경험을 향상시키고 “ZOOM 4.0” 예약 시스템의 인터페이스를 간소화하기 위해, 저는 다양한 기능을 통합하는 여정을 시작했습니다. 그러나 복잡성이 오히려 기능성을 가리게 되는 결정적인 순간에 부딪혔고, 이로 인해 오버플로 오류가 발생하고 코드베이스가 복잡해졌습니다.

// 다수의 기능을 추가하는 것이 처음에는 좋은 의도로 시작되었지만, 이는 덜 직관적이고 더욱 번거로운 사용자 인터페이스를 초래하게 되었습니다. 이러한 인식은 단순화를 향한 전략적인 전환을 촉발시켰습니다. 필수 기능들로 줄여나가면서 저는 원활하고 사용자 친화적인 경험을 제공하는 핵심 목표에 다시 집중하게 되었습니다.

// 이러한 성찰 과정은 기능의 다양성과 사용자 편의성 사이의 균형을 유지하는 것의 중요성을 강조하였습니다. 추가된 ReservationScreen의 부가적인 기능들을 제외함으로써 사용자 중심의 좀 더 간결한 코드를 구현하려 노력했습니다.

// 추가하려된 기능들: 회의 ID, 비밀번호, 위치, 캘린더 선택 드롭다운 메뉴 등

// "회의 상세 정보 입력 필드들"
            TextField(
              decoration: InputDecoration(
                labelText: '회의 ID',
              ),
            ),
            SizedBox(height: 10),
            TextField(
              decoration: InputDecoration(
                labelText: '비밀번호',
              ),
            ),
            SizedBox(height: 10),
            TextField(
              decoration: InputDecoration(
                labelText: '날짜 및 시간',
              ),
            ),
            SizedBox(height: 10),
            // 위치 정보 입력 필드
            TextField(
              decoration: InputDecoration(
                labelText: '위치',
              ),
            ),
            SizedBox(height: 10),
            // 캘린더 선택 드롭다운 메뉴
            DropdownButton<String>(
              items: <String>['iCalendar', 'Google Calendar', 'Outlook'].map((String value) {
                return DropdownMenuItem<String>(
                  value: value,
                  child: Text(value),
                );
              }).toList(),
              onChanged: (_) {},
            ),
            SizedBox(height: 20),
            // 알림 설정 스위치
            SwitchListTile(
              title: Text('회의 시작 15분 전 알림'),
              value: true,
              onChanged: (bool value) {},
            ),
