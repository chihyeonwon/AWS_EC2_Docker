## EC2 생성
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/24cc3f30-3d5e-4f36-9b49-34b26b58d167)
```
솔루션 탭의 가상 머신 시작을 눌러서 EC2 서비스로 들어간다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/4f90dab7-b40a-4eb1-b36a-01ce4c19e17f)
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/73c3b7bf-2a6e-4d90-b361-e88d6cdbffd8)
```
키 페어 파일을 생성하고 바탕화면에 키를 다운로드한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/c80ecff5-b14d-4270-86f2-07602aad0550)
```
Ubuntu Server 20.04 LTS (HVM), SSD Volumn Type을 선택한다. 
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/7ae42123-306f-4f3c-978e-e360e3b73c62)
```
인스턴스는 t2.micro 인스턴스를 선택한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/a2a3a26c-936a-450e-b7e8-b983bbd799aa)
```
스토리지는 30GiB의 범용 SSD(gp2)를 사용한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/6afbad25-3545-49ee-a915-994b2dd4869b)
```
키 페어는 아까 생성한 fullstack-recommender-key를 넣어준다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/7340756f-f9e8-465b-9b96-bb98c55e7307)
```
AMI 선택, 인스턴스 유형 선택, 스토리지 선택, 키 페어 선택등을 마치고 인스턴스 시작을 누른다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/15bcfb20-b398-413d-8cc1-f221bf37022e)
```
생성한 EC2 인스턴스가 정상적으로 실행 중인 것을 확인할 수 있다.
```

## EC2 환경 설정 및 배포 환경 설정

![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/dce9c887-1822-494a-ad09-5a4748e3f6bd)
```
인스턴스 ID에 오른쪽 클릭하여 연결이라는 메뉴를 클릭한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/ef5b94d4-b79b-4d48-b76f-8a7b788ccb42)
```
연결 정보를 확인하고 오른쪽 아래의 연결을 클릭한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/b938f82e-77d0-4256-b890-db9199dde82c)
```
연결이 되면 검정색 화면이 나타나고 이제 docker와 gitlab-runner 프로그램을 우분투 환경에 설치한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/46a48fb9-d350-42ff-a5dc-15389c1c8240)
```
curl 명령어를 이용해서 설치용 스크립트를 다운로드받아서 설치한다음 sudo 명령어로 스크립트를 실행한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/979dfedb-8240-45e0-831e-653a28812efe)
```
관리자 권한 없이 docker 명령어를 실행할 수 있도록하는 명령어를 실행한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/8af56889-4b7f-4828-9f8e-fe04e964ebce)
```
현재 실행되고 있는 docker 컨테이너를 확인할 수 있는 명령어를 실행한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/63965aab-c51b-4cf0-94a9-fec9b32c4954)
```
다음과 같이 나오면 정상적으로 docker가 설치된 것이다.
```


































