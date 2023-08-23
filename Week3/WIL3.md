# 3주차: 플러터 위젯 다루기

책 또는 강의: 03장 다트 비동기 프로그래밍
05장 기본 위젯 알아보기

## 03 다기 프로그래밍

### 3.1 동기 vs 비동기 프로그래밍

---

- 동기
    - 지금까지 모두 동기
    - 함수를 실행하면 다음 코드가 실행되기 전에 함수의 결괏값 먼저 반환

- 비동기
    - 요청한 결과를 기다리지 않고, 응답 순서도 요청한 순서와 다를 수 있음
    - 장점: 자원 낭비x, 효율적으로 코드 실행
    - ex) 데이터베이스 가져오는 작업, 복잡한 미적분 계산, 이미지 인코딩 등 시간이 걸리는 작업

### 3.2 Future

---

- 미래에 받아올 값
- Future.delayed() : 특정 기간 동안 아무것도 하지 않고 기다림
    
    ```dart
    Future.delayed(Duration(seconds: 3), () { // 3초간 대기
    });
    ```
    

### 3.3 async와 await

---

- 비동기 프로그래밍은 코드가 작성된 순서대로 실행되지 않으면 헷갈릴 수 있음
    
    → async, await 사용하면 가독성 유지 가능
    
- async
    - 함수 매개변수 정의와 바디 사이에 입력해서 지정해준다
- await
    - 대기하고 싶은 비동기 함수 앞에 입력

### 3.4 Stream

---

- 지속적으로 값을 반환 받을 때
    - cf) Future은 반환값을 딱 한 번 받아냄
- 사용하려면 플러터에서 기본으로 제공하는 dart:async 패키지 불러오고, StreamController를 listen()해야함
    
    ```dart
    import 'dart:async';
    
    void main() {
    final controller = StreamController();
    final stream = controller.stream;
    
    final streamListener1 = stream.listen((val){
    print(val);
    });
    
    controller.sink.add(1);
    }
    ```
    

## 05 기본 위젯 알아보기

### 5.1 위젯 소개

---

- Container, GestureDetector, SizedBox, Column, Row, ListView

- child 매개변수
    - 단 하나의 위젯만 입력

- children 매개변수
    - 여러 위젯을 리스트에 입력 가능

### 5.2 위젯 실습용 템플릿 작성

---

- 기본 코드
    
    ```dart
    import 'package:flutter/material.dart';
    
    void main() {
    	runApp(MyApp());
    }
    
    class MyApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
    	return MaterialApp(
    		home: Scaffold(
    			body: Center(
    				child:
    			),
    		),
    	);
    }
    }
    ```
    

### 5.3 텍스트 관련 위젯

---

- 화면에 글자를 보여주려면 글자를 렌더링할 수 있는 위젯 필요 → Text 위젯

### 5.4 제스처 관련 위젯

---

- 사용자가 키보드로 글자를 입력하는 행위 외의 모든 제스처
    - ex) 화면을 한 번 탭 or 두 번 탭 or 길게 누르는 행동
- Button 위젯
    - TextButton, OutlinedButton, ElevatedButton
- IconButton 위젯
- GestureDetector 위젯
- FloatingActionButton 위젯

### 5.5 디자인 관련 위젯

---

- Container 위젯
- SizeBox 위젯
- Padding 위젯
- SafeArea 위젯

### 5.6 배치 관련 위젯

---

- Row 위젯
- Column 위젯
- Flexible 위젯
- Expanded 위젯
- Stack 위젯