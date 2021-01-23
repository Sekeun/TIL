# 리스트

---

## 0. 개요

- 동일한 이름을 갖는 원소들의 연속 저장 영역
  - 자료의 집합: 여러 개의 값을 집합적으로 저장
- 리스트에 소속되는 각 값을 요소(element) 또는 원소라고 한다.
- 각 원소는 인덱스로 구분(0부터 시작)

```python
a = []	# 비어있는 리스트
b = [1, 2, 3]
c = ['Life', 'is', 'too', 'short']
d = [1, 2, ['python', 'play']]	# 이중 리스트
```

## 1. 특징

- 리스트의 크기는 가변적
- 다양한 종류의 데이터를 하나의 리스트 안에 저장 가능
- 하나의 변수에 여러 개의 값을 모아 놓은 것이어서 루프를 돌려 개별 요소를 쉽게 꺼낼 수 있음

## 2. 리스트의 인덱싱과 슬라이싱

### 인덱싱

```python
a = [1, 2, 3]
a[0]	# 첫번쨰 요소
1

a[0] + a[2]
4

b = [1, 2, 3, ['a', 'b', 'c']]

b[0]
1

b[-1]
['a', 'b', 'c']

b[-1][0]	# 이중 리스트에서 인덱싱
'a'
```

### 슬라이싱

```python
리스트[begin:end:step]
```

```python
# 중첩된 리스트에서의 슬라이싱
a = [1, 2, 3, ['a', 'b', 'c'], 4, 5]
a[2:5]
[3, ['a', 'b', 'c'], 4]
a[3][:2]
['a', 'b']
```

## 3. 리스트의 연산

### 리스트 더하기(+)

```python
a = [1, 2, 3]
b = [4, 5, 6]
a+b
[1, 2, 3, 4, 5, 6]
```

### 리스트 반복하기(*)

```python
a = [1, 2, 3]
a * 3
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

### 리스트 연산 오류 예시

- 정수와 문자열은 더할 수 없기에 형 오류 발생

```python
a = [1, 2, 3]

a[2]+"hi"
TypeError: unsupported operand type(s) for +: 'int' and 'str'

str(a[2]) + "hi"
3hi   
```

## 4. 리스트의 수정과 삭제

### 리스트에서 값 수정하기

- 리스트는 값을 수정하거나 삭제할 수 있다

```python
a = [1, 2, 3]
a[2] = 4
a
[1, 2, 4]
```

### 리스트 요소 삭제

- del 함수 사용

```python
a = [1, 2, 3]

del a[1]
a
[1, 3]

del a[1:]
a
[1]
```

## 5. 리스트의 복사

### 얕은 복사 (shallow copy)

- 실제 리스트는 복사되지 않고 참조값(주소)만 복사
- 복사본 리스트 요소의 값을 변경하면 원본 리스트 요소의 값도 변경

```python
scores = [10, 20, 30, 40]
values = scores         # 원본 보관

values[0] = 100         # 복사본 리스트의 요소값 변경

print(values)
[100, 20, 30, 40]
print(scores)           # 원본 값도 함께 변경
[100, 20, 30, 40]       # 실체 보관이 아닌 주소를 복사한 것
```

### 깊은 복사 (deep copy)

- 리스트의 복사본을 새로 생성하여 반환
- 원본 리스트의 데이터를 다른 곳에 한번 더 저장한 후 주소를 반환
- 연산자 `=` 로는 불가능

```python
# list 또는 deepcopy() 함수 사용
# 복사본 리스트의 값을 변경해도 원본 리스트의 값은 변경 x

scores = [1, 2, 3, 4, 5]
values = list(scores)

values[0] = 100

print(values)
[100, 2, 3, 4, 5]
print(socres)
[1, 2, 3, 4, 5]

import copy

a = ['a', 'b', 'c']
b = copy.deepcopy(a)

