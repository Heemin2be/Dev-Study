1234

## 자바 설치하기

- 설치된 JDK 확인
  /Library/Java/JavaVirtualMachines : JDK 폴더 설치된 장소
  /Library/Java/JavaVirtualMachines/amazon-corretto-8.jdk/Contents/Home
- 환경변수로 설정할 JDK의 경로 복사
  - pwd : 현재열려있는 폴도의 경로를 복사
  - vi ~/.zshrc : 복사한 경로를 .zshrc 에 붙여넣어 JAVA 경로를 설정하기
    i를 눌러서 insert mode로 변경
    ### MongoDB 경로 추가
    ```zsh
    export PATH="/opt/homebrew/opt/mongodb-community@4.4/bin:$PATH"
    ```
    ### Java 경로 설정
    ```zsh
    JAVA_HOME=/Library/Java/JavaVirtualMachines/amazon-corretto-8.jdk/Contents/Home
    PATH=$JAVA_HOME/bin:$PATH
    export JAVA_HOME
    export PATH
    ```
    - 작성 후 esc를 눌러 읽기모드로 변경
    - shift + ; 를 눌러 나가기 모드로 전환
    - wq!를 입력 후 엔터 : 저장 후 나가기
  - cd ~/ : 홈 디렉토리로 이동
    - source ~/.zshrc : vi 편집기로 입력한 환경변수 값을 적용
  - echo $SHELL : 사용중인 쉘 확인
- 설정된 환경변수 확인
  - echo $JAVA_HOME : 입력한 값이 설정되었는지 확인
  - java -version : 자바 버전 확인
- 자바 설치 잘 됐는지 확인
  - which java : 자바가 설치된 곳 확인
  - cd /usr/bin
  - ls -lrt _java_ : java가 포함한 모든파일이나옴
