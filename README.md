"# hyujikoh" 
git 명령어

1. 설정과 초기화
git config --global user.name “Your name”
전역 사용자명 

git config --global user.email “Your email address”
이메일 구성하기 (해당 저장소 디렉터리로 이동 후)

git config user.name “Your 
저장소별 사용자명 구성하기 (해당 저장소 디렉터리로 이동 후)

git config user.email “Your email address”
이메일 구성하기 (해당 저장소 디렉터리로 이동후)

git config --global --list
전역 설정 정보 조회

git config --list
저장소별 설정 정보 조회

git config --global color.ui “auto”
Git의 출력결과 색상 활성화하기

mkdir /path/newDir
cd /path/newDir
git init
새로운 저장소 초기화하기

git clone <저장소 url>
저장소 복제하기

git remote add <원격 저장소> <저장소 url>
새로운 원격 저장소 추가하기

2. 기본적인 사용법
git add <파일>
git commit –m “<메시지>”
새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기

git add -p [<파일> [<파일> [기타 파일들…]]]
파일의 일부를 스테이징하기

git add -i
add 명령에서 Git 대화 모드를 사용하여 파일 추가하기

git add -u [<경로> [<경로>]]
수정되고 추적되는 파일의 변경 사항 스테이징하기

git commit -m “<메시지>” -a
수정되고 추적되는 모든 파일의 변경 사항 커밋하기

git checkout HEAD <파일> [<파일>]
작업 트리의 변경 사항 돌려놓기

git reset HEAD <파일> [<파일>]
커밋되지 않고 스테이징된 변경 사항 재설정하기

git commit -m “<메시지>” --amend
마지막 커밋 고치기

git commit -C HEAD --amend
이전 커밋을 수정하고 커밋 메시지를 재사용하기


git clone : origin 에 있는 repository 를 로컬로 가져오는 명령어. 
           이렇게 해서 가져온 git 이 master 임. 

git init : git 초기화 인데 git clone 을 하게 되면 자동 수행 됨. 

git add : 작업내용을 반영하는 작업. 

git status : 변경되고 commit 되지 않은 파일 목록을 보여 줌. 

git commit : 변경 내용 or 신규 추가 파일이 master 에 추가 됨. 
     --amend 옵션 : 직전에 commit 메시지를 수정. 
     -am 옵션 : add 와 commit 을 동시 진행. 

git log : master 에 변경된 내용이 log 됨. 
            --graph 옵션 : 시각적으로 확인. 

git push : master 의 수정 사항이 GitHub 의 origin repository 에 등록. 

git branch : 로컬의 branch 목록을 표시. 초기에는 *master 만 표기됨.

$ git branch -a     라고 하면 origin 의 목록까지 표시됨. 

git checkout -b "브렌치 명" : branch 생성. 

git checkout "브렌치 명" : 해당 branch 를 활성화 . 

git init : git 생성하기

git clone git_path : 코드가져오기

git checkout branch_name : 브랜치 선택하기

git checkout -t remote_path/branch_name : 원격 브랜치 선택하기

git branch branch_name : 브랜치 생성하기

git branch -r : 원격 브랜치 목록보기

git branch -a : 로컬 브랜치 목록보기

git branch -m branch_name change_branch_name : 브랜치 이름 바꾸기

git branch -d branch_name : 브랜치 삭제하기

git push remote_name — delete branch_name : 원격 브랜치 삭제하기 

git add file_path : 수정한 코드 선택하기

git commit -m “commit_description” : 선택한 코드 설명 적기 ( git commit –m “내용”)

git push romote_name branch_name : add하고 commit한 코드 git server에 보내기 

git pull : git서버에서 최신 코드 받아와 merge 하기
git fetch : git서버에서 최신 코드 받아오기

git reset — hard HEAD^ : commit한 이전 코드 취소하기

git reset — soft HEAD^ : 코드는 살리고 commit만 취소하기

git reset — merge : merge 취소하기

git reset — hard HEAD && git pull : git 코드 강제로 모두 받아오기

git config — global user.name “user_name ” : git 계정Name 변경하기

git config — global user.email “user_email” : git 계정Mail변경하기

git stash / git stash save “description” : 작업코드 임시저장하고 브랜치 바꾸기

git stash pop : 마지막으로 임시 저장한 작업코드 가져오기

git reset // add 한 파일 취소

git reset — -merge // merge 한 코드 취소

git reset — soft HEAD^ //commit 코드 살리기

git reset — hard HEAD^ //commit 이전의 코드로 돌아가기

git reset — hard HEAD // HEAD를 기준으로 이전코드로 돌아갑니다.

git pull // git 서버에서 코드를 다시 받아옵니다.

관리

git-clean - 작업 트리에서 untracked 파일을 제거

git-clean -d : untracked 디렉토리 이외의 untracked 파일 제거

git-clean -f : Git구성 변수인 clean.requireForce가 false로 설정되지 않은 경우 
git clean은 -f, -n 또는 -i를 지정하지 않으면 파일이나 디렉토리를 
삭제하지 않습니다.

git-clean -q : 오류만 표기

git-clean -n : 실제로 아무것도 제거하지 않고 수행 할 작업만 표기   

git-clean -x : -e옵션과 함께 사용하여 주어진 무시 규칙을 계속 사용하여 빌드를 포함해
모든 파일 제거가능

git-clean -X : 무시된 파일만 제거가능


git-gc - 불필요한 파일 정리 및 로컬 저장소 최적화

git-gc --aggressive : 더 많은 시간을 투자해 최적화에 신경씀

git-gc --auto : 하우스 키핑이 필요한지 여부확인

git-gc --prune : 지정된 날짜보다 오래된 객체 제거

git-gc --quiet : 모든 상황을 표시하지않음

