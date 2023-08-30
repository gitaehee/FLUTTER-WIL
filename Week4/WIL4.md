# 4주차: UI 구현하기 1

책 또는 강의: 무료 인터넷 강의 시청 예정

- 링크
    
    [Flutter 로 웹툰 앱 만들기 – 노마드 코더 Nomad Coders](https://nomadcoders.co/flutter-for-beginners/lobby?utm_source=free_course&utm_campaign=flutter-for-beginners&utm_medium=site)
    
    ![2.2 부터 들었음](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled.png)
    
    2.2 부터 들었음
    
    ![들어오라고 하신 부분](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%201.png)
    
    들어오라고 하신 부분
    

## 2 HELLO FLUTTER

### 2.2 Running Flutter

---

- cmd에서
    - 경로 입력
        
        ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%202.png)
        
        - 한국어 있거나 띄어쓰기 있으면 “ “ 따옴표 쓰기
    - ‘flutter create 파일명’ 입력
        
        ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%203.png)
        
        - flutter run 입력 X
            - flutter run 하면 콘솔에서 하는 거라 안해야지 visual code에서 개발자 도구를 사용할 수 있음
    - 밑에 두 개 입력하면 자동으로 visual code 실행됨
        
        ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%204.png)
        

- visual studio code에서
    - 왼쪽 탭에 있는 확장(extension) 클릭해서 Dart랑 Flutter 설치하기
    - 오른쪽 하단에 window 클릭하면 상단 중간에 여러개 뜨는데 그 중에 chrome-web 클릭

## 3 UI CHALLENGE

### 3.0 Header

---

- lib 안에 있는 main dart에서 시작
- 기본 코드
    
    ```dart
    import 'package:flutter/material.dart';
    
    void main() {
      runApp(App());
    }
    
    class App extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            body: Center(
              child: Text('Hello world!'),
            ),
          ),
        );
      }
    }
    ```
    
    - test에 있는 widget_test.dart 에서도 const MyApp을 그냥 App으로 바꿔주기
    - 오른쪽이 화면 보이게 하는 거고 왼쪽이 중지
        
        ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%205.png)
        
        ![결과](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%206.png)
        
        결과
        
- 백그라운드 예시
    - Colors.red.shade800,
- 결과
- 이미지
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%207.png)
    
- 코드
    
    ```
    import 'package:flutter/material.dart';
    
    void main() {
      runApp(App());
    }
    
    class App extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            backgroundColor: Color(0xFF181818), //검정배경
            body: Padding(
              padding: EdgeInsets.symmetric(horizontal: 40), //겉테두리 남기기
              child: Column(
                children: [
                  SizedBox(
                    height: 80, //옆으로 옮기기
                  ),
                  Row(
                    mainAxisAlignment: MainAxisAlignment.end, //오른쪽 끝으로 보내기
                    children: [
                      Column(
                        crossAxisAlignment: CrossAxisAlignment
                            .end, //글자 두개가 중간에 맞춰지지 않게 둘다 모두 오른쪽 정렬 되도록
                        children: [
                          Text(
                            'Hey, Selena',
                            style: TextStyle(
                              color: Colors.white, //배경검정이니 글자흰색으로
                              fontSize: 28,
                              fontWeight: FontWeight.w800,
                            ),
                          ),
                          Text(
                            'Welcome back',
                            style: TextStyle(
                                color: Colors.white.withOpacity(0.8), fontSize: 18),
                          ),
                        ],
                      )
                    ],
                  )
                ],
              ),
            ),
          ),
        );
      }
    }
    ```
    

### 3.1 Developer Tools

---

- 오른쪽 가이드라인 누르면 이렇게 뜸
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%208.png)
    

### 3.2 Buttons Section

---

- 이미지
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%209.png)
    
- 코드
    
    ```dart
    import 'package:flutter/material.dart';
    
    void main() {
      runApp(App());
    }
    
    class App extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            backgroundColor: Color(0xFF181818), //검정배경
            body: Padding(
              padding: EdgeInsets.symmetric(horizontal: 40), //겉테두리 남기기
              child: Column(
                //서로를 위 아래로 두고 싶을 때 콜롬 쓴다 (옆은 Row)
                crossAxisAlignment: CrossAxisAlignment.start, //왼쪽으로 이동
                children: [
                  SizedBox(
                    height: 80, //옆으로 옮기기
                  ),
                  Row(
                    //이모티콘이 글씨 옆에 있어서
                    mainAxisAlignment: MainAxisAlignment.end, //오른쪽 끝으로 보내기
                    children: [
                      Column(
                        //글씨 두개가 세로로 있어서
                        crossAxisAlignment: CrossAxisAlignment
                            .end, //글자 두개가 중간에 맞춰지지 않게 둘다 모두 오른쪽 정렬 되도록
                        children: [
                          Text(
                            'Hey, Selena',
                            style: TextStyle(
                              color: Colors.white, //배경검정이니 글자흰색으로
                              fontSize: 28,
                              fontWeight: FontWeight.w800,
                            ),
                          ),
                          Text(
                            'Welcome back',
                            style: TextStyle(
                                color: Colors.white.withOpacity(0.8), fontSize: 18),
                          ),
                        ],
                      )
                    ],
                  ),
                  SizedBox(
                    height: 120,
                  ),
                  Text(
                    'Total Balance',
                    style: TextStyle(
                      color: Colors.white.withOpacity(0.8),
                    ),
                  ),
                  SizedBox(
                    height: 5,
                  ),
                  Text(
                    '\$5 194 482', //$는 변수 넣을 때 사용하는데 5는 변수가 아니니까 \넣어줘야함
                    style: TextStyle(
                      fontSize: 48,
                      fontWeight: FontWeight.w600,
                      color: Colors.white,
                    ),
                  ),
                  SizedBox(
                    height: 30,
                  ),
                  Row(
                    children: [
                      Container(
                        decoration: BoxDecoration(
                          color: Colors.amber,
                          borderRadius: BorderRadius.circular(45),
                        ),
                        child: Padding(
                          padding: EdgeInsets.symmetric(
                            vertical: 20,
                            horizontal: 50,
                          ),
                          child: Text(
                            'Transfer',
                            style: TextStyle(
                              fontSize: 20,
                            ),
                          ),
                        ),
                      ),
                    ],
                  ),
                ],
              ),
            ),
          ),
        );
      }
    }
    ```
    

