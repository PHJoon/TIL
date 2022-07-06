# Git

## Git 명령어

- **git config --global user.name "이름"**
- **git config --global user.email "메일주소"**
  - 최초 1회 설정, 누가 커밋 기록 남겼는지 확인하기 위한

- **git config --global -l or --list**
  - 작성자 설정 확인

- **git init** 
  - 저장소 사용하려는 디렉터리 가서 실행, 저장소 초기화되고 git 저장소 생성
    - 이미 git저장소인 폴더 내에 또 다른 저장소 생성 금지(터미널에 이미 master가 있다면 입력X)
    - 홈 디렉터리에서 git init 하면 안됨(터미널 경로 `~`확인)

- **git status** 
  - git 상태 확인, 파일 상태 확인
    - `Untracked` : Git이 관리하지 않는 파일
    - `Tracked` : Git이 관리하는 파일
      - `Unmodified` : 최신
      - `Modified` : 수정되었지만 아직 Staging Area에 반영X
      - `Staged` : Staging Area에 올라간 상태

- **git add `파일`, `폴더`**
  - 스테이지로 파일 올림

- **git add .**
  - 스테이지로 전체 올림

- **git commit -m `"내용"`**
  - 내용과 함께 커밋

- **git remote add `저장소 이름` `저장소 주소`**
  - 저장소 이름으로 원격 저장소 추가

- **git remote -v**
  - 저장소 목록 보기

- **git remote rm `저장소 이름`**
  - 원격 저장소와 로컬 저장소 연결 끊음

- **git push `저장소 이름` `브랜치 이름`**
  - 커밋을 원격 저장소로 업로드

- **git push -u `저장소 이름` `브랜치 이름`**
  - 이후에는 `$ git push`만 작성해도 업로드

- **git clone `저장소 주소`**
  - 원격 저장소 커밋 내역 모두 로컬 저장소로 가져옴

- **git pull `저장소 이름` `브랜치 이름`**
  - 원격 저장소 변경사항 가져와서 로컬 저장소를 업데이트
  - 완전히 일치하면 실행해도 변화 없음

- **git log**
  - 커밋 기록 확인
    - `--oneline` : 한 줄로 보여줌
    - `--graph` : 브랜치와 머지 내역 그래프로 보여줌
    - `--all` : 현재 브랜치 포함 모든 브랜치 내역 보여줌
    - `--reverse` : 커밋 내역의 순서를 반대로
    - `-p` : 파일 변경 내용도 보여줌
    - `-숫자` : 원하는 숫자만큼의 내역 보여줌

- **git reset HEAD `파일명`**
  - 스테이지에 add된 파일 취소
  - `파일명` 생략하면 스테이지의 모든 파일 취소

- **git reset HEAD^**
  - commit을 취소

- **git commit --amend**
  - commit message 수정

- **.gitignore**
  - git이 특정 파일이나 폴더에 버전 관리 못하게 지정
    - 민감한 정보
    - OS파일
    - IDE 혹은 Text editor에서 활용되는 파일
    - 개발 언어 혹은 프레임워크에서 사용되는 파일
  - .git 폴더와 동일한 위치에 생성
  - git add전에 작성해야함
  - 도움되는 사이트 : https://www.toptal.com/developers/gitignore
  
  - `*.txt`: txt 파일 모두 무시
  - `!asd.txt` : `*.txt` 파일 중 예외 만들기
  - `/File_1` : 현재 디렉터리에 있는 File_1 파일만 무시(다른 경로에 있는 File_1 은 제외)
  - `Folder/` : Folder 디렉터리에 있는 모든 파일 무시
  - `Folder/*.txt` : Folder/asd.txt 파일은 무시, Folder/Folder_1/asd.txt 파일은 무시하지 않음
  - `Folder/**/*.pdf : Folder 디렉터리 아래 모든 .pdf 파일 무시