b[0] = 1
print(a)
['a', 'b', 'c']
print(b)
[1, 'b', 'c']
```

## 6. 리스트 컴프리헨션 (List Comprehension)

```python
# 다음 문법으로 요소의 집합을 정의
수식 for 변수 in 리스트 (if 조건)	# if문 생략 가능
```

## 7. 리스트 관리 함수들

### 내장함수 vs 메소드

1. 내장 함수

   - 함수: 특정 기능을 수행하는 코드 집합

   - 내장 함수: 파이썬에 이미 만들어져 있는 함수들

   - print() / len()

   - 사용법: print(변수(객체)), len(리스트)

     ```python
     print(names)
     ```

2. 메소드

   - 함수와 같은 코드 집합이지만 클래스의 멤버로 객체를 통해서만 사용 가능

   - append() / insert() / remove() / count() ..

   - 사용법: 객체.메소드

     ```python
     a.append(5)
     ```

### 삽입

- 리스트는 문자열과 달리 변경이 가능하다.
- `append` 인수로 전달한 요소를 리스트의 끝에 덧붙여 추가
- `insert` 삽입할 위치와 요소값을 전달받아 리스트의 중간에 삽입

```python
nums = [1, 2, 3, 4]
nums.append(5)
nums.insert(2, 99)
print(nums)
[1, 2, 99, 3, 4, 5]

nums = [1, 2, 3, 4, 5, 6]
nums.insert(len(num), 7)
print(nums)
[1, 2, 3, 4, 5, 6, 7]
# len(num)을 활용해 끝에 추가

nums.insert(999, 8)
print(nums)
[1, 2, 3, 4, 5, 6, 7, 8]
# 기존 인덱스+1 까지의 위치가 아니면 해당 위치가 없더라도 마지막에 삽입
```

- 여러 요소를 한꺼번에 삽입할 때는 범위에 리스트를 대입

```python
nums = [1, 2, 3, 4]
nums[2:2] = [90, 91, 92]
print(nums)
[1, 2, 90, 91, 92, 3, 4]

nums = [1, 2, 3, 4]
nums[2] = [90, 91, 92]
print(nums) 
[1, 2, [90, 91, 92], 4]
```

- `extend`
  - 리스트에 다른 리스트를 추가하여 병합할 때 사용
  -  하위 리스트로 추가되는 `append()` , `insert()`와 차이 

```python
a = [1, 2, 3]
a.extend([4, 5])
print(a)
[1, 2, 3, 4, 5]
```

### 삭제

- `del` : 순서값을 지정하여 삭제하는 명령

  - 지정한 위치의 요소를 지움

  ```python
  score = [88, 95, 70, 100, 99, 80]
  
  # del( ) : 함수 형식 호출
  del(score[1])
  print(score)
  [88, 70, 100, 99, 80]
  # del 요소의 위치
  del score[0]
  [70, 100, 99, 80]
  ```

- 대상을 선택하는 방법에 따라 메서드를 골라 사용

  - `remove` : 리스트에서 값이 해당되는 요소를 찾아서 제거

    - `리스트.remove(값)`
    - 동일한 값이 있는 경우 첫번째 값만 삭제
    - 여러 개를 삭제해야할 경우 제거해야하는 원소의 수를 확인 후 for 문 이용
    - 제거 요소가 없을 시 에러 발생

    ```python
    n = [1, 3, 2, 3, 4, 5]
    n.remove(3)
    print(n)
    [1, 2, 3, 4, 5]
    ```

  - `pop`  

    - `리스트.pop()`: 리스트의 마지막 요소를 반환하고 삭제
      - 리스트가 비어있을 시 에러 발생

    ```python
    x = ['a', 'b', 'c', 'd']
    y = x.pop()     # 마지막 요소를 반환하기 때문에 그 값을 변수에 저장
    print(y)
    d
    print(x)
    ['a', 'b', 'c', 'd']
    ```

    - `리스트.pop(인덱스)` : 인덱스 위치에 있는 요소를 반환하고 삭제

    ```python
    avengers = ['아이언맨', '헐크', '토르', '캡틴아메리카']
    h = heroes.pop(2)
    print(heroes)
    ['아이언맨', '토르', '캡틴아메리카']
    print(h)
    헐크
    ```

### 정렬

- `sort()` : 리스트를 정렬하며 요소의 순서가 조정되어 원본 리스트를 변경

```python
scores = [90, 78, 87, 65, 77]
scores.sort()           # 기본 오름차순 정렬
print(scores)
[65, 77, 78, 87, 90]