### 3.3 VSCode Settigs

---

- 파란 줄 오류 라인 없애는 법
    - 오류 뜨는 이유 : const를 쓰는 게 좋은데 어느 곳에 쓰고 안 쓰고를 다 기억할 수 없기 때문
    1. 설정 들어가서 command palette (명령 팔레트) 들어가기
    2. open user setting (JSON) 클릭하고 아래 코드 삽입
        
        ```
        ,
                "editor.codeActionsOnSave": {
                    "source.fixAll": true
                },
        ```
        
- "dart.previewFlutterUiGuides": true, → 실행 안 됨

### 3.4 Code Actions

---

- 전구 클릭
    - ex) wrap with padding
        - 패딩으로 감쌀 수 있음
    - 단축키 : control + .

### 3.5 Reusable Widgets

---

- 이미지
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%2010.png)
    
- 코드
    
    ```dart
    import 'package:flutter/material.dart';
    import 'package:toonflix/widgets/Button.dart';
    
    void main() {
      runApp(const App());
    }
    
    class App extends StatelessWidget {
      const App({super.key});
    
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            backgroundColor: const Color(0xFF181818), //검정배경
            body: Padding(
              padding: const EdgeInsets.symmetric(horizontal: 40), //겉테두리 남기기
              child: Column(
                //서로를 위 아래로 두고 싶을 때 콜롬 쓴다 (옆은 Row)
                crossAxisAlignment: CrossAxisAlignment.start, //왼쪽으로 이동
                children: [
                  const SizedBox(
                    height: 80, //옆으로 옮기기
                  ),
                  Row(
                    //이모티콘이 글씨 옆에 있어서
                    mainAxisAlignment: MainAxisAlignment.end, //오른쪽 끝으로 보내기
                    children: [
                      Column(
                        //글씨 두개가 세로로 있어서
                        crossAxisAlignment: CrossAxisAlignment
                            .end, //글자 두개가 중간에 맞춰지지 않게 둘다 모두 오른쪽 정렬 되도록
                        children: [
                          const Text(
                            'Hey, Selena',
                            style: TextStyle(
                              color: Colors.white, //배경검정이니 글자흰색으로
                              fontSize: 28,
                              fontWeight: FontWeight.w800,
                            ),
                          ),
                          Text(
                            'Welcome back',
                            style: TextStyle(
                                color: Colors.white.withOpacity(0.8), fontSize: 18),
                          ),
                        ],
                      )
                    ],
                  ),
                  const SizedBox(
                    height: 120,
                  ),
                  Text(
                    'Total Balance',
                    style: TextStyle(
                      color: Colors.white.withOpacity(0.8),
                    ),
                  ),
                  const SizedBox(
                    height: 5,
                  ),
                  const Text(
                    '\$5 194 482', //$는 변수 넣을 때 사용하는데 5는 변수가 아니니까 \넣어줘야함
                    style: TextStyle(
                      fontSize: 48,
                      fontWeight: FontWeight.w600,
                      color: Colors.white,
                    ),
                  ),
                  const SizedBox(
                    height: 30,
                  ),
                  const Row(
                    mainAxisAlignment: MainAxisAlignment.spaceBetween, //버튼 두개 떨어트리기
                    children: [
                      Button(
                          text: 'Transfer',
                          bgColor: Color(0xFFF1B33B),
                          textColor: Colors.black),
                      Button(
                          text: 'Request',
                          bgColor: Color(0xFF1F2123),
                          textColor: Colors.white),
                    ],
                  ),
                ],
              ),
            ),
          ),
        );
      }
    }
    ```
    
- 폴더랑 파일 하나 더 만들기
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%2011.png)
    
    - 코드
        
        ```dart
        import 'package:flutter/material.dart';
        
        class Button extends StatelessWidget {
          final String text;
          final Color bgColor;
          final Color textColor;
        
          const Button(
              {super.key,
              required this.text,
              required this.bgColor,
              required this.textColor});
        
          @override
          Widget build(BuildContext context) {
            return Container(
              decoration: BoxDecoration(
                color: bgColor,
                borderRadius: BorderRadius.circular(45),
              ),
              child: Padding(
                padding: const EdgeInsets.symmetric(
                  vertical: 20,
                  horizontal: 50,
                ),
                child: Text(
                  text,
                  style: TextStyle(
                    color: textColor,
                    fontSize: 20,
                  ),
                ),
              ),
            );
          }
        }
        ```
        

### 3.6 Cards

---

- 이미지
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%2012.png)
    

### 3.7 Icons and Transforms

---

- 이미지
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%2013.png)
    

### 3.8 Reusable Cards

---

- 이미지
    
    ![Untitled](4%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20UI%20%E1%84%80%E1%85%AE%E1%84%92%E1%85%A7%E1%86%AB%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%201%2070af1dbd4a5c471bbdabbc9b0cac696c/Untitled%2014.png)