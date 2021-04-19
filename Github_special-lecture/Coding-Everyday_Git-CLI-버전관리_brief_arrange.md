# Git 시작

* ### 0. git 설치

  > Windows 10 기준

  [Git 홈페이지](git-scm.)에서 'Download *[version]* for Windows' 클릭 후 넘어간 페이지에서 자동 다운로드 또는 수동으로 '64-bit Git for Windows Setup' 클릭하여 다운로드 되는 파일 실행하여 Git 설치

  > *version*은 2021년 4월 8일 기준 2.31.64 버전이 Latest source Release임.

  > 수동 다운로드 시 운영체제 플랫폼에 유의
  >
  > \- Windows 32-bit 운영체제 또는 MacOS 등

  \* 설치 과정에서 설정할 내용 없음. Next만 눌러 진행.





* ### 1. git 환경 구성

  git을 통해 관리하고자 하는 폴더 또는 디렉토리를 미리 지정해야 합니다.

  

  Git 설치가 정상적으로 완료됐다면,

  1. *Git Bash* 프로그램을 실행합니다.
     명령 프롬프트 혹은 터미널(Terminal)과 같은 화면이 나옵니다.

     

  2. `cd` 명령어로 관리 대상 디렉토리로 이동합니다.

     ```Bash
     $ cd [대상 디렉토리]
     ```

     `pwd` 명령어로 현재 위치한 디렉토리를 확인할 수 있습니다.

     

  3. `git init` 명령어로 `.git` 폴더를 생성합니다.

     ```Bash
     $ git init		# 또는 git init .
     ```

     `ls -a` 명령어로 `.git` 폴더가 생성된 것을 확인할 수 있습니다.

     > 이제 *.git* 에 의해 관리되는 디렉토리 옆에 *(master)* 표시가 추가됩니다.
     >
     > `.git` 폴더에 버전 기록 등 관리되는 환경의 모든 정보가 포함되어 있으므로 `.git` 폴더 삭제에 유의해야 합니다.

     

  4. 이제 `.git` 폴더가 위치한 디렉토리는 git이 모니터링하며 디렉토리 내의 변경사항을 추적합니다.

     > git에서 이렇게 모니터링 되는 디렉토리를 *Working Directory* 또는 *Working Tree* 라고 합니다.







* ### 2. 버전 생성

  먼저, 버전을 저장하며 관리하고자 하는 내용을 git에 알려줘야 합니다.

  

  1. `git add [대상]` 명령어를 통해 git이 버전을 만들 대상을 지정합니다.

     ```Bash
     $ git add a.txt
     ```


     git에서 *Staging Area* 라고 하는 곳에 대상을 위치시켜 버전을 만들 준비를 합니다.

  

  `git add` 명령을 통해 대상이 지정되면, commit 하여 실제 버전을 생성할 수 있습니다.

  

  2. `git commit` 명령어를 입력하여 버전을 생성합니다.

     ```Bash
     $ git commit
     ```

     생성된 버전은 git의 *Repository* 라고 하는 곳에 저장됩니다.

     

     명령 입력 시, *commit message* 를 입력하라며 파일 에디터가 나타납니다. commit message 는 필수 입력 내용으로, 여기에 내용을 입력하고 빠져나와 commit을 완료합니다.

     

     명령어를 `git commit -m [commit message]` 와 같이 입력하면 에디터로 이동하지 않고 곧바로 commit이 가능합니다.

     ```Bash
     $ git commit -m [commit message]
     ```

     

     ---

     > git을 처음 설치하고 commit 한 적이 없다면 다음과 같은 오류가 발생합니다.
     >
     > ```Bash
     > $ git commit
     > 
     > *** Please tell me who you are.
     > 
     > Run
     > 
     >   git config --global user.email "you@example.com"
     >   git config --global user.name "Your Name"
     > 
     > to set your account's default identity.
     > Omit --global to set the identity only in this repository.
     > 
     > fatal: empty ident name (for <>) not allowed
     > ```
     >
     > 
     >
     > git은 생성한 버전을 관리할 때 **누가** 이 버전을 생성한 것인지를 요구하기 때문에, 그 정보가 사전에 설정되어 있어야 합니다.
     >
     > 
     >
     > 오류 내용에서 설명하는 대로 지금 commit 하는 사람의 이름과 이메일 주소를 설정해줍니다.
     >
     > [Github 계정을 개설](https://github.com/join)하고, Github 계정 주소와 계정명을 입력합니다.
     >
     > ```Bash
     > $ git config --global user.name [이름]
     > ```
     >
     > ```Bash
     > $ git config --global user.email [이메일 주소]
     > ```
     >
     > 
     >
     > `git config --global user.name` 이나 `git config --global user.email` 명령으로 위에서 입력한 내용으로 잘 설정되었는지 확인할 수 있습니다.
     >
     > ```Bash
     > xsrsx@HYPC MINGW64 ~/git_basic (master)
     > $ git config --global user.name HoriYeori
     > 
     > xsrsx@HYPC MINGW64 ~/git_basic (master)
     > $ git config --global user.name
     > HoriYeori
     > ```
     >
     > ```Bash
     > xsrsx@HYPC MINGW64 ~/git_basic (master)
     > $ git config --global user.email xsrsx2000@gmail.com
     > 
     > xsrsx@HYPC MINGW64 ~/git_basic (master)
     > $ git config --global user.email
     > xsrsx2000@gmail.com
     > ```

     ---







