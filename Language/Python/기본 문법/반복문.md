### 시퀀스 자료형(Sequence Data Tytpe)

---

- 순서가 있는 자료형
    - 리스트
    - 문자열
    - range 객체
    - 튜플, 딕셔너리

### for 사용법

---

**for** 변수 **in** 시퀀스 자료:

 명령문 

```python
# 예시
for a in [1,2,3,4]:
	print a 
```

### range 명령어

---

range(10) 
⇒ 0~9 까지 숫자를 포함하는 range 객체를 만들어 준다. 

### for 실습

---

```python
# 반복문
# : 반복해서 명령을 사용하고 싶을 때 

# for 문
# - 리스트 

champions = ["티모","이즈리얼","리신"]

for chamption in champions:
    print("선택한 챔피언은",chamption, "입니다.")
```

```python
# - 문자열 사용

fighting_message = "자신감을 가지자! 나에게 한계란 없다!"

for word in fighting_message:
    print(word)

# -range 객체 사용 
# range(10) -> 0~9까지 숫자를 포함하는 객체이다. 
# range(시작, 끝+1)
# range(시작, 끝+1 , 단계)

for i in range(1,10,2):
    print(i)
```

### While 사용법

---

for문을 사용할 때는 반복할 횟수가 정해졌을 때 사용을 하고

While 문을 사용할 때는 반복할 횟수가 정해지지 않을 때 사용을 한다. 

초기식
While 조건식:
 반복할 명령
 증감식 

```python
i = o 
while i <10:
print(i,"번째 다짐, 나는 할 수 있다!")
i+=1
```

### 무한루프와 break

---

While true:
   반복할 명령
   if 조건식:
      break

```python
while true:
	x = input("종료하려면 exit을 입력하세요>>>")
if x == "exit":
	break
```

### While 실습

---

```python
# while
# : 보통 반복 횟수가 정해지지 않았을 때 사용한다. 

i = 0
while i < 10:
    print(i,"번째 다짐, 나는 할 수 있다!")
    i += 1
```

```python
# 무한 루프
# : 조건식에 True를 넣어서 항상 반복되게 만든 것.

while True:
    x = input("종료하려면 exit를 입력하세요>>>")
    if x == "exit":
        break
```

### 반복문 실습 문제 1)

---

1.  구구단 출력 프로그램을 만들어보자. 프로그램 사용자로부터 출력할 단을 입력 받고, 해당 구구단을 출력하는 프로그램이다.

```python
numbers = int(input("몇 단을 출력할까요?>>>"))

# 1
forwhile True:
    print("[메뉴를 입력하세요]")
    x = int(input("1. 게임시작 2. 랭킹보기 3. 게임종료 >>>"))
    if x == 1:
        print("-> 게임을 시작합니다.")
    elif x == 2:
        print("-> 실시간 랭킹")
    elif x == 3: 
        print("-> 게임을 종료합니다.")
        break
    else:
        print("-> 다시 입력해주세요.") i in range(1,10):
    print(str(x)+ "*" + str(i) + "=" + str(x*i))

# 2
for i in range(1,10):
    print(x,"*",i,"=",x*i)
```

### 반복문 실습 문제 2)

---

1. 메뉴 입력 게임 

```python
while True:
    print("[메뉴를 입력하세요]")
    x = int(input("1. 게임시작 2. 랭킹보기 3. 게임종료 >>>"))
    if x == 1:
        print("-> 게임을 시작합니다.")
    elif x == 2:
        print("-> 실시간 랭킹")
    elif x == 3: 
        print("-> 게임을 종료합니다.")
        break
    else:
        print("-> 다시 입력해주세요.")
```

### 반복문 실습 문제 3)

---

1. 성민은 연세대학교에 Lily라는 이름의 교환학생과 친해지케 되었다. 영어를 잘하지 못했던 성민은, Lily에게 한국어를 가르쳐 주기 위해 한국어 연습 프로그램을 만들게 되었다.

```python
Learning_Koreans = ["사랑해","귀엽다", "고마워", "행복해"]

for Learning_Korean in Learning_Koreans:
    print(Learning_Korean)
    data = input("위와 같은 단어를 꼭 적어야해>>>>")
    if data != Learning_Korean:
        print("틀렸어 안녕")
        break
```

### 반복문 실습 문제 4)

---

1. 3번의 업그레이드 버전: 맞힌 개수와 틀린 개수를 계산 

```python
Learning_Koreans = ["사랑해","귀엽다", "고마워", "행복해"]

score = 0

for Learning_Korean in Learning_Koreans:
    print(Learning_Korean)
    data = input("위와 같은 단어를 꼭 적어야해>>>>")
    if data == Learning_Korean:
        print("맞았어")
        score += 1
    else:
        print("틀렸어")

print("전체 문제 개수:",len(Learning_Koreans))
print("맞힌 문제 개수:",score )
print("틀린 문제 개수:",len(Learning_Koreans) - score )
```