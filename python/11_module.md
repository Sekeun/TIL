# 모듈

---

 ## 0. 개요

- 함수, 변수, 클래스 등을 모아놓은 파일 (.py)

### 사용법

- 하나의 파일에 모든 코드를 넣지 않고
- 함수, 변수, 클래스 단위로 별도의 파일을 만들어 놓은 뒤
- 필요할 때 `import` 해서 사용
- 모듈이 저장되어 있는 공간(폴더)을 경로로 등록해서 사용

### 함수 / 모듈 / 패키지의 포함 관계

![img](https://t1.daumcdn.net/cfile/tistory/9976BC4E5C6B98863E)

## 1. 모듈의 종류

- 표준 모듈: 파이썬 언어 패키지 안에 기본으로 포함되어 있는 모듈
- 사용자 정의 모듈: 개발자가 직접 정의한 모듈
- 써드파티 모듈: 다른 업체나 개인이 만들어서 제공하는 모듈

## 2.  모듈 선언 방법

### 모듈 전체 참조

```python
import 모듈명(파일명) : import math
import 모듈명 as 별칭 : import pandas as pd
# 모듈명이 길거나 모듈명이 동일한 경우 별칭 사용

모듈명.함수명: math.pow()
# 모듈 내 함수를 참조
```

### 모듈 내 일부 참조

```python
from 모듈명 import 변수명 or 함수명
# 예
from wordcloud import ImageColorGenerator

from 모듈명 import 변수명 or 함수명 as pd

from 모듈명 import *
# 모듈 내에서 '_'로 시작하는 스페셜 변수나 매직 메서드를 제외한 모든 것을 참조
```

## 3. 모듈 만들기

```python
# new_calc.py
# 사칙연산 모듈
# 사칙연산 함수 포함

def add(a, b):
    return a+b

def sub(a, b):
    return a-b

def mul(a, b):
    return a*b

def div(a, b):
    return a/b
```

## 4. 모듈 불러오기

```python
# 모듈 사용
# 사용할 모듈과 같은 폴더에 저장되어 있는 파일
import new_calc             # 모듈명만 import
from new_calc import sub    # 모듈 내 함수까지 import
a = new_calc.add(7, 4)      # 모듈명.함수명
print(a)
11
print(sub(7,4))             # 함수명 만으로 사용 가능
3
```

## 5. __main__ 함수

- 프로그램을 실행시켰을 때 `main()` 함수가 동작하는 것처럼 작성 가능
- 전체 프로그램이 `main()` 에 있는 순서대로 수행됨
- __name__ 변수 사용 (스페셜 변수 / 내장 변수)

```python
if __name__ == "__main__":
  input_name()
  show_name()
  
'''
직접 파일을 실행했을 떄, __name__ =="__main__"이 참이돼
if문의 다음 문장이 수행됨.

다른 파일에서 이 모듈을 불러서 사용할 때는 거짓이 되어
if문의 다음 문장이 수행되지 않음.
'''
```

### 함수를 사용한 프로그램 설계

1. 문제 분해
   - 문제를 한 번에 해결하려고 하지 않고 더 작은 크기의 문제들로 *분*해
   - 문제가 충분히 작아질 때까지 반복
2. 함수로 작성
   - 문제가 충분히 작아지면 각 문제를 함수로 작성
3. 함수 조립
   - 함수들을 조립해 최종 프로그램 완성