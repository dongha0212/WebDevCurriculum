# Quest 00. 형상관리 시스템

## Introduction
* git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics
* git
  * `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
  * `.git` 폴더
* GitHub

## Resources
* [Resources to learn Git](https://try.github.io)
* [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
* [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist
Q: 형상관리 시스템은 왜 나오게 되었을까요?
A: 프로젝트에서 발생하는 변경사항을 체계적으로 추적하고 통제하여 관련된 사람에게 보고 함으로써 특히 여러사람들과 협업 시 프로젝트의 완성도를 높이고 실수를 줄이기 위해서 사용함.

Q: git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?
A: git 은 분산형 버전관리 시스템으로 Repository 의 완전한 복사본을 로컬에 저장 가능하다. 로컬에서 모든 히스토리를 기록하여 처리속도가 빠르지만 대용량 코드 관리에 부적절하다.
분산형 형상관리 시스템 : 각 개발자가 중앙 서버에 접근하지 않고 코드작업을 할수있다. 각 개발자의 독립적으로 작업한 후 변경사항을 병합/거절 가능.

Q: git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
A: 많은 개발자들이 사용하던 사유소스관리 시스템(SCM)인 비트키퍼의 자유이용이 제한되면서 리누스 토르발스는 비트키퍼와 같은 자신만의 분산 시스템을 원했으나 당시 사용가능한 자유시스템중 그를 만족시키는 것이 없어 개발함.

Q: git과 GitHub은 어떻게 다를까요?
A: git : 버전 관리 프로그램 / Github : git 저장소(Repository)를 관리하는 클라우드 기반 호스팅 서비스


Q: git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
A: clone : 저장소 복제
   add : 새로운 파일을 추가하거나 존재하는 파일을 스테이징.
   commit : 스테이징된 파일을 '새로운 버전'으로 기록 commit 시점에 파일의 스냅샷정보가 .git 파일 에 저장함.
   push : 지역 브랜치를 원격 브랜치에 병합함.
   stash : 변경사항을 스테이징이나 커밋하지 않고 따로 보관하여 새로 병합되거나 원격브랜치에 푸시할때 영향이 없도록 한다. stash push로 스태시보관할 파일을 따로 보관하고 stash pop으로 다시 현재 작업파일에 적용함. 

Q: git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
A: git 시스템은 프로젝트 히스토리를 4개의 object 로 관리.
   blob : git add 시 생성, 파일내용이 들어있다.
   tree : git commit 할때 생성 타입과 객체명 파일명이 기록된다.
   commit : git commit 할때 생성, tree 객체명, 부모 commit 객체명, author, committer, message가 기록된다.
   tag : git tag 시 생성, commit 객체명, tag이름, tagger, message가 기록된다.

Q: 리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?
A:  git reset --hard <돌아갈 commit>
    git push -f
    reset 사용하여 되돌아갈 commit으로 이동하여 강제로 원격 브랜치에 push
    git log --oneline // 커밋기록 확인
    git revert <취소할 커밋> // 커밋을 취소
    git commit -m "revert message" 
    push
    revert 사용하여 commit을 취소

## Quest
* GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced
* Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
* 실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?
