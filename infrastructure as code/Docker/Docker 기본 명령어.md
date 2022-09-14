### Run - Start a Container

---

- **docker run** 명령어는 이미지로부터 컨테이너를 실행할 때 사용
    
    ⇒ docker run nginx 
    

### Ps - list Containers

---

- **docker ps** 명령어는 실행되는 모든 컨테이너와 해당 컨테이너의 기본정보를 나열
- **docker ps -a** 명령어는 이미 멈췄거나 종료한 컨테이너까지 모두 출력

### Stop - stop a Container

---

- 실행 중인 컨테이너를 멈출 땐 **docker stop** 명령어를 사용
- 이 경우 컨테이너 ID 혹은 컨테이너 이름을 같이 입력
- 컨테이너 ID 혹은 컨테이너 이름을 모를 경우 **docker ps** 명령어로 확인 가능

### Rm - Remove a container

---

- **docker rm** 명령어를 통해 멈추거나 종료한 컨테이너를 영구적으로 삭제 가능

### images - List images

---

- **docker images** 명령어로 사용할 수 있는 이미지의 목록과 이미지의 크기 확인 가능

### rmi - Remove images

---

- 사용하지 않을 이미지를 삭제하려면 **docker rmi** 명령어를 실행
- 이미지를 삭제하려면 해당 이미지가 종속된 모든 컨테이너를 중단하거나 삭제해야함

### Pull - download an image

---

- docer run 명령어를 실행했을 때 이미지 다운로드를 기다리지 않기 위해 이미지만 다운로드해서 보관하려면 **docker pull** 명령어를 사용

### Exec - execute a command

---

- 특정 컨테이너의 파일 콘텐츠를 확인하려면 **docker exec [컨테이너 ID]** **[Command]**명령어를 사용
    - Ex. docker exec distracted_mcclintock cat /etc/hosts