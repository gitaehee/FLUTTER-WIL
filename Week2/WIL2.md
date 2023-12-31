# 2주차: Dart 언어 개념 2

책 또는 강의: 02장 다트 객체지향 프로그래밍

## 02 다트 객체지향 프로그래밍

### 2.1 객체지향 프로그래밍의 필요성

---

- 모두 main에 작성하지 않고, 클래스에 종속되게 할 수 있음

### 2.2 객체지향 프로그래밍의 시작, 클래스

---

```dart
Idol blackPink = Idol(); // Idol 인스턴스(객체) 생성
```

2.2.1 생성자

- 클래스의 인스턴스를 생성하는 메서드

```dart
Idol(String name) : this.name = name;
```

2.2.2 네임드 생성자

- 클래스를 생성하는 여러 방법을 명시하고 싶을 때 사용

2.2.3 프라이빗 변수

- 같은 파일에서만 접근 가능한 변수
    - cf ) 다른 언어: 클래스 내부에서만 사용하는 변수

```dart
String _name // '_'로 시작해 선언
```

2.2.4 게터 / 세터

- getter는 값을 가져올 때, setter는 값을 지정할 때
- 장점: 어떤 값이 노출되고 어떤 형태로 노출될지, 어떤 변수를 변경 가능하게 할지 유연하게 정할 수 있음
- 게터는 매개변수 정의 x, 세터는 매개변수를 하나만 받음

```dart
blackPink.name = '에이핑크'; // 세터
print(blackPink.name); // 게터
```

### 2.3 상속

---

- extends 키워드를 사용해 상속
- class 자식 클래스 extends 부모클래스

### 2.4 오버라이드

---

@override

- 오버라이드 → 자식클래스에 재정의된 메서드 실행

오버라이드x → 부모클래스에서 정의된 메서드 사용

### 2.5 인터페이스

---

- 여러개 쓰고 싶으면 ‘,’로 열거
- 상속은 재정의 필요 없지만, 인터페이스는 모든 기능을 다시 재정의해야한다.

### 2.6 믹스인

---

- 특정 클래스에 원하는 기능들만 골라넣을 수 있는 기능
- ‘,’로 열거

### 2.7 추상

---

- 상속이나 인터페이스로 사용하는 데 필요한 속성만 정의하고 인스턴스화할 수 없도록 하는 기능
- abstract 키워드

### 2.8 제네릭

---

- 특정 변수의 타입을 하나의 타입으로 제한학 싶지 않을 때 자주 사용

### 2.9 스태틱

---

- static 키워드 사용하면 클래스 자체에 귀속
    - cf ) 다른 속성들은 각 ‘클래스의 인스턴스’에 귀속

### 2.10 캐스케이드 연산자

---

- 인스턴스에서 해당 인스턴스의 속성이나 멤버 함수를 연속해서 호출할 때 사용