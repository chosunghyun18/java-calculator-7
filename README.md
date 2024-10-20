# java-calculator-precourse

---
### 학습 목표

- Git, GitHub, IDE 등 실제 개발을 위한 환경에 익숙해진다.
- 교육 분야에 맞는 프로그래밍 언어를 사용하여 간단한 문제를 해결한다.

### 나만의 학습 목표

- String 비교 연산을 효율적으로 하는 방식을 익힌다.
- 정의를 하고 개발을 하는 연습을 한다.

---

### 기능 요구 사항

입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.

- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.

    - 예: "" => 0, "1,2" => 3, "1,2,3" => 6, "1,2:3" => 6

- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 문자를 커스텀 구분자로 사용한다.

    - 예를 들어 "//;\n1;2;3"과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.

- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.


### 입출력 요구 사항

#### 입력

- 구분자와 양수로 구성된 문자열


#### 출력

- 덧셈 결과

```
  결과 : 6
```

실행 결과 예시

```
  덧셈할 문자열을 입력해 주세요.
  1,2:3
  결과 : 6
```


### 프로그래밍 요구 사항

---


- JDK 21 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 Application의 main()이다.
- build.gradle 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 System.exit()를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
- 기본적으로 Java Style Guide를 원칙으로 한다.


---

1) 입출력 요구 사항 정의

입력 "구분자와 양수로 구성된 문자열" 은 다음과 같다.

- 기능 요구 사항을 따르면 '잘못된 값'을 입력한 경우라 명시가 되어 있다.

잘못된 입력 값의 대한 추가 설명은 다음과 같다.

정의 : 구분자와 양수로 구성된 문자열 외 조합으로 된 문자열 모두

예시 ) 구분자로만 구성된 문자열

```
  
  -> ",,::"
  
  -> "//;\n:,,:"
  
```

예시 ) 숫자로만 구성된 문자열

```
  
  -> "112211"
  
  -> "001011"
  
```

예시 ) 구분자와 숫자 외 추가로 구성된 문자열

```
  
  -> "1,2:3 4"
  커스텀 구분자가 아닌 공백이 추가로 조합된 문자열
  
  -> "1,2:3 ㅁ"
  커스텀 구분자가 아닌 한글 'ㅁ' 이 추가로 조합된 문자열
  
```


#### 입력 가능한 값 

- 문자열 길의 대한 제한 다음과 같다.
  : 주어진 라이브러리를 사용자 입력으로 받는다는 조건에 의하여, 문자열 길이의 제한을 확인한다.

출력 형식의 대한 정의

다음 처럼 1줄로 출력을 정의 한다.

다음) "결과 : [숫자]"

예시)

```
   -> 결과 : 6
   
   -> 결과 : 15

```



2) 기능 요구 사항의 대한 정의

입력한 문자열에서 추출여 더하는 계산기를 만든다.

커스텀 구분자를 지정할 수 있다.

커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 '문자'를 커스텀 구분자로 사용한다.

- 커스텀 구분자를 통해 만드는 구분자의 대한 대상은 '문자'이다. 

문자는 다음과 같이 정의한다.

- 언어학 해석 : 언어의 전달 수단의 하나로 사용되는 부호 , 점 선 등의 조합
- 컴퓨터 : 컴퓨터가 기억하거나 송출할 수 있는 숫자나 알파벳 또는 특수문자를 이르는 말

출처) Oxford Language

커스텀 구분자로 만들 수 있는 문자의 대한 정의

문자열을 구성 할 수 있는 컴퓨터가 입력 가능한 문자 모두

커스텀 구분자의 예시

```
   -> 
   공백 n 개
   
   -> //0\n10203
  숫자 0
  
```






