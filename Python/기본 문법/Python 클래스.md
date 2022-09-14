### 클래스와 객체의 개념

---

- 클래스
    - 객체를 만들기 위한 **설계도**
- 객체
    - 설계도로부터 만들어낸 **제품**
    

- **속성은 클래스를 설명하는 특징**
- **메서드는 동작을 나타냄**

### 클래스 만들기

---

```python
class 클래스이름:
	def 메서드이름(self):
		명령블록
```

```python
class Monster:
	def say(self):
		print("나는 몬스터다")
	
```

### 클래스 호출하기

---

```python
인스턴스 = 클래스이름()
인스턴스.메서드()
```

```python
goblin = Monster()
goblin.say()
```

**인스턴스는 현재 레벨에서는 그냥 객체라고 보면 이해하기 쉽다.**

### 속성 추가하기

---

- Monster 클래스에 속성을 추가해 봅시다.
    1. 체력
    2. 공격력
    3. 이동속도

```python
class Monster:
	def__init__(self,health,attack,speed):
		self.health = health
		self.attack = attack
		self.speed  = speed

goblin = Monster(800,120,300)
wolf   = Monster(1500,200,350)
```

### 메서드 추가하기

---

- Monster 클래스에 메서드를 추가해 봅시다.
    1. 체력 감소하기
    2. 체력가져오기

```python
class Monster:
	def__init__(self,health,attack,speed):
		self.health = health
		self.attack = attack
		self.speed  = speed
	def decrease_health(self,num):
			self.health -= num 
	def get_health(self):
			return self.health

goblin = Monster(800,120,300)

goblin.decrease health(100)
print(goblin.get_health())
```

### 상속의 개념

---


**클래스들에 중복된 코드를 제거하고 유지보수를 편하게 하기 위해서 사용한다.**

**자식클래스는 부모클래스한테 있는 속성과 메서드를 그대로 가져올수 있다**

### 상속 사용방법

---

- **부모 클래스 정의**
    
    ```python
    class Monster:
    	def__init__(self,health,attack,speed):
    		self.health = health
    		self.attack = attack
    		self.speed  = speed
    	def move(self):
    			print("지상에서 이동하기")
    ```
    

```python
#속성
1. 이름
2. 체력
3. 공격력
#메서드
1. 이동하기
```

- **자식 클래스 정의**

```python
class Wolf(Monster):
	pass

class Shark(Monster):
	def move(self):
			print("헤엄치기")

class Dragon(Monster):
	def move(self):
			print("날기")
```

```python
#속성(Monster로 부터 상속받은)
1. 이름
2. 체력
3. 공격력
#메서드 오버라이딩: 메서드 재정의
shark
1. 헤엄치기
dragon
1. 날기 
```

- **예제**

```python
class Monster:
    def __init__(self, name, health, attack):
        self.name = name
				self.health = health
        self.attack = attack
        
    def move(self):
        print(f"[{self.name}] 지상에서 이동하기")

class Wolf(Monster):
    pass
class Shark(Monster):
    def move(self):
        print(f"[{self.name}] 헤엄치기")
class Dragon(Monster):
    def move(self):
        print(f"[{self.name}] 날기")

wolf = Wolf("울프", 1500, 200)
wolf.move()

shark = Shark("샤크", 3000, 400)
shark.move()

dragon = Dragon("드래곤", 8000, 800)
dragon.move()
```

### 클래스 실습 문제

---

```python
class item:
    def __init__(self, name, price, weight, isdropable):
        self.name = name
        self.price = price
        self.weight = weight
        self.isdropable = isdropable
    
    def sale(self):
        print(f"[{self.name}] 판매가격은 [{self.price}]")

    def discard(self):
        if self.isdropable:
            print(f"[{self.name}] 버렸습니다.")
        else:
            print(f"[{self.name}] 버릴 수 없습니다.")

class Wearableitem(item):  
    def __init__(self, name, price, weight, isdropable, effect):
        super().__init__(name, price, weight, isdropable)   
        self.effect = effect
    def wear(self):
        print(f"[{self.name}] 착용했습니다. {self.effect}")

class Usableitem(item):
    def __init__(self, name, price, weight, isdropable, effect):
        super().__init__(name, price, weight, isdropable)
        self.effect = effect
    def use(self):
        print(f"[{self.name}] 사용했습니다. {self.effect}")

#인스턴스  생성
sword = Wearableitem("이가닌자의검", 30000, 3.5, True, "체력 5000증가 ,마력 5000증가")
sword.wear()
sword.sale()
sword.discard()

potion = Usableitem("신비한 투명물약",150000,0.1, False,"투명효과 30초 지속")
potion.discard()
potion.sale()
potion.use()
```