[다트언어의 장점]
- UI 제작의 최적화
- 비동기 언어
- 동시성 기능
- 코드의 변경사항을 즉시 화면에 반영
- 멀티플랫폼에서 로깅, 디버깅, 실행 가능
- AOT 컴파일 가능 -> 빠른 속도
- 자바스크립트로의 컴파일 지원
- 백엔드 프로그래밍 지원

다트 문법 공부 : dartpad.dev

[기초 문법]
1) 메인함수 구조
void main() {
}
2) 주석
// /**/ ///
3) print()
4)var
var 변수명 = 값;
자동으로 타입을 추론한다
5) dynamic
dynamic 키워드를 사용하면 변수의 타입이 고정되지 않아서 다른 타입의 값을 저장할 수 있다
6) final / const 
이 둘은 변수의 값을 처음 선언 후 변경할 수 없다
둘의 차이는 코드를 실행하지 않은 상태에서 값이 확정되면 const를, 실행될 때 확정되는 final을 사용해야 에러가 안 난다
7) 변수 타입
Sting, int, double, bool

[컬렉션]
: 여러 값을 하나의 변수에 저장할 수 있는 타입
list, map, set
1) list
add(): 추가 / where(): 순회하면서 true면 유지 false면 버림 / map(): 순회하면서 값 변경 / reduce(): 순회하면서 값 쌓음 / fold(): reduce와 비슷한데 타입 제약이 없다는 차이점이 있다 / 

2) Map 타입
Map<키의 타입, 값의 타입>맵이름
키 실행하면 값 나오고, 값 실행하면 키 나옴

3) Set 타입
중복 방지

4) enum
변수의 값을 몇가지 옵션으로 제한하는 기능

[연산자]
1) + - * / % ++ += -= *= /= 다 가능
2) null
타입 뒤 ? 추가하면 null 저장
?? 사용하면 기존에 null인 때만 값이 저장되도록 할 수 있다
3) > < >= <= == != 다 가능
4) is 이용해서 변수 타입 비교 가능
5) && || 가능

[제어문]
1) if 문
2) switch 문
값에 따라 블록 수행, enum과 같이 사용하면 유용
3) for 문
4) while, do while 문

[함수와 람다]
1) 
포지셔널 파라미터: 순서대로 값이 지정
네임드 파라미터: 매개변수 순서 상관 없이 이름을 이용해 값을 입력
- { } 와 required 키워드 이용
포지셔널과 네임드 섞어쓸 때에는 포지셔널이 먼저 위치해야한다
2) 익명함수와 람다함수
둘 다 함수 이름이 없으며 일회성으로 쓸 때 사용
다트에서는 이 둘 구분 안 함
익명함수에서 {} 빼고 => 추가한 것이 람다 함수
3) typedef
typedef는 함수의 시그니처만 정의할 수 있다 (시그니처: 반환값 타입, 매개변수 개수와 타입 등)


[try catch]
try에서 에러가 나면 catch문을 실행하라는 뜻