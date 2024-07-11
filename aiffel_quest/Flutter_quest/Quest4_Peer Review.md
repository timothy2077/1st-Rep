코더: 김원영 리뷰어: 유제민

<aside>
🔑 **PRT(Peer Review Template)**

- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 기능이 정상적으로 작동하는지?
        문제 없이 작동 잘 됩니다.
    
- [x]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation/markdown이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
        actions: <Widget>[
          IconButton(
            icon: Icon(Icons.search), // 검색 아이콘 버튼
            onPressed: () { // 검색 버튼이 눌렸을 때 호출되는 함수
              showSearch(context: context, delegate: CustomSearchDelegate());
            },
          ),
        ],
      ),
      body: Center(
        child: _widgetOptions.elementAt(_selectedIndex), // 현재 선택된 탭에 해당하는 위젯을 표시
      ),
      bottomNavigationBar: BottomNavigationBar( // 하단 네비게이션 바
        items: <BottomNavigationBarItem>[ // 각 탭 아이템들
          BottomNavigationBarItem(
            icon: Icon(Icons.add),
            label: '새 회의',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.calendar_today),
            label: '예약',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.event),
            label: '캘린더 추가',
          ),
        ],
        currentIndex: _selectedIndex, // 현재 선택된 탭의 인덱스
        selectedItemColor: Colors.amber[800], // 선택된 탭의 색상
        onTap: _onItemTapped, // 탭이 탭될 때 호출되는 함수
      ),
    );
  }

        
- [x]  **3.** 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는
   “새로운 시도 및 추가 실험”을 해봤나요? ****
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인 또는
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
        - 회고에 잘 적혀 있습니다.
        

        
- [x]  **4. 회고를 잘 작성했나요?**
    - 프로젝트 결과물에 대해 배운점과 아쉬운점, 느낀점 등이 상세히 기록 되어 있나요?
    - 이번 프로젝트를 진행하면서 어떤 문제가 있었는지, 어떻게 해결했는지, 어떤 것을 느꼈는지 잘 기록되어 있습니다.
    


- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 모듈화(함수화) 했는지
        - 효율적이고 정리가 잘 되어 있습니다.  
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
        - actions: <Widget>[
          IconButton(
            icon: Icon(Icons.search), // 검색 아이콘 버튼
            onPressed: () { // 검색 버튼이 눌렸을 때 호출되는 함수
              showSearch(context: context, delegate: CustomSearchDelegate());
            },
          ),
        ]
        - 앱 동작을 정말 간결하고 확실하게 구혔했다 생각합니다.
