# 변수

---

## 0. 개요

- 메모리에 이름을 붙여 놓고 값을 저장하는 것 => 객체를 참조하는 이름표
- 실제 데이터는 객체 안에 저장
- 용도에 맞게 이름을 붙이되 중복되어서는 안됨
- 파이썬 변수는 참조형 변수

## 1. print() / id() / type() 함수

- print(변수)
  - 변수가 가리키는 객체의 값 출력

  - 문자열과 변수를 함께 출력할 때

    - 방법 1

      ```python
      print("문자열", 변수)
      ```

    - 방법 2: 포맷코드 사용

      ```python
      name = "홍길동"
      no = 2016001
      year = 4
      grade = "A"
      average = 93.5
      print("성명: %s"% name)
      print("학번: %s"% no)
      print("학년: %d"% year)
      print("학점: %c"% grade)
      print("평균: %.2f"% average)        # % 와 f 사이에 '.n'으로 소숫점 자리 조절
      성명: 홍길동
      학번: 2016001
      학년: 4
      학점: A
      평균: 93.50
      ```

- id(변수)

  - 변수가 가리키는 객체를 입력값으로 받아서 객체의 고유값(레퍼런스)을 반환 
  - 변수가 참조하는 주소를 출력

- type(변수)

  - 변수의 형태(저장된 값의 형태)를 출력

```python
x = 10
print(x)
10                  # 변수가 참조하는 주소를 찾아가 저장된 값을 출력
id(x)
140390483237456     # 변수가 참조하는 주소를 출력
type(x)
<class 'int'>       # 변수의 형태를 출력
```

## 2. 특징

- 변수 선언이 따로 필요 없음
  - 필요한 곳에서 변수를 만들어 값을 저장
  - 변수에 저장된 값의 형태에 따라
  - 실행 시점에서 동적으로 type 검사
  - 동적 타입: 실행 중에 변수의 타입을 바꿀 수 있는 특성
- 파이썬 변수는 대입하면 변수를 만들어(선언) 저장하게 됨

## 3. 변수명

- 대소문자 구분

- 중간에 공백 허용 X

- 이미 용도가 정해져 있는 예약어를 사용할 수 없음

- 표기법

  1. 스네이크 표기법: 변수명은 영문자와 숫자, 밑줄(_)로 구성 `camel_case`

  2. 카멜 표기법: 각 단어의 첫 문자는 대문자로 표기하고 붙여쓰되 맨 처음 문자는 소문자로 표기 `camelCase`

  3. 파스칼 표기법: 카멜 표기법과 비슷하지만 맨 처음 문자를 대문자로 표기 `PascalCase`

## 4. 변수 저장

- 한 개의 변수에 한 개의 값 저장

```python
result = 10
```

- 여러개의 변수에 여러개의 값을 저장

```python
a, b, c, d = 1, 2, 3, 4     # 왼쪽 항의 변수의 개수와 오른쪽 항의 변수의 개수가 일치해야 함
```

- 여러개의 변수에 동일한 한 개의 값을 저장

```python
a = b = c = 10          # 변수1 = 변수2 = 변수3 = 값
print(a)
10
print(b)
10
print(c)
10
```

- 두 변수의 값 교환 (swap)

> 파이썬의 변수는 참조형 변수이므로 가능

```python
a, b = 10, 20
a, b = b, a     # a 변수에 있는 값을 b 변수에 저장, b 변수에 있는 값을 a 변수에 저장
print(a, b)
20 10
```

- 변수 삭제

```python
del a       # del 명령어 사용
a
Traceback (most recent call last):
  File "<pyshell#16>", line 1, in <module>
    a
NameError: name 'a' is not defined      # 삭제 성공
```

## 5. 문자열 저장 변수

- 변수에 문자를 저장할 때 따옴표 사용

```python
name = "홍길동"
age = 23
print(name, age)
홍길동 23
```

- 문자열 변수와 문자열 값을 연결할 때 + 연산자 사용 가능

```python
address = "서울시 강남구"
print("저는 " + address + "에 삽니다.")
저는 서울시 강남구에 삽니다.
age = 23
print("저는 " + age + "살 입니다.")
Traceback (most recent call last):
  File "<pyshell#25>", line 1, in <module>
    print("저는 " + age + "살 입니다.")
TypeError: can only concatenate str (not "int") to str
# age는 정수 type. 문자열끼리만 연결 가능.
```

- 형변환

  - 정수 형태를 문자열로 변경시키면 연산이 불가능

  - 변수에 들어있는 정수값을 print문에서만 일회성으로 문자열로 변경시키는 작업

  - 다른 자료형을 지정된 자료형으로 일회성으로 변환시켜주는 함수
    
    - 정수: int
    
    - 실수: float
    
    - 문자열: str
    
    - 수식 완성: eval
    
      ```python
      age = 23
      print("저는 " + str(age) + "살 입니다.")
      저는 23살 입니다.
      ```
    
  - 입력 코드를 이용한 형변환의 이해

    ```python
    # 사용자로부터 수 1개를 입력받아 그 수 보다 10 증가한 값을 출력하는 프로그램
    su = int(input "숫자를 입력하세요: ")
    print('입력한 값 보다 10 증가한 값: ', su+10)
    ```

## 6. 상수

- 값이 변경되지 않는 저장공간
- 파이썬에서는 별도의 상수가 없음
- 변수와 구분하기 위해 전부 대문자로 사용
- 나중에 상수의 값을 변경해도 오류가 없음

```python
PI = 3.141592       # 개발자가 임의로 구성한 상수

r = 10
area = r*r*PI
print(area)
314.1592
```

```python
INT_RATE = 0.03     # 개발자가 임의로 구성한 상수

deposit = 10000
interst = deposit * INT_RATE
balance = deposit + interest
print(int(balance))
10300
```
