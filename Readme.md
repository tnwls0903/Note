** 나와 다른 사람이 작업 중 다른사람이 먼저 add commit하고 내가 늦게 add commit하게 되면 충돌 에러가 발생함! **
=> 충돌에러 발생한 사람은 git push add origin 명령어 실행하여 먼저 commit한 사람의 소스코드로 바꾸고 나서, 작업해야 됨
=> 같은 파일을 동시에 개발하면 계속 충돌 현상이 발생되므로, 각자 다른 파일 개발 담당 권장

https://github.com/silversmell/gittest1.git
① 폴더 생성 후 초기화
git init

② 사용자 등록
origin이란 이름으로 원격 저장소 https://github.com/tnwls0903/Note.git 를 등록

git config user.name "tnwls"
git config user.email "kim20267878@gmail.com"
git remote add origin https://github.com/tnwls0903/Note.git
cat .git/config

③ 소스 변경시 반복 실행 (3줄 세트)
git add .
git commit -m "김수진 수정함"
git push origin main


④ 최신 소스 로딩하기, push reject발생하면 실행
- origin이란 이름의 원격 저장소에 있는 main branch를 Local로 가져와 병합
git pull origin main -> STS(편집기)로 이동하여 편집 계속


- 저장소 삭제: git remote remove origin || STS에서 폴더 전체 삭제 -> clone 명령어 실행 -> import 폴더 -> 2번 사용자 등록
- clone: 
git clone https://github.com/daumnulunggi/test2.git test2-clone
git clone ttps://github.com/tnwls0903/Note.git Note