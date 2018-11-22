# 개요
1. 서버실행 방법 및 명령어
2. 사용된 기술
3. 앵귤러 코드
  
## 1. 서버 실행  
`npm intall`  package.json 모듈 다운로드
`ng server` : 서버 실행  
`--port` : 포트 변경  ( `ng serve` default 4200 )  
`--host` : 0.0.0.0 ( `ng serve` default 127.0.0.1 )

#### Internet Information Services를 이용한 실행방법
1. 제어판  
2. Window 기능 켜기/끄기
3. 인터넷 정보 서비스 체크

++ 사이트의 실제경로에는 `ng build` 이후 dist 폴더안의 프로젝트 경로를 넣어준다.

### 빌드
`ng build` : javascript 코드로 변환시키는 컴파일 과정을 거친다. component의 오류를 감지한다.  
`--prod` : production 환경으로 실행, 엄격하게 검사하며 각종 사용하지 않는 코드를 제거한다.  


### 기타 명령어.
`ng generate component component-name` or `ng g c component-name` : 컴포넌트 생성  
`ng --version` : 앵귤러 버전확인

## 2. 사용된 기술
>jenkins (CI server)
server : raspberry pi  

Webhook(gitlab -> jenkins)걸어준다.  
![webhookgitlab](./readme_image/2.PNG)  
이후 이벤트가 감지되면  
![webhookgitlab](./readme_image/1.PNG)  
자동으로 빌드. 빌드완료 후 SFTP 프로토콜로 본서버에 접속 배포  

>docker
프로젝트 진행중 잦은 서버 옮김 및 문제로 인해 docker 도입  
`docker pull centos:latest` : centos7 당김  
`docker run -it {repoName}:{tagName} /bin/bash` : 실행 및 접속  
`yam install ...` 필요한 프로그램 설치 ( nginx,node,angular cli,git )  
`docker commit {CONTAINER_ID} {WANT_NAME}` : 컨테이너 commit  
`docker images` : commit 이미지 확인
![webhookgitlab](./readme_image/4.PNG)  
`docker push ..` dockhub에 push  
`docker run --privileged -p {hostPort}:{containerPort} -it -e "container=docker" -v {jenkinsFiles}:/usr/share/nginx/html -v /sys/fs/cgroup:/sys/fs/cgroup {repository}:{tag} /usr/sbin/init`  
: -v 옵션으로 호스트와 공유할 폴더를 설정하여 컨테이너를 실행  
![webhookgitlab](./readme_image/3.PNG)  

~~docker 옵션과 자세한 설명은 해당 dockerhub를 참조~~  
>~~https://hub.docker.com/r/wslp12/dopehotz_fe/~~

## 3. 앵귤러 코드




