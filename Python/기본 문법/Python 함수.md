### 함수를 사용하는 이유

---

- 재사용성이 좋아진다.
- 유지보수가 편리해진다.
- 가독성이 좋아진다.

### 함수의 기본 형태

---

```python
정의하기
	def 함수이름():
			명령블록
```

```python

def printHello():
		print("Hello")
```

⇒ **호출 방법 printHello()**

### 매개변수가 있는 함수

---

```python
def 함수이름(매개변수1,매개변수2):
		명령블록
```

⇒ 호출 방법 **함수이름(인자1,인자2)**

```python
def sum(a,b):
		print(a+b)
```

⇒ **호출 방법 sum(3,4)**

### 반환값이 있는 함수

---

```python
def 함수이름():
		명령블록
		return 반환값
```

```python
def getRandomNumber():
		number = random.randint(1,10)
		return number
```

### 매개변수와 반환값이 있는 함수

---

```python
def 함수이름(매개변수1,매개변수2):
		명령블록
		return 반환값
```

```python
def sum(a,b)
		result= a + b
		return result
```

### 함수 실습 문제 1)

---

숫자 세 개를 받아와 합계와 평균을 출력하는 함수 

```python
def pruntSumAvg(x,y,z):
    """
    세게의 숫자를 받아 합계와 평균을 출력하는 함수
    """
    total = x + y + z
    Avg   = total/3
    print("합계 :",total)
    print("평균 :",Avg)
    print(f"합계 :{total},평균 :{Avg}")
pruntSumAvg(10,20,30)
```

### 함수 실습 문제 2)

---

로또 예상 번호 추출 프로그램을 파이썬으로 작성하려고 한다. 
다음 조건에 따라 프로그램을 완성해보자.

(단, 숫자는 겹쳐서는 안된다.)

- 조건
    
    1. 로또 번호를 6개를 생성한다.
    
    2. 로또 번호는 1~45까지의 랜덤한 번호다.
    
    3. 6개의 숫자 모두 달라야 한다.
    
    4. getRandomNumber() 함수를 사용해서 구현한다.
    

```python
import random

def getRandomNumber():
    number = random.randint(1,45)
    return number

lotto_number = []

while len(lotto_number) < 6:
    A = getRandomNumber()
    if A not in lotto_number:
        lotto_number.append(A)
        lotto_number.sort()

print(lotto_number)
```