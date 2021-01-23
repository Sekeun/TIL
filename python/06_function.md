# 함수

---

## 0. 개요

- 특정 작업을 수행하는 코드의 집합

- 함수 사용의 이유
  1. 코드 재사용: 한 번 만들어 놓고 여러 번 사용
  2. 중복된 코드 제거: 동일 내용의 코드를 여러 번 적을 필요 없이 함수로 만들어 필요한 곳에서 사용
  3. 작업 분해: 복잡하고 긴 내용을 기능별로 분리해 함수로 만들어 사용
- 함수 사용의 장점
  1. 경제적 (코드 재사용)
  2. 프로그램 가독성 증대 (작업 분해)
  3. 프로그램의 유지 관리 용이
     - 변경 사항 발생 시 해당 함수만 수정 작업

## 1. 함수의 종류

### 내장함수 (Built-in-Function)

- 파이썬에 이미 만들어져 있는 함수들
- 형식에 맞춰 함수 이름만 호출해서 사용
  - `print()`, `input()`, `dir()`, ...
- 특정 객체를 통해 사용 가능한 함수 (메소드)
  - `문자열.sort()`, `문자열.split()`, `리스트.insert()`, ...

### 사용자 정의 함수

- 사용자가 임의로 생성해서 사용하는 함수

## 2. 함수의 구조

```python
def 함수명 (매개변수1, 매개변수2):
  수행 문장1
  수행 문장2
  반환값 (생략 가능)
  
# def : 함수 정의 키워드
# 매개변수: 함수로 전달되는 값을 받는 변수 (생략 가능)
# 반환값(return): 함수의 실행 결과를 호출원으로 돌려주는 값

# 예시
def sum(n1, n2):
  print(n1, n2)
  return n1 + n2

# 변수는 괄호가 없고: sum
# 함수는 괄호가 있다: sum()

print(10)
# print라는 함수를 호출학 매개변수의 값으로 10을 전달
```

## 3. 함수 이름

- 함수의 목적을 설명하는 동사
- 혹은 동사 + 명사를 사용 (예시)
  - square(num) : 정수를 제곱하는 함수
  - compute_average(list) : 평균을 구하는 함수
  - set_cursor_type(c) : 커서의 타입 설정
  - showResult() : 결과 출력

## 4. 함수 사용

- 함수를 사용하려면 함수를 호출(call)해야 한다.
- 함수 호출
  - 함수를 호출하기 전에 먼저 함수를 정의해야 한다.
  - 함수 이름을 적는다.
  - 함수는 호출하지 않으면 아무 일도 하지 않는다.

## 5. 인수와 매개변수

### 인수(argument)(또는 인자)

- 함수에게 실제로 전달되는 값
- 위치 인수 vs 키워드 인수
  - 위치 인수 (positional arguments) (일반적인 인수)
    - 함수 호출 시 위치에 의하여 구별하는 방식
    - 매개변수의 순서대로 인수를 전달하여 사용하는 경우
    - 순서대로 전달
    - `add(a, b, c)`
    - 호출: `add(10, 20, 30)`

  - 키워드 인수 (keyword arguments)
    - 인수들 앞에 키워드를 두어 인수를 구별하는 방식
    - 인수의 위치가 매개변수의 위치와 달라도 됨
    - `add(a, b, c)`
    - 호출: `add(c=30, a=10, b=20)`

  - 주의사항
    - 위치 인수와 키워드 인수를 섞어서 사용해도 되지만
    - 우치ㅣ 인수를 키워드 인수 보다 앞에 두어야 한다
    - 호출: `add(10, c=30, b=20)` : 위치 인수가 앞에 와야 함
    - 호출: `add(c=30, 10, 20)` : 불가능

### 매개변수(parameter)

- 함수로 전달된 값을 받는 변수
- Default 매개변수

```python
def calc(n1, n2):	# 두 개의 파라미터를 요구하는 함수
  return n1+n2

calc(2, 3)				# 인수 2개를 반드시 전달
calc(2)						# 하나만 입력했을 때 에러 발생
TypeError: calc() missing 1 required positional argument: 'n2'
    
# 매개변수에 기본값을 지정할 수 있다.
print('abc', end='0')
abc0
print('abc')
abc

# default 매개변수를 사용할 수 있다.
def greet(name, msg='안녕!'):
  print(name+', '+msg)
  
# 호출 시 매개변수 지정
greet('Oh', 'hello')
greet('Oh')
Oh, hello			 # 호출시 전달된 인수가 사용
Oh, 안녕!				# 매개변수의 기본값이 사용
```

- 가변길이 매개변수 (Variadic Prameter)

  - variable length parameter

  - 1개의 매개변수로 개수가 정해지지 않은 여러 개의 값을 전달 받을 때 사용하는 매개변수

  - *args

    - arguments의 약자
    - 인수 값을 받음

    ```python
    def sum(*args):
      
    sum(1, 2, 3)	#	인수가 3개
    sum(1, 2, 3, 4, 5)	# 인수가 5개
    
    # *args 대신 다른 이름 사용 가능
    # 예) *names, *numbers, ...
    ```

  - **kargs

    - Keyword arguments의 약자
    - key=value 값을 받음
    - end = ' '

    ```python
    def info(**kwargs):
      
    info(id = "abcd", name = "kim")	# 인수가 2개
    info(id = "abcd", name = "Lee", age = 30)	# 인수가 3개
    
    # **kwargs 대신 다른 이름 사용 가능
    # 예) **names, **numbers, ...
    ```


### 지역변수 vs 전역변수

- 지역변수 (local variable)

  - 함수 내부에서 정의된 변수
  - 함수 안에서만 사용 가능
  - 함수 호출 시 생성하고 함수 종료시 소멸되어 더이상 사용할 수 없음

  ```python
  def show() :
      a=1         # 지역변수(show() 안에서만 사용) - 변수 생성
      print(a)    # 코드 실행 후 변수 사라짐
  
  print(a)        # 함수 외부이므로 사용 불가
  ```

  - 함수의 매개변수 또한 지역 변수
  - 외부로부터 값을 전달 받아 함수 내부에서만 사용하는 변수

  ```python
  def show(a):	# 매개변수 a: 전달되는 1을 받음
    a = a + 1		# a는 함수 내에서 지역변수로 사용됨
    print(a)		# 2 출력
    
  show(1)
  2
  print(a)			# error: a는 함수 내에서만 사용 가능
  NameError: name 'a' is not defined
  ```

- 전역변수

  - 함수 외부에서 정의된 변수
  - 프로그램 내 모든 곳에서 사용 가능
  - 함수 내에서 전역변수 값을 변경하려면 `global` 키워드 사용

  ```python
  a = 1		# 함수 밖에서 정의된 전역변수 0
  def show():
    c = a+p
    print(a)
    print(b)
    print(c)
  
  def add():
    print(a)
    print(b)
    
  b = 2		# 함수 밖에서 정의된 전역변수 b
  show()
  add()
  print(a)
  print(b)
  ```

- 매개변수의 값으로 리스트를 전달했을 경우

  ```python
  # 함수에서 리스트 요소 변경시 원본 리스트도 변경
  
  def show_list(my_list):
    print('전달된 리스트 변경 없음:', my_list)
    my_list[0] = 10	#	첫번째 요소 변경
    print("첫번째 요소 변경 후:", my_list)
    print('1. id(함수내-매개변수):')
  ```

  