scores = [90, 78, 87, 65, 77]
scores.sort(reverse)    # 내림차순 정렬
print(scores)
[90, 87, 78, 77, 65]
```
```python
# 영문자는 대문자~소문자 순으로 정렬 (A~Z, a~z)
char = ['A', 'B', 'Z', 'c', 'j']
char.sort()
print(char)
['c', 'j', 'A', 'B', 'Z']

# 영문 대소문자 구분 없이 오름차순으로 정렬
char = ['b', 'A', 'd', 'C']
char.sort(key=str.lower)
print(char)
['A', 'b', 'C', 'd']

# 영문 대소분자 구분 없이 내림차순으로 정렬
char = ['b', 'A', 'd', 'C']
char.sort(key=str.lower, reverse=True)
print(char)
['d', 'C', 'b', 'A']
```

- `reverse()` : 정렬이 아닌 역순으로 순서를 변경, sort와 마찬가지로 원본 리스트를 변경

```python
scores = [90, 78, 81, 64, 89]
scores.reverse()        # 내림차순 정렬
print(scores)
[90, 89, 81, 78, 64]
```

- 문자열 정렬

```python
# 첫 문자를 기준으로 정렬
color = ['oraNge', 'Blue', 'Green', 'Red', 'blacK']
color.sort()
print(color)
['Blue', 'Green', 'Red', 'blacK', 'oraNge']

color = ['oraNge', 'Blue', 'Green', 'Red', 'blacK']
color.sort(key=str.lower)
print(color)
['blacK', 'Blue', 'Green', 'oraNge', 'Red']
```

- `sorted()` : 원본을 유지하면서 정렬된 새로운 리스트를 반환

```python
a = [3, 5, 1, 2, 4]
b = sorted(a)

print('a: ', a)
print('b: ', b)
a:  [3, 5, 1, 2, 4]
b:  [1, 2, 3, 4, 5]
```

### 검색

- `index()` : 특정 요소의 위치를 찾으며, 발견되지 않을 경우 에러 발생 
- `count()` : 특정 요소값의 개수를 조사

```python
score = [88, 95, 70, 100, 99, 80, 78]
perfect = score.index(100)
print("만점 받은 학생은"+ str(perfect)+"번입니다.")
pernm = score.count(100)
print("만점자 수는"+str(pernum)+"번입니다.")
만점 받은 학생은 3번 입니다.
만점자 수는 1번 입니다.
```

- `len()` / `max` / `min` 

```python
score = [88, 95, 70, 100, 99, 70]
print("학생 수는 %d명 입니다." %len(score))     # 리스트의 길이 조사
print("최고 점수는 %d점 입니다." %max(score))    # 리스트의 요소 중 최댓값 반환
print("최저 점수는 %d점 입니다." %min(score))    # 리스트의 요소 중 최솟값 반환
학생 수는 6명 입니다.
최고 점수는 100점 입니다.
최저 점수는 70점 입니다.
```

```python
# 문자는 아스키 코드 값으로 비교
n = ['c', 'a', 'D', 'A', 'b']
'''
A(65) a(97)
B(66) b(98)
C(67) c(99)
D(68)
'''
print('최대: ', max(n))
print('최소: ', min(n))
최대:  c
최소:  A
```

- `in` /  `not in`  : 요소가 있는지(없는지) 검사할 때 사용

```python
ans = input("결제 하시겠습니까? ")
if ans in ['yes', 'y', 'ok', '예', '당근']:
  print("구입해주셔서 감사합니다.")
else :
  print("안녕히 가세요.")
```

- 일치 검사
  - 비교 연산자를 사용하여 2개의 리스트를 비교
  - `==` / `!=` / `>` 등
  - 첫번째 요소부터 비교 시작
  - 첫번째 요소의 비교에서 결과가 `False` 이면 더 비교않고 종료
  - 리스트 안의 모든 요소 비교 결과가 `True` 일 경우 전체 결과 `True`

