### 모듈의 개념

---

- 한 개의 완성된 프로그램 파일

### 파이썬 기본 모듈 사용방법

---

```python
import 모듈이름
모듈이름.변수
모듈이름.함수()
```

```python
import math
print(math.pi)
print(math.ceil(5.7)

##조금 더 간편히 표현##
from math import pi,ceil
print(pi)
print(ceil(5.7))
```

### 파이썬 모듈 사용 예제

---

```python
from math import pi,ceil
print(pi)
print(ceil(2.7))

#ceil 말고 c로 사용하고 싶을 때 **as**를 사용하면 된다. 
from math import pi,ceil as c
print(pi)
print(c(2.7))

#외부 모듈:다른 사람이 만든 파이썬 파일을 pip로 설치해서 사용
# pyautogui
# 터미널에 python -m pip install pyautogui 또는 pip install pyautogui를 작성하여 모듈 설치

import pyautogui as pg

pg.moveTo(500,500, duration=2) # 화면에 2초동안 마우스를를 500 500 위치로 마우스를 자동으로 이동
```

### 모듈 만들기 예제

---

```python
# 파일 이름: pay_module.py
# 결제 정보, 관리 모듈
# 변수 
version = 2.0

# 함수
def printAuthor():
    print("스타트 코딩")

# 클래스
class pay:
    def __init__(self, id, price, time):
        self.id = id
        self.price = price
        self.time = time
    def get_pay_info(self):
        return f"{self.time},{self.id},{self.price}"
```

```python
# 모듈 사용 

import pay_module

# 변수 사용
print(pay_module.version)

# 함수 사용

pay_module.printAuthor()

# 클래스 사용

pay_info = pay_module.pay("A102030", 13000, "2021-06-13")

print(pay_info.get_pay_info())
```

### 패키지의 개념

---

- **관련 있는 모듈을 하나의 폴더로 구성해 놓은 것**

### 패키지 사용 예제

---

- __init__.py
    
    ```python
    from . import character, item, monster
    ```
    
- character.py
    
    ```python
    def test():
        print("this is a character module")
    ```
    
- item.py
    
    ```python
    def test():
        print("this is a item module")
    ```
    
- monster.py
    
    ```python
    def test():
        print("this is a monster module")
    ```
    
- [main.py](http://main.py) ← 실제 패키지를 불러오는 부분
    
    ```python
    # 1. improt 패키지.모듈
    
    import unit.character as uc
    
    uc.test()
    
    # 2. from 패키지 import 모듈
    
    from unit import item
    
    item.test()
    
    # 3. import 패키지 import * => 패키지 안에 모든 모듈을 가져옴
    
    from unit import *
    
    character.test()
    item.test()
    monster.test()
    
    # 4. import 패키지 
    
    import unit
    unit.character.test()
    ```