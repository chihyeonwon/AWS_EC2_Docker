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
## EC2 연결
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
## Docker 설치 방법
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
## gitlab-runner 설치 방법
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/1f831e4e-5a5a-4349-a8af-12bb4753759d)
```
gitlab-runner 공식 문서에서 안내하는 방식으로 설치한다.
Gitlab 리포지토리를 우분투에 등록하는 과정으로 다음 명령어를 실행한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/64cf9af8-0000-446d-b376-29df5bedcfd4)
```
You can now install packages라는 메시지가 나오면 Gitlab 리포지토리를 우분투에 등록이 완료된 것이다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/e3118c49-631e-43ca-990f-bc24d601f5f6)
```
이제 다음 명령어를 실행하여 gitlab-runner를 설치한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/bdfc9844-d438-41f8-90ff-dbe2aa1ba7cf)
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/dcbce113-d94d-476e-bba8-92046547fe03)
```
설치가 완료되고 다음 명령어로 설치가 제대로 되었는지 확인할 수 있다.
gitlab-runner: Service is running 이라는 메시지가 출력되면 성공이다.
```
## GitLab deploy branch 분리
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/5343e6e5-8f97-43c9-b672-33b90eae84ec)
```
VS Code에서 지금까지 변경한 모든 내용을 stage 상태로 업로드한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/892ee926-3f77-46b8-9fd9-2714cac838e7)
```
stage 상태가 되면 commit을 할 준비가 된 것이다. git commit을 입력하여 stage에 있는 내용을 모두 커밋한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/e006c758-d649-4d57-bcf9-b6dbcf721c5c)
```
git push를 하여 지금까지 했던 내용을 GitLab에 모두 업로드한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/3b271a72-8f22-422b-879f-ee9e612f413e)
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/d9a915b4-d9a3-435d-838a-fcdd3a43c9ba)
```
git create를 입력하고 브랜치 이름을 deploy로 생성한다. 이렇게 하면 로컬, 즉 내 컴퓨터에만 있는 브랜치인 deploy가 생성된다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/9433329a-48ce-4066-aeea-ed67e558373c)
```
deploy 브랜치를 푸시 과정을 통해서 GitLab에 업로드한다. upstream branch 경고는 무시하고 ok를 누른다.
브랜치만 따로 푸시하는 경우에는 stage -commit 과정을 따로 해줄 필요가 없다. 안에 들어 있는 내용은 바뀐 게 없기 때문이다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/a17e7a86-196e-4bc4-b073-ea58f16d5aa4)
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/3621bfbd-3c75-4822-a815-f1380d0e946f)
```
deploy 브랜치가 GitLab에 업로드 된 것을 확인할 수 있다.
```
## GitLab runner로 배포 자동화
1. gitlab-runner를 AWS EC2에 등록한다.
2. gitlab-runner를 실행할 .gitlab-ci.yml파일을 만든다.
3. 만든 백엔드 서버를 dockerize 하여 배포한다.

#### gitlab-runner 등록
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/afbcdbfc-31ee-4e3c-b2ef-a89cb4930ba1)
```
GitLab-Settings-CI/CD 메뉴에서 Runners 메뉴의 Expand를 눌러 확장하면 Registration Token을 확인할 수 있다.

토큰 값을 복사해준다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/f1dfa088-8f83-4037-ac55-f561791bd9d7)
```
EC2에 연결해서 다음 명령어로 gitlab-runner 등록을 시작한다.

Enter the GitLab instance URL에 https://gitlab.com/을 입력한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/39420ce2-afab-4ef2-8a2b-1e7063df74e1)
```
토큰을 입력하는 프롬프트에서 아까 Gitlab runner에서 복사해 두었던 토큰을 입력한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/da463134-1918-4f92-8718-aceb9b9b1073)
```
runner가 어떤 역할을 하는지 알아보기 쉽도록 지정하는 description 항목이다.
원하는 설명을 적으면 되는데 여기서 fullstack-api라고 작성한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/0f18916a-7e0b-4b5d-b9a4-58351c4a0634)
```
다음으로 tag를 입력하는 프롬프트가 나온다. 이 tags는 중요하다. 나중에 gitlab-runner의 tags를 이용해서
어떤 runner에 CI를 실행시킬 것인지 결정하기 때문이다.

통일된 코드를 가지기 위해서 fullstack-api라고 입력한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/d7810d1b-2f32-4f4e-8153-46a0ffae15de)
```
Enter optional maintenance note for runner 프롬프트는 빈칸으로 넘기고 다음에 나오는 executor를 선택하는 프롬프트에
shell을 입력한다.
```
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/f8720d07-bef2-479a-af9c-af430a12e0cb)
![image](https://github.com/chihyeonwon/AWS_EC2_Docker/assets/58906858/2a8e67a4-0c5f-48ea-9174-1112ec6b5ee5)
```
등록 완료 메시지가 나타나고 GitLab-Setting-CI/CD 메뉴의 하단에 fullstack-api라는 이름의 runner가 등록된 것을
확인할 수 있다.
```
#### .gitlab-ci.yml 파일 코드에 추가
```
코드에 .gitlab-ci.yml을 추가해서 deploy 브랜치에 배포했을 때 자동으로 GitLab에서 배포가 진행되도록 만든다.
```

```
GitLab에서 runner를 사용하는 리포지토리인지 아닌지를 감지하기 위해서는 .gitlab-ci.yml 라는 이름의 파일이 필요하다.
프로젝트 가장 상단의 폴더에 .gitlab-ci.yml 파일을 만들어준다.(파일 이름의 가장 앞에 마침표를 확인한다)
```































