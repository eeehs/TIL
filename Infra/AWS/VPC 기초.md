## What is VPC

---

Amazon Virtual Private Cloud(VPC)를 이용하면 사용자가 정의한 가상 네트워크로 AWS리소스를 시작할 수 있다. 
이 가상 네트워크는 AWS의 확장 가능한 인프라를 사용한다는 이점과 함께 고객의 자체 데이터 센터에서 운영하는 기존 네트워크와 매우 유사하다.

### VPC 특징

---

- 계정 생성 시 default로 vpc가 생성됨
- EC2,RDS,S3 등의 서비스 활용 가능
- 서브넷 구성
- 보안 설정(IP block ,inbount, outbound 설정)
- VPC Peering(VPC 간의 연결)
- IP 대역 지정 가능
- VPC는 하나의 Region에만 속할 수 있음**(다른 Region으로 확장 불가능)**

### VPC 구성 요소

---

- Availability Zone
    - 물리적으로 분리되어 있는 인프라가 모여 있는 데이터 센터
    - 각 AZ는 일정 거리 이상 떨어져 있음
    - 하나의 Region은 2개 이상의 AZ로 구성됨
    - 각 계정의 AZ는 다른 계정의 AZ와 다른 아이디를 부여받음
- Subnet(CIDR)
    - VPC의 하위 단위
    - 하나의 AZ에서만 생성 가능
    - 하나의 AZ에는 여러 개의 subent 생성 가능
    - Private subnet
        - 인터넷에 접근 불가능한 subnet
    - Public subnet
        - 인터넷에 접근 가능한 subnet
    - CIDR 블록을 통해 Subnet을 구분
    - CIDR
        - 하나의 VPC 내에 있는 여러 IP 주소를 각각 Subnet으로 분리 / 분배하는 방법
            - 1번째 서브넷 : 211.11.124.0/26 (211.11.124.0 ~ 211.11.124.63)
            - 2번째 서브넷 : 211.11.124.64/26 (211.11.124.64 ~ 211.11.124.127)
            - 3번째 서브넷 : 211.11.124.128/26 (211.11.124.128 ~ 211.11.124.191)
            - 4번째 서브넷 : 211.11.124.192/26 (211.11.124.192 ~ 211.11.124.255)
- Internet Gateway
    - 인터넷으로 나가는 통로
    - Private subnet은 IGW로 연결되어 있지 않음
- Network Access Control List / Security group
    - 보안 검문소
    - NACL → Stateless / SG → Stateful
    - Access Block은 NACL만 가능
- Route Table
    - 트래픽이 어디로 가야 할지 알려주는 테이블
    - VPC 생성 시 자동으로 생성
- NAT(Network Address Translation) instance / NAT gateway
    - Private subnet 안에 있는 Private instance가 외부의 인터넷과 통신하기 위한 방법
        - NAT Instance는 단일 Instance(EC2)
        - NAT Gateway는 aws에서 제공하는 서비스
    - NAT Instance는 Public Subnet에 있어야함
- Bastion Host
    - Private Instance에 접근하기 위한 수단
    - Public subnet 내에 위치하는 EC2
- VPC endpoint
    - AWS의 여러 서비스들과 VPC를 연결시켜주는 중간 매개체
        - AWS에서 VPC 바깥으로 트래픽이 나가지 않고 aws의  여러 서비스를 사용하게 만들어주는 서비스
        - Private subnet 같은 경우는 격리된 공간이므로 그 공간에서 aws의 다양한 서비스를 연결할 수있도록 지원하는 서비스
    - Interface Endpoint
        - Private ip를 만들어 서비스로 연결
    - Gateway Endpoint
        - 라우팅 테이블에서 경로의 대상으로 지정하여 사용