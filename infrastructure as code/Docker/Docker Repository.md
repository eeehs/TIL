### Docker Image

---

**docker run nginx**를 실행할 때  

default로 **docker run docker.io/nginx/nginx**  이렇게 실행되는 것과 같다. 

> docker.io ⇒ Registry
> 

> nginx ⇒ User Account
> 

> nginx ⇒ image Repository
> 

이렇게 구성이 된다. 

따라서 어떠한 컨테이너로 실행할 때 따로 Registry와 User Account를 기입하지 않는다면 

자동으로 Registry는 docker.io로 적용이 되고 User Account는 image Repository와 같게 설정이 되면서 실행이 된다. 

### Docker image tag 변경

---

기존의 Docker 이미지명을 새로운 이름으로 변경하거나, 새로운 태그명을 붙일 때 docker image tag 명령을 사용.

**동일한 이미지가 새로운 이름의 이미지로 복사.**

> **docker image tag <기존의 이미지명>:<기존의 태그명> <새로운 이미지명>:<새로운 태그명>**
>