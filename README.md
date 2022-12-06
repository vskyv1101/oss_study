<h3 align="center"> OSS_STUDY </h3>

- git bash 기본설정하기
```bash
$ cd 저장소 폴더 ----- 깃 저장소 폴더
$ git config user.name "사용자 이름"
$ git config user.email "이메일 주소"
$ git config --global core.autocrlf true ----- 맥과 윈도우 간의 자동변화
$ git config --global core.safecrlf false ----- 뉴라인 경고 없애기
```
- 새 폴더 만들기
```bash
$ mkdir vskyv1101 ----- 새 폴더 만들기
$ cd vskyv1101 ----- 만든 폴더로 이동
```
- git init 명령어는 기존 폴더에 숨겨진 영역을 추가함으로써 깃 저장소로 변경함.
- 경로명을 입력하지 않으면, 현재 폴더에서 초기화됨.

```bash
$ git init 경로명
```
```bash
$ git init ----- 저장소 초기화
```
- 현재 폴더를 의미하는 .을 사용할 수도 있음.
```bash
$ git init .
```
- 파일 목록을 출력하는 리눅스 명령어
```bash
$ ls
```
- -a 명령어를 사용하여 폴더 안의 숨겨진 파일을 같이 출력
```bash
$ ls -a
```
- 보통 폴더 앞에 . 이 있으면 숨겨진 폴더를 의미함.
- 숨겨진 폴더인 .git 폴더에는 깃 저장소에 필요한 모든 뼈대 파일이 담겨 있음.
- 깃 저장소를 복사하고자 할 때는 숨겨진 .git 폴더까지 같이 복사해야함.
```bash
$ cp -r 원본폴더 복사폴더
```
- 깃의 상태 메시지를 확인할 수 있음.
```bash
$ git status ----- 상태 확인
On branch master
No commits yet ----- 커밋이 없다는 메시지
nothing to commit (create/copy files and use "git add" to track) ----- 변경된 내용이 없다는 메시지
```
- 깃 저장소 복제
```bash
$ git clone 원격저장소URL 새폴더이름
```
- 깃 저장소 복제해보기
```bash
$ git clone https://github.com/vskyv1101/oss_study ----- 저장소 복제
Cloning into 'vskyv1101'...
remote : Enumerating objects: 975, done.
remote : Total 975 (delta 0), reused 0 (delta 0), pack-reused 975
Receiving objects: 100% (975/975), 4.98 MiB : 3.67 MiB/s, done.
Resolving deltas: 100% (307/307), done.
```
- 새 파일 생성
```bash
$ mkdir gitstudy04 ----- 새 폴더 만들기
$ cd gitstudy04 ----- 만든 폴더로 이동
$ git init ----- 저장소를 깃으로 초기화
Initialized empty Git repository in E:/gitstudy04/.git
infoh@hojin MINGW64 /e/gitstudy04(master)
$ code index.htm
```
- 워킹 디렉터리의 파일을 스테이지 영역으로 등록하기.
```bash
$ git add 파일이름
```
- 스테이지 삭제
```bash
$ git rm --cached index.htm ----- 스테이지 삭제
```
- 이름변경
```bash
$ git mv 파일이름 새파일이름
```
- 수정된 파일 이력을 커밋하는법
```bash
$ git commit
```
- 파일 등록과 커밋을 동시에 하는 방법
```bash
$ git commit -a
```
- 커밋 후 커밋 기록 확인
```bash
$  git log ----- 저장소의 커밋이력 확인
```
- 수정한 파일 되돌리기
```bash
$ git checkout --수정파일이름
```
- 수정한 파일을 다시 스테이지에 올리기
```bash
$ git add 수정파일이름
```
- 커밋과 동시에 간단하게 메시지도 커밋하기
```bash
$  git commit -m "커밋 메시지"
```
- -a 와 -m 옵션을 같이 사용하기
```bash
$ git commit -am "커밋 메시지"
```
- 메시지가 없는 빈 커밋을 작성하는법
```bash
$  git commit --allow-empty-message -m "" ----- 커밋 메시지를 작성하지 않음
```
- 특정 커밋의 상세 정보를 확인하고 싶을 때
```bash
$ git show 커밋ID
```
- 스테이지 vs 워킹 디렉터리
```bash
$ git diff ----- 스테이지 vs 워킹 디렉터리 비교
```
- diff 내용을 추가해서 커밋
```bash
$ git commit -v ----- diff 내용 추가
```
- 로컬 저장소를 서버로 이용할 때
```bash
$ git remote add 원격저장소별칭 폴더경로
```
- 원격 저장소로 연결할 때
```bash
$ git remote add 원격저장소별칭 원격저장소URL
```
- 등록된 원격 저장소 삭제
```bash
$ git remote rm 원격저장소별칭
```
- 원격저장소로 로컬 깃 저장소의 내용을 전송할 때
```bash
$ git push 원격저장소별칭 브랜치이름
```
- 원격 저장소의 갱신된 내용을 추가로 내려받을 때
``` bash
$ git pull
```
- 수동 병합
```bash
$ git merge 원격저장소별칭 / 브랜치이름
```
- 브랜치 생성
```bash
$ git branch 브랜치이름 커밋ID
```
- 현재 브랜치가 어떤 커밋 해시 값을 가리키는지 확인할 때
```bash
$ git rev-perse 브랜치이름
```
- 깃에서 브랜치 간 이동할 때
```bash
$ git checkout 브랜치이름
$ git checkout --파일이름 ----- 파일로 체크아웃 / 특정 커밋이나 파일로도 할 수 있음.
```
- 서로 다른 로컬 브랜치와 리모트 브랜치를 수동으로 지정하여 연결
```bash
$ git push origin 브랜치이름:새로운브랜치
```
- 브랜치 정보 확인
```bash
$ git branch -a ----- 모든 브랜치 정보 확인
$ git branch -vv ------ 복제 저장소의 트래킹 브랜치 확인
$ git branch -r ----- 원격 저장소의 리모트 브랜치 목록 확인
```
- 원격 저장소에서 페치된 커밋들을 새로운 로컬 브랜치로 반영할 때
```bash
$ git merge 원격저장소별칭/브랜치이름
```
- 원격 브랜치의 포인터를 사용하여 임시 브랜치를 생성하거나 직접 체크아웃할 때
```bash
$ git checkout -b 임시브랜치이름 origin/브랜치이름
```
- 브랜치 삭제할 때
```bash
$ git branch -d 브랜치이름
```
- 원격 브랜치를 삭제할 때
```bash
$ git push origin --delete 리모트브랜치이름
```
- 스태시 명령어
```bash
$ git stash ----- 수정 중인 내역을 커밋하지 않고도 브랜치를 이동할 수 있게 워킹 디렉터리를 깨끗이 청소함
$ git stash save ----- 스태시를 여러 개를 생성할 때 유용함
$ git stash save "WIP: 메시지" ----- 스태시가 여러 개 있을 때 각각의 스태시를 구별할 수 있도록 메시지도 추가 가능
$ git stash list ----- list 옵션을 사용하여 스태시에 저장된 스택 확인 가능
```
- 스태시에 임시 저장한 작업 내용들을 읽고 다시 적용하기
```bash
$ git stash pop
```
- 스태시 스택에 저장된 내용으로 새로운 브랜치를 동시 생성 가능
```bash
$ git stash branch 브랜치이름
```
- 스태시 스택에 저장된 항목들을 브랜치에서 복원할 때
```bash
# git stash apply
```
- 스태시 목록에서 삭제할 때
```bash
$ git stash drop
```
- 워킹디렉터리에 있는 추적되지 않는 파일 삭제
```bash
$ git clean
```
- 병합하지 않은 브랜치 확인
```bash
$ git branch --merged
```
- 리베이스 작업
```bash
$ git rebase 브랜치
```  
         
