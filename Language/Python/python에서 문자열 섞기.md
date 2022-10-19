Password Generator를 만드는 도중 문자열을 섞어야 하는 상황이 발생했는데 이 부분을 몰라서 찾아보게 되었습니다. 

“[정우로그](https://stackgokr.com/detail/6954)” 라는 좋은 블로그에서 문자열을 섞는 방법에 대해서 여러개를 설명해 주었고 본인은 여러 방법 중  .join 함수와 random.sample를 이용해서 섞는 방식과 리스트에서 random.shuffle 후 다시 문자열로 변경하는 방식을 학습했습니다. 

코드로 보여드리자면

 

- **.join, random.sample**
    
    ```python
    import random
    s="abcdef123"
    result = ''.join(random.sample(s,len(s)))
    
    ```
    
- **.join, random.shuffle**
    
    ```python
    import random
    l = list(s)
    random.shuffle(l)
    result = ''.join(l)
    ```
    

### .join 함수

---

join 함수는 매개변수로 들어온 리스트에 있는 요소들을 합쳐서 하나의 문자열로 반환하는 함수

- **‘’.join(리스트)**를 이용하면 매개변수로 들어온[’a’,’b’,’c’] 이런 식의 리스트를 ‘abc’의 문자열로 합쳐서 반환
- **‘구분자’.join(리스트)**를 이용하면 리스트의 값과 값 사이에 ‘구분자’에 들어온 구분자를 넣어서 하나의 문자열로 합쳐줍니다. 
’_’.join([’a’,’b’,’c’]) 라 하면 “a_b_c” 와 같은 형태로 문자열을 만들어서 반환해줍니다.

### random.sample()함수

---

**sequence**에서 지정한 숫자만큼의 요소들을 랜덤으로 뽑아 **리스트로 반환**해주는 함수

```python
random.sample(sequence, k)
```

- **sequence:** 리스트, 집합, range() 등 random의 범위가 될 sequence 입력
- **k:** 반환될 리스트의 크기 입력

**활용예시**

- 5개의 과일 중 2개의 과일 랜덤으로 출력
    
    ```python
    import random
    mylist = ["apple", "banana", "cherry", "orange", "blueberry"]
    print(random.sample(mylist, k=2))
    
    #Result
    ['orange', 'blueberry'] # 결과는 다르게 나올 수 있다. 
    ```
    
- 0에서 99 중 10개의 숫자를 랜덤으로 출력
    
    ```python
    import random
    data_list = random.sample(range(100), 10)
    print(data_list)
    
    #Result
    [75, 20, 98, 60, 5, 47, 4, 21, 90, 52] # 결과는 다르게 나올 수 있다
    ```
    

### random.shuffle

---

리스트의 순서를 무작위로 반환해주는 함수

- 예시
    
    ```python
    import random
    
    list = ["ice cream", "pancakes", "brownies", "cookies", "candy"]
    
    random.shuffle(list)
    
    print(list)
    
    #Result
    ['cookies', 'pancakes', 'ice cream', 'brownies', 'candy'] # 순서의 결과가 다르게 나올 수 있다. 
    ```