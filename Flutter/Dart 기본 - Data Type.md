## Keyword
`Flutter` `Dart` `Variables` `Type`

## Reference
- [노마드 코더 Dart 시작하기](https://nomadcoders.co/dart-for-beginners/lobbyy)
- [Dart 공식문서](https://dart.dev/guides)

## Data Type
#### String
  > 문자열을 따옴표를 활용하여 표현한다.
```
 String str = "Hello World";
 print(`str = $str`); // String Interploation
 print('str = ' + str); // String Concatenation
```

#### bool
  > true / false 값을 담는 타입이다.
```
 bool flag = true;
```

#### int
  > 정수 타입을 표현한다.
```
 int number = 12;
```

#### double
  > double과 int의 슈퍼 클래스이다.<br>
  > double과 int class는 num class를 상속 받는다.
```
 num number1 = 12;
 num number2 = 12.34;
```

#### List
  > 데이터를 순차적으로 담는 자료구조로 인덱싱이 가능하다.<br>
  > 대괄호를 사용하여 선언한다.
```
 List<int> list = [1, 2, 3, 4];
```
  - collection if
    > 조건에 의해 collection 값을 변경하거나 조정하고 싶을 때 사용한다.
  ```
   List<int> list = [
    1,
    2,
    3,
    4,
    if(true) 5, // collection if
   ]; 
   print(list); // [1, 2, 3, 4, 5]
  ```
    
  - collection for
    > collection 문법 안에서 for문을 사용할 수 있다. 
  ```
   List<String> list = [
    for (int i = 1; i < 5; i++) '#$i', // collection for, String Interpolation
    '#5',
   ];
   print(list); // [#1, #2, #3, #4, #5]
  ```

#### Map
  > key-value 쌍으로 이뤄진 객체를 말한다.<br>
  > key, value는 어떤 자료형이든 사용 가능하다.<br>
  > 중괄호를 사용해 선언할 수 있다.
```
 Map<String, int> map = {
     "one": 1,
     "two": 2,
     "three": 3,
 };

 print(map); // {one: 1, two: 2, three: 3}
```

#### Set
  > 요소의 저장 순서를 유지하지 않는다.<br>
  > 같은 요소의 중복을 허용하지 않는다.
```
 Set<int> set = {1, 2, 3, 4, 5};
 print(set); // {1, 2, 3, 4, 5}
 set.add(1); // 1을 넣어도 기존 set에 1이 있기 때문에 중복을 허용하지 않음
 print(set); // {1, 2, 3, 4, 5}
```
