### How to create my own image?

---

1. OS - Ubuntu
2. Update apt repo
3. Install dependencies using apt
4. Install Python dependencies using pip
5. Copy source code to /opt folder
6. Run the web server using “flasck” command

- Dockerfile

```docker
FROM Ubuntu

RUN apt -get update && apt -get -y install python

RUN pip install flask flask-mysql

COPY . /opt/source-code

ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run
```

### Environment Variables

---

```python
## app.py
-
-
color = os.environ.get('APP_COLOR')
```

```docker
## Dockerfile 
export APP_COLOR=blue; python app.py 
```

- **color를 app에서 바꾸지 않고 dockfile에서 export 명령으로 색깔을 바꿀 수 있게 설정 가능**
- docker run -e APP_COLOR=blue simple-webapp-color

### inspect Environment Variable

---

- **docker inspect** 명령어를 사용해서 실행 중인 컨테이너의 property를 볼 수 있다.

- **이름:blue-app, 이미지:kodekloud/simple-webapp, 환경변수: appcolor=blue 인 컨테이너 실행**
    
    docker run -e APP_COLOR=blue --name blue-app kodekloud/simple-webapp
    

### CMD vs ENTRYPOINT

---

```docker
# CMD

FROM Ubuntu

CMD sleep 5 

```

- **하드코딩되어있어 sleep 시간을 변경 못함**
    
    CMD command param1
    
    CMD sleep 5
    
    CMD[”command”,”param1”]
    
    CMD[”sleep”,”5”]
    

```docker
# ENTRYPOINT

FROM Ubuntu

ENTRYPOINT ["sleep"]
```

- 명령어를 작성 시 sleep시간을 설정 가능
- docker run ubuntu-sleeper 10
- 명령어 입력 시 시간을 설정하지 않으면 오류 발생

```docker
# ENTRYPOINT

FROM Ubuntu

ENTRYPOINT ["sleep"]

CMD ["5"] 
```

- “docker run ubuntu-sleeper” 시간 설정 명령어를 입력하지않으면 CMD에 설정된 “5”가 작동
- 만약 “docker run ubuntu-sleeper 50” 으로 작성하면 **CMD는 미작동**

- **도커 실행할 때 실행 정보 알아내는 커멘드**
    - docker run python:3.6 cat /etc/*release