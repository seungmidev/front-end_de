# 프론트엔드 개발환경의 이해와 실습 (webpack, babel, eslint..)

> 모듈시스템을 사용하고 개발 환경을 자동화하는 방법(Webpack)  
최신 자바스크립트 문법을 사용하는 환경 만들기(Babel)  
동료와 협업하는 개발 환경 만들기 (ESLint, Prettier)

## NPM

### 1. Node.js가 필요한 이유
1. 최신 스펙으로 개발 가능
2. 빌드 자동화
3. 개발 환경 커스터마이징



### 2. Node.js 다운로드
LTS : node로 서버를 운영할 때  
최신 버전 : 개발 환경을 구축할 때



### 3. package.json
scripts : 프로젝트를 자동화할 수 있는 셸 스크립트를 입력하는 부분  
scripts > test : 문자열을 echo 명령어 작성 & 에러코드 1번을 반환



### 4. 외부 Package 설치
1. npm init 명령어를 사용하여 package.json을 기록하고 프로젝트 초기화
2. CDN 사용 : 외부 라이브러리를 직접 가져오는 방식(서버가 장애가 난다면 어플리케이션이 정상 작동하지 않음)
3. 코드를 직접 다운로드 : 라이브러리가 업데이트 될 때마다 최신 버전으로 교체해야 함
4. npm을 사용 : npm install 패키지명
  - package.json 내 유의적 버전 "^16.13.1" 표기
  - 주 버전(Major Version): 기존 버전과 호환되지 않게 변경한 경우 = 16
  - 부 버전(Minor version) : 기존 버전과 호환되면서 기능이 추가된 경우 = 13
  - 수 버전(Patch version) : 기존 버전과 호환되면서 버그를 수정한 경우 = 1
  - ^(캐럿) : ^16.13.1은 16.13.1 ~ 17.0.0 미만 버전까지 포함



## Webpack

### 1. IIFE
즉시 실행 함수 표현
1. 독립적인 스코프가 생성
2. IIFE 안에서 실행되는 함수는 외부 접근 불가능(전역 스코프 오염 예방)



### 2. 모듈
1. CommonJS : exports 키워드로 모듈으르 만들고 require() 함수로 불러 들이는 방식
2. AMD : 브라우저 환경(비동기)
3. UMD : AMD 기반으로 CommonJS까지 지원

* ES2015 표준 모듈 시스템 : export 키워드로 모듈을 만들고 import 구문으로 불러 들이는 방식
* 익스를 포함한 몇 몇 브라우저는 모듈 사용 불가능 (script 태그 내 type="text/javascript" 대신 type="module"을 사용)



### 3. 엔트리/아웃풋

#### Webpack 역할
모듈로 연결된 여러개의 자바스크립트 파일을 하나로 합쳐줌(번들러)



#### Webpack 실행 필수 옵션
1. --mode : development, production, none
2. --entry : 모듈의 시작점
3. --output : 결과 저장 경로



#### npm으로 webpack 실행
package.json 내 scripts 부분에 "build": "webpack" 추가  
npm run build 명령어로 실행

