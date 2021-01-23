# 자료형 (data type)

---

## 파이썬이 처리하는 자료형

- 수치형

  - 정수 (int)

    ```python
    num = 100
    type(num)
    ```

  - 실수 (float)

    ```python
    PI = 3.14
    type(PI)
    ```

- 문자열 (str)

  ```python
  name = "홍길동"
  type(PI)
  ```

- 진위형 (boolean type)

  ```python
  done = True
  type(done)
  ```

- 파이썬에서 변수는 지정된 자료형이 없음 (가변 자료형)

- 지정한 값에 따라 변수의 자료형이 정해짐 (동적 타이핑)

  ```python
  a = 100
  type(a)		# class int
  
  a = 'hello'
  type(a)		# class str
  ```