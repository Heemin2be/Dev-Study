- 초기세팅
  - 유저 정보 입력
    - git config —global [user.name](http://user.name) “`내이름`” : 깃에 내 이름 설정
    - git config — global [user.email](http://user.email) “`깃허브 이메일`” : 깃에 내 이멜 설정
    - git config —list : config 잘 됐는지 확인
  - 환경설정
    1. git config —global [user.name](http://user.name) “`내이름`” : 깃에 내 이름 설정
    2. git config — global [user.email](http://user.email) “`깃허브 이메일`” : 깃에 내 이멜 설정
    3. git config —list : config 잘 됐는지 확인
    4. git init : git을 초기화
- 소스코드 업로드
  1. git add .(all) : (현재 디렉토리에)모든 파일을 깃에 올릴지 추려본다.
     - git add : (현재 디렉토리에)어떤 파일을 깃에 올릴지 추려본다.
  2. (필수아님) git status : add로 추가된(,수정된) 파일을 알려줌
  3. git commit -m “`히스토리 제목`” : 커밋
     1. 커밋 : 히스토리
  4. git remote add origin “`레파지토리url`” : 레파지토리로 내 소스코드를 보냄
  5. git remote -v : 연결한 레파지토리 주소를 알려줌
  6. git push -u origin ”`보낼 브랜치`” : 푸쉬

  7. [https://miro7923.github.io/uno mas/teamwork-by-github/](https://miro7923.github.io/uno%20mas/teamwork-by-github/)
- git remote로컬 Git 저장소와 원격 저장소 간의 연결을 관리
  1. **원격 저장소 목록 확인**
  ```bash
  git remote
  ```
  - 이 명령어는 현재 로컬 저장소에 연결된 원격 저장소의 이름을 출력합니다. 보통 `origin`이라는 이름이 사용됩니다.
  ```bash
  git remote -v
  ```
  - `v` 옵션을 추가하면, 각 원격 저장소의 URL도 함께 출력됩니다. `fetch`와 `push` URL이 각각 표시됩니다.
  **2. 새 원격 저장소 추가**
  ```bash
  git remote add <name> <url>
  ```
  - 이 명령어는 새로운 원격 저장소를 추가합니다
  - `<name>`에는 원격 저장소의 이름을 지정하며, `<url>`에는 해당 저장소의 URL을 입력합니다.
  - 예를 들어, `origin`이라는 이름으로 GitHub에 있는 저장소를 추가하려면 다음과 같이 입력합니다:
    ```bash
    git remote add origin https://github.com/user/repo.git
    ```
  3. **원격 저장소 이름 변경**
  ```bash
  git remote rename <old-name> <new-name>
  ```
  - 이 명령어는 기존의 원격 저장소 이름을 변경합니다.
  - 예를 들어, `origin`이라는 이름을 `new-origin`으로 변경하려면 다음과 같이 입력합니다:
    ```bash
    git remote rename origin new-origin
    ```
  4. **원격 저장소 제거**
  ```bash
  git remote remove <name>
  ```
  - 이 명령어는 지정된 이름의 원격 저장소를 제거합니다.
  - 예를 들어, `origin`이라는 이름의 원격 저장소를 제거하려면 다음과 같이 입력합니다:
    ```bash
    bash코드 복사
    git remote remove origin

    ```
  5. **원격 저장소 정보 조회**
  ```bash
  bash코드 복사
  git remote show <name>

  ```
  - 이 명령어는 특정 원격 저장소의 상세 정보를 보여줍니다.
  - 예를 들어, `origin` 원격 저장소의 정보를 확인하려면 다음과 같이 입력합니다:
    ```bash
    bash코드 복사
    git remote show origin

    ```
- 포크 후 원본 이랑 동기화
  1. 포크를 해 온다
  2. 포크한 내용을 내가 수정한다.
  3. sync fork 로 내 수정본을 병합해달라고 요청한다
  4. 원본에서 수락
  5. 동기화 완료
- 스테이징 취소
  ### 1. **특정 파일의 스테이징 취소**
  - 특정 파일의 스테이징을 취소하고 싶다면, 다음 명령어를 사용합니다:
    ```bash
    bash코드 복사
    git reset HEAD <file>

    ```
  - 예를 들어, `example.txt` 파일을 스테이징에서 제거하려면:
    ```bash
    bash코드 복사
    git reset HEAD example.txt

    ```
  ### 2. **모든 파일의 스테이징 취소**
  - 현재 스테이징된 모든 파일을 스테이징에서 제거하려면, 다음 명령어를 사용합니다:
    ```bash
    bash코드 복사
    git reset HEAD .

    ```
  - 이 명령어는 현재 디렉토리 및 하위 디렉토리에서 스테이징된 모든 파일을 스테이징에서 제거합니다.
  ### 3. **최근 커밋의 스테이징 취소** (아직 푸시하지 않은 경우)
  - 최근 커밋한 내용을 스테이징 영역으로 되돌리고 싶다면, 다음 명령어를 사용합니다:
    ```bash
    bash코드 복사
    git reset --soft HEAD^

    ```
  - 이 명령어는 가장 최근 커밋을 취소하고, 변경 사항을 스테이징 상태로 되돌립니다.
  ### 4. **스테이징된 변경 사항을 완전히 취소 (작업 디렉토리에서도 삭제)**
  - 스테이징된 변경 사항뿐만 아니라, 작업 디렉토리에서도 해당 변경 사항을 완전히 제거하려면:
    ```bash
    bash코드 복사
    git reset --hard HEAD

    ```
  - 주의: 이 명령어는 스테이징된 모든 변경 사항과 작업 디렉토리의 변경 사항을 삭제하므로, 되돌릴 수 없습니다.
  ### 요약
  - **특정 파일의 스테이징 취소**: `git reset HEAD <file>`
  - **모든 파일의 스테이징 취소**: `git reset HEAD .`
  - **최근 커밋의 스테이징 취소**: `git reset --soft HEAD^`
  - **변경 사항을 완전히 취소**: `git reset --hard HEAD` (주의 필요)
