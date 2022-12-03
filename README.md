# OSS_STUDY
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
