redux 없이 상태관리
대신 SWR 을 사용합니다.

========= backend 설치 시작 =========
mysql 설치 mysql 8.0 이상 버전을 설치했고
taskkill 명령어로 기존 3306 포트 사용중인 mysql 을 죽이고 
설치중 legacy 로 하길 추천 호환성 버그 문제에있어서 좋음
설치하였음 비번은 cloneslack
back - config - config.js 에서 username 을 바꿔주고
env 에 나의 mysql "pw"를 입력함

-- 이때발생한오류 access denied for user 오류 --
.env 를 back폴더에 넣어주니까 해결됨 다른폴더에있어서 문제가 발생
-- 

npx sequelize db:create 터미널에서 입력시 
sleact 라는 데이터베이스가 생성

이후 table을 만드는데 back-models에 있는대로 생성이됨
npm run dev 입력시 실행이됨 (table을 만들기위해)

npx sequelize db:seed:all
=> 가짜 데이터를 만듬 seedrs 에 워크스페이스(회사),chanel(부서) 

※데이터베이스 - 테이블 - 로우 순으로 크기

======== backend 과정 끝 =========

※터미널을 사용할때 git-bash를 추천하는 이유는 (맥이랑비슷,리눅스랑비슷) 명령어 오류가 더적음

========= front 셋팅 시작 ==========
1. 노드의 첫시작은 거의 npm init
2. init 할때 name 의 이름을 지을때 npm에 있는 패키지 이름이랑 겹치면 에러가 발생할수있음
3. npm i react react-dom 으로 리액트 설치
4. npm i tyesscript /  npm i @types/react @types/react-dom : 타입스크립트를 사용할 경우라면 입력
5. tip: 실행시 packge.json/pack-lock.json/node_moudels(폴더) 가 생기는데 git 에는 node_modules는 무거워서 올리지않음
6. tip: pack-lock.json 정확히 의존하고 있는 버전들을 표기해줌
7. tip: 리눅스 에서 (.파일이름 확장자없는) 이런파일들은 숨겨지고 , 설정파일로 인식하면 좋음
8. 이수업에서는 타입스크립트 -> 바벨로 바꾸고 -> js로 바꿔줌 : 바벨이 이미지 나 html 등 js로 바꿔준다!
9. "strict": true 를 무조건씀 any 를 사용하는건 추천하지않음
10. tpyescript는 js의 변수,함수의매개변수,함수의반환값에 타입이 붙어있다 생각하면 좋음
11. webpack-dev-server : 는 프록시 서버 역할도 해줌 cors 에러도 해결해줌 
12. <Switch> 여러개중에 하나만선택 스위치처럼 하나가 켜지면 나머지는꺼짐
13. <Route> component 를 화면에 뛰어주는 역할
14. <Redirect> 진짜 다른페이지로 돌려주는 역할