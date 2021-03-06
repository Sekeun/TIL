# 리터럴 vs 식별자

---

## 1. 리터럴 (literal)

- 고정된 값

- 변수에 저장되는 값

  ```python
  x = 30		# 30: 리터럴
  ```


### 종류

- 정수 리터럴

  - 0b로 시작되면 2진수

  - 0o로 시작되면 8진수

  - 0~9로 시작되면 10진수 (소수점이 없는 정수)

  - 0x로 시작되면 16진수

    ```python
    a = 0b1010          # 2진수
    b = 0o123           # 8진수
    c = 300             # 10진수 (10진수 중 소수점이 없는 정수)
    d = 0x123ffc        # 16진수
    print(a, b, c, d)   # 10진수로 변환해서 출력
    10 83 300 1196028
    ```

- 실수 리터럴

  - 소수점이 있는 실수

  - e를 포함하는 지수

    ```python
    a = 3.14            # 소수점이 있는 실수
    b = 1.234e2         #	e를 포함하는 지수
    print(a, b)         # 지수표현을 숫자로 변환해 출력
    3.14 123.4
    ```

- 문자 리터럴 (한 글자)

  - 따옴표로 묶은 하나의 문자

    ```python
    'A'		# 'A': 문자 리터럴
    ```

- 문자열 리터럴 (여러 글자)

  - 따옴표로 묶은 일련의 문자

  - 작은 따옴표, 큰 따옴표, 삼중 따옴표 모두 사용 가능

    ```python
    # "홍길동": 문자열 리터럴
    name = "홍길동"						
    print(name)
    홍길동
    
    # "파이썬 프로그래밍": 문자열 리터럴
    str = "파이썬 프로그래밍"
    print(str)
    파이썬 프로그래밍
    
    # 줄바꾸기를 할 때 삼중 따움표 사용	
    str2 = '''제 이름은\		
    홍길동입니다.'''										
    print(str2)
    제이름은
    홍길동입니다.
    
    # 여러줄 주석을 사용할 때 삼중 따옴표 사용
    '''여러줄 주석을 처리할 때		
    삼중 따옴표를 사용합니다.
    문자열로 표시되지만 사용하지 않고
    컴퓨터가 인지만 하므로
    주석과 같은 효과를
    볼 수 있다'''
    ```

- 논리 리터럴

  - True, False 값

    ```python
    t = True        # True, False: 문자 리터럴
    f = False
    print(t, f)
    True False
    ```

- 특수 리터럴

  - None

  - 값(객체)이 없음

    ```python
    abc = None      # None:	특수 리터럴
    type(abc)
    <class 'NoneType'>
    
    phone = ''
    print(phone)
                    # 값이 없음 
    type(phone)
    <class 'str'>   # 아무 값이 없음에도 따옴표로 구분을 지으면 변수의 형태가 결정 (문자열)
                    # 특수 리터럴을 사용해야 형태가 NoneType으로 설정됨
    ```

## 2. 식별자 (identifier)

- 다른 것과 구분하기 위해 사용되는 이름

  ```python
  PI = 3.141592     # PI: 식별자
  ```

  



