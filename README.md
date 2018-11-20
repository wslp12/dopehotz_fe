# 개요
1. 서버실행 방법 및 명령어
2. 사용된 기술
3. 앵귤러 코드 설명
  
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
