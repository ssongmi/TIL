## Keyword
`Flutter` `Dart` `Variables` `Type`

## Reference
- [노마드 코더 Dart 시작하기](https://nomadcoders.co/dart-for-beginners/lobbyy)
- [Dart 공식문서](https://dart.dev/guides)

## Types
#### var
  > 타입 추론이 가능하다.<br>
  > 추론된 타입이 한 번 입력되고 나면 다른 타입을 지정할 수 없다.
```
 var test = 123; // int 값 대입
 test = "test"; // Error - int 타입의 값 대입 후 다른 타입 대입 시
```

#### dynamic
  > 타입 추론이 가능하다.<br>
  > 타입이 정해진 후에도 변경 가능하다.
```
 dynamic test = 123; // int 값 대입
 test = "test"; // int 타입의 값 대입 후 다른 타입 대입 가능
```

#### final
  > 한 번 값을 대입하면 변경할 수 없다.
  > 파일이 실행될 때 해당 위치에서 값이 결정된다. → 런타임 시에 결정되는 값도 상수로 설정 가능하다.
```
 // 실행 시 시간이 결정되기 때문에 대입 가능
 final log = DateTime.now();
```

#### const
  > 한 번 값을 대입하면 변경할 수 없다.
  > 파일을 컴파일 할 때 값이 결정된다. → 컴파일 타임에 상수를 설정할 수 있다.
```
 // 실행 시 시간이 결정되기 때문에 const 타입 변수에 대입 불가
 const log = DateTime.now(); // Error
```

#### late
  > non-nullable 변수의 초기화를 나중에 할 수 있다.
  > 값의 초기화를 뒤로 미루지만, 개발자가 null을 실수로 사용하는 것을 방지할 수 있다.(nullable 과의 차이점)
```
 class Human {
    late String name; // late를 해주지 않으면 값이 초기화되지 않아 오류 발생
 }

 void mani() {
    Human h1 = Human();
    h1.name = 'human';
    print(h1.name); // human
 }
```