git-gc --force : 같은 저장소에 실행중인 다른 git gc가 있어도 실행되도록 함

git-fsck - db에 있는 객체의 연결성과 유효성을 확인

git-fsck --unreachable : 존재하지만 참조노드에 도달할 수 없는 객체 표시

git-fsck --dangling : 존재하지만 직접 사용되지 않은 개체 표시

git-fsck --root : 루트 표기

git-fsck --tags : 태그 표기

git-fsck --full :  대체 오브젝트 풀의 하위 디렉토리를 팩하고 기본값으로 만듬

git-fsck --connectivity-only : 태그,커밋 및 트리 객체의 연결만 검사

git-fsck --strict : 보다 엄격한 검사를 사용함

git-fsck --verbose : 자세하게 설명

git-fsck --name-objects : 도달 할 수 있는 객체의 이름을 표기할 때, 호환되는

도달 가능한 방법을 설명하는 이름도 표시함

git-reflog - reflog정보 관리

git-reflog --all : reflog의 모든 과정 정의

git-reflog --expire : 지정된 시간보다 오래된 항목 제거  

git-reflog --expire-unreachable :  지정된 시간보다 오래된 항목을 현재 팁에서 도달 할 수 없도록 제거함

git-reflog --updateref : 이전 상위 항목이 제거된 경우 상위 reflog항목의 값으로 업데이트

git-reflog --rewrite : reflog 항목의 선행작업이 제거된 경우 새 필드와 같도록 조정

git-reflog --dry-run : 실제로 모든 항목을 제거하지 않고 정리된 것이 뭔지 보여줌

git-reflog --verbose : 화면에 추가정보를 보여줌

git-instaweb - gitweb에서 작업 저장소를 찾음
   
git-instaweb --local : 웹서버를 로컬 ip에만 바인드 함

git-instaweb --httpd : 실행될 HTTP 데몬 명령을 함

git-instaweb --module-path : 모듈 경로

git-instaweb --port : httpd를 바인드할 포트 번호 설정

git-instaweb --browser : gitweb 페이지를 보는데 사용할 웹 브라우저설정

git-instaweb --start : httpd인스턴스를 시작

git-instaweb --stop : httpd인스턴스를 멈추고 종료함

git-archive - 명명된 트리에서 파일의 아카이브 생성
   
git-archive --list : 사용 가능한 모든 형식을 표기

git-archive --verbose : 진행 상황의 오류를 표시

git-archive --prefix : 아카이브의 각 파일 이름앞에 <prefix>를 붙임

git-archive --output : 아카이브를 stdout 대신 <file>에 사용

git-archive --worktree-attributes : 작업 트리의 gitattributes파일 속성을 찾음

git-archive --remote : 원격저장소에서 tar 아카이브를 검색함

git-archive --exec : 원격 측의 경로를 지정하기위해 사용

git-archive --tree-ish : 아카이브를 생성하는 트리

git-archive --path : 선택적 경로 매개 변수가 없으면 현재 작업 디렉토리의 모든 파일과 하위 디렉토리가 아카이브에 포함


git-bundle : 아카이브로 객체 및 참조 이동

git-bundle --create<file> : 파일이라는 번들 만드는데 사용

git-bundle --verify<file> : 번들파일이 유효하고 현재 저장소에 정상적으로 적용되는지 확인

git-bundle --list-heads<file> : 번들에 정의 된 참조 나열

git-bundle --unbundle<file> : 번들에 있는 객체를 저장소에 저장하기 위해 git index-pack에 전달한 다음 정의된 모든 참조 이름을 표시

git-bundle --git-rev-list-args : git rev-parse와 git rev-list에 허용되는 인수목록은 전송에 대한 특정 객체 및 참조를 지정











마크다운 문법


제목
#h1 
#으로 시작하는 텍스트 하나부터 여섯 개까지 쓸 수 있다. #dl 늘어날때마다 제목 수준은 내려간다. 

h1
=== 
h2
-- 
마찬가지로 -,=으로 쓸 수 있다.

인용
>인용문 -> “인용문  
=“인용문으로 나타난다. 

>>인용문안에 인용문
=“인용문
	“ 인용문

코드 블록 
```
코드 블록
입니다.
```
~~~ 
코드블럭 
입니다
~~~ 
:~~~또는  ```를 코드 첫줄과 마지막줄에 3개씩 삽입한다. 몇 번째 코드인지를 알기위한 문법

인라인 코드 
`문장코드`
:문장에 양 끝에 `을 집어넣어 문장에 배경을 넣어 감싸준다.

강조
*문장코드*
_문장코드_
: 기울여 쓰기위한 문법

**문장코드**
__문장코드__
: 볼드체로 쓰기위한 문법

수평선 
--- 
=== 
___ 
;-,=,_중 하나를 3개씩 작성하여 수평선을 만든다.

링크
[링크](http://example.com “링크제목“)
: 인라인 링크 

[링크1][1] 
[1]: http://example1.com/ "링크제목1" 
:참조 링크

<example.com/> 
<example@example.com> 
:url 링크

[링크](#id) 
:내부 링크

리스트
number.문장
: 적힌숫자랑 상관없이 순서대로 번호가 매겨진다

(*,+,- 중 하나)문장 
	(*,+,- 중 하나)문장
	(*,+,- 중 하나)문장
:순서없는 리스트 위한 문법

테이블
Header 1 | Header 2
--------- | ---------
Content 1 | Content 3
Content 2 | Content 4
:테이블을 생성한다

| :-------- | :--------: | --------: |
| Left | Center | Right |
:테이블을 정렬하면서 생성한다.
이미지

![alt text](/test.png )
:인라인 이미지

![alt text](image_URL)
:링크 이미지

![alt text][1]
[1]: /test.png
:참조 이미지
  
