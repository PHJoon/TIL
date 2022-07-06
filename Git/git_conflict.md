# Git 충돌

###### pull -> 원격저장소 업데이트(로컬은 업데이트된 커밋 pull하지 않은 상태)  ->  push 하는 경우<br>

- **서로 다른 파일 수정**
    - 자동으로 병합<br><br>
- **같은 파일의 다른 라인 수정**
    - 자동으로 병합<br><br>
- **같은 파일의 같은 라인 수정**
    - `rejected` 에러
    1. `push` 하기 전에 `pull` 먼저 실행
    2. 가져온 변경사항(Incoming Change)과 로컬 변경사항(Current Change) 둘 다 보여줌
        - Accept Current Change
        - Accept Incoming Change
        - Accept Both Changes
        - Compare Changes
    3. `(master|merging)` 이라 표시됨
    4. `git add` -> `git commit` -> `git push`