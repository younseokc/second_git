DAY-6



1. GIT(소스 저장소)
   1. Vcs : version control system
      1. 변경 이력을 기록을 통해서 변경된 내용을 공유 
      2. 타인이 작업한 내용을 쉽게 병합
      3. 과거 상태로 쉽게 복구가능
      4. 여러 분기를 통해 병렬관리 기능
2. 다른 소스 관리 프로그램
   1. svn
   2. mercurial
3. GIT 의 특징
   1. branch
   2. GIT에서의 작업 흐름
      1. working directory- 
         1. 실제로 내가 작업하는 파일을 관리하는 공간(내 컴퓨터 안에서)
      2. staging area-(index)
         1. 대기공간.
         2. checkout the project
         3. repository 에 들어가기 전 준비 공간
         4. 파일이 갖고 있는 의미(수정사항, 이 파일의 목적)같은 comment를 작성할 수 있는 공간.
         5. 이 공간에서 repository에 올릴 파일을 선택한다.
         6. 가상의 공간(내 컴퓨터 안에 저장 되 있다.)
         7. 이 공간에선 다시 working directory로 돌아가서 수정할 수 있다.(unstaging)
         8. 내 컴퓨터에만 남아있고, 다른 사람 컴퓨터에는 반영이 필요없을 경우에 staging area에서 
      3. .git diretory(repository 저장소)
         1. 작업내용이 히스토리를 관리를 해줄 공간
         2. 변경이력을 저장한 저장소.
         3. local repository
            1. 내 컴퓨터에 존재함.
            2. Remote repository에 보내기 전.
         4. remote repository(원격 저장소)
            1. 서버에 존재함.
            2. 싱크를 맞춰줄 수 있다.
   3. Git ignore.
   4. repository
      1. 프로젝트의 단위로 생각해서 진행하면 편하다. 



커밋의 단위는 작업 하나당으로 생각한다. ex) 어떤 class 를 추가. or bugfix 하나의 작업 내역을 하나의 커밋 단위로 잡는다.   

리버스 커밋으로 위해서 한가지 테스크를 끝낼때마다 커밋을 해주는 편이 좋다.



 reverse와 reset

1. reset
   1. reset은 돌아가고 싶은 상태의 commit에서 reset~을 선택해준다. reset은 잘 사용하지 않는 편이 좋다. 자칫하단 모든 소스가 전부 날아가기 때문이다.
   2. reset은 총 두가지가 있다. (mixed는 제외)
      1. soft - local repository
      2. hard - working directory(특별한 이유가 없는 한 hard reset을 하면 된다.)
2. reverse

 과제

1. 자신이관심있는 분야의 내용을 정리할 저장소 만들기
2. readme.md파일을 생성하여 관심있는 분야엥 대해 mark down문법으로 정리하기
3. 내용을 정리하면서 짝꿍과 함께 임의 충돌을 만들고 해결해보기
4. 주간보너스 과제
   1. 짝꿍이 아닌 사람의 저장소의 내용을 보충해보기(full request<?>)



문제 해결 방법 

conflict 가 난 파일의 우클릭 후 문제 해결 방안을 선택 한 다음에 해결할 수 있다. 

1. mine : 마지막 내 로컬 컴퓨터 커밋 기준으로 해결한다. 
   1. 이 경우엔 커밋하고 마지막에 commit을 해주도록 한다.
2. their ; 마지막으로 서버에 저장되어 push되어진 것을 기준으로 해결한다. 
3. Marked resolved : 현재 해결 되었다고 친다.



Day-7

간단한 터미널 명령어 

    pwd - 현재 경로 표기
    open  .(open과 .은 두번 띄운다.) - 현재 터미널에서 보고 있는 창을 윈도우에서 띄어줌
    rm rf 'directory' - 해당 폴더 삭제
    rm 'filename' - 해당 파일 삭제



GIT Terminal 명령어

    git init : 현재 있는 워킹 디렉토리에 git 폴더 새엇ㅇ
    git status : 현재 워킹 디렉토리 상태를 확인
    git log : git의 log를 확인
    git log -p : 파일 수정을 디테일하게 보여줌 
    git clone : remote저장소를 통째로 워킹 디렉토리로 복사
    git pull : remote의 정보를 가져와 워킹디렉토리와 병합
    git add 'filename' :  변경한 해당 파일을 stagearea에 올려놓기 위함
    git add -A : stagearea에 올라가있지 않은 모든 파일들을 한번에 올리는 것
    git commit : stagearea에 있는 파일들을 커밋시키는 것
    git commit 'filename' : stagearea에 있는 지정한 해당파일을 커밋시키는 것
    git reset --hard '커밋 번호' : 해당 커밋 번호로 하드 리셋
    git revert '커밋 번호' : 해당 커밋으로 돌아감
    
    branch
    git branch - 현재 있는 브렌치 목록을 보여준다.
    git branch 'branch name' - 지정한 브렌치 이름으로 브렌치를 생성한다.
    git branch 'branch name' 'Parent branch name' - 상위 브렌치 밑에 하위 브렌치를 생성한다.g
    git checkout 'branch name' - 지정한 브렌치 이름으로 옮겨서 작업한다.
    git branch -d 'branch name' - 지정한 브렌치를 삭제한다.
    git merge 'commit code'- 현재 브렌치에 해당 커밋코드의 커밋과 머지 시킨다.
    git branch -v - 각각의 브렌치의 마지막 커밋 상태를 보여준다.
    
    



터미널  GIT 워크플로우 

1. git init 으로 워킹디렉토리 폴더 세팅
2. (파일작성 혹은 수정 후 )  git add 'filename' 으로    stagearea로 파일을 추가함.
3. git commit 'filename'혹은 git commit 'filename' -m.'남겨야되는 코멘트'로 커밋을 함.

새로운 repository에 올리는 방법 

1. git remote add '해당 repository 이름' '해당 repository'의 url'
2. git push



gitignore

vi .gitignore을 생성한 뒤에 올라가면 안되거나, 올려도 쓸모가 없는 파일명을 적어두면 해당 파일은 add나 commit의 해당이 되지 않는다.

Gitignore는 왠만하면 git init 을 하자마자 만들어주면 좋다

Gitinore.io에 들어가면 더미나 덤프 파일들을 자동으로 만들어주는 사이트다. 즐찾하자.


