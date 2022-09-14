### 파일 입출력을 사용하는 이유

---

- 파일로부터 데이터를 읽어와서 프로그램에 사용하기 위해
- 프로그램에서 만든 데이터를 파일형태로 저장하기 위해

### 파일 열기 모드

---

- w: 쓰기 모드(write)
- a: 추가 모드 (append)
- r: 읽기 모드 (read)
    - **w와 a의 차이: w는 덮어쓰기, a는 이어쓰기**

### 파일 쓰기

---

- 파일객체 = open("파일이름","파일모드")
- 파일객체.write(데이터)
- 파일객체.close()

```python
file = open("data.txt","w")
file.write("1.스타트코딩과 함께 파이썬 공부")
file.close()
```

### 파일 추가

---

- 파일객체 = open("파일이름","파일모드")
- 파일객체.write(데이터)
- 파일객체.close()

```python
file = open("data.txt","a")
file.write("비전공자도 쉽게 배울 수 있습니다.")
file.close()
```

### 파일 읽기

---

- 파일객체 = open("파일이름","파일모드")
- 변수 = 파일객체.read()
- 파일객체.close()

```python
file = open("data.txt","r")
data = file.read()
file.close()
```

### 파일 입출력 기본 예제

---

```python
# 1. 파일 쓰기

file = open("./myvenv/Chapter10/data.txt", "w", encoding = "utf8")
file.write("1. 스타트코딩과 함께 파이썬 공부")
file.close()

# 2. 파일 추가하기 

file = open("./myvenv/Chapter10/data.txt", "a", encoding = "utf8")
file.write("\n2. 비전공자도 정말 쉽게 배울 수 있습니다.")
file.close

# 3. 파일 읽기

file = open("./myvenv/Chapter10/data.txt", "r", encoding = "utf8")

# 3.1 파일 전체 읽기
data = file.read()
print(data)
file.close()

# 3.2 파일 한줄 읽기 

while True:
    data = file.readline()
    print(data, end="")
    if data =="":
        break
file.close()
```

### Pickle 모듈

---

- 파일에 파이썬 객체 저장하기
    
    ```python
    import pickle
    data = {
    			"목표1" : "매일 팔굽혀펴기 100회",
    			"목표2" : "매일 코딩 공부 1시간"
    }
    file = open("data.pickle","wb")
    pickle.dump(data,file)
    file.close()
    ```
    
- 파일로부터 파이썬 객체 읽기
    
    ```python
    import pickle
    file = open("data.pickle","rb")
    data = pickle.load(file)
    print(data)
    file.close()
    ```
    

### with 구문

---

- **with 구문 사용 x**
    
    ```python
    file = open("data.txt","r")
    data = file.read()
    file.close()
    ```
    
- **with 구문 사용 o**
    
    ```python
    with open("data.txt","r")as file:
    data = file.read()
    ```
    

### CSV 파일이란?

---

- csv(comma-separated values)
    - 데이터가 콤마로 구분된 텍스트 파일 형식
- student.csv
    - 이름,반,번호
    - 재석,1,20
    - 홍철,3,8
    - 형돈,5,32

### CSV 파일 입출력 사용방법

---

- csv 파일쓰기
    
    ```python
    import csv
    
    data = [
    			["이름","반","번호"],
    			["재석",1,20],
    			["홍철",3,8],
    			["형돈",5,32]
    ]
    ```
    

```python
file = open("student.csv","w")
writer = csv.writer(file)
for d in data:
		writer.writerow(d)
file.close()
```

- csv 파일 읽기
    
    ```python
    import csv
    
    file = open("student.csv","r")
    reader = csv.reader(file)
    for d in reader:
    		print(d)
    file.close()
    ```