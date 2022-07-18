# Github   

### Real Github
1. terminal   
 -> most people use comder for window, iterm for macOS


</br>

### github setting
- core.autocrlf   
  - 운영체재마다 에디터에서 줄바꿈을 할 때 들어가는 문자열이 달라짐 이로 인해 git history 등을 보는데 문제가 있을 수 있음으로 이를 방지해주는 명령어   
 `window : git config --global core.autocrlf true / macOS : git config --global core.autocrlf input`
 (윈도우는 carriage-return & line feed / macOS는 line feed)
 
</br>

- alias   
   - git 에 내장되어 있는 명령어들의 호출을 커스텀할 수 있다   
   `git config --global alias.(커스텀명령어) 기존명령어` 
- git congig --h 를 통해서 명령어들을 확인할 수 있음

</br>

### github Workflow


</br>

#### Working directory 
- 수정 및 작업 등을 하는 곳
   - 어느 정도의 작업이 완료된 파일들은 개별로 staging area 에 옮김    
   `staging area 로 옮기는 명령어 : git add 파일이름 (git add * 를 하면 풀더에 있는 모든 파일이 staging area 로 업로드 됨)`


</br>

#### Staging area
- 작업이 어느정도 완료되어 버전 히스토리에 업로드가 준비된 파일들
   - 준비가 된 파일들은 commit 을 통해 git directory 로 업로드함

</br>

#### .git directory(repository)
- 버전에 히스토리를 가지고 있는 곳
   - direcotory 에 업로드 된 히스토리는 local 환경에 업로드 되어 있기에, github 와 같은 서버에 push 를 해서 히스토리를 업로드함
   - 서버에 있는 히스토리를 다운 받고 싶다면 pull 을 사용할 수 있음

</br>

#### git repository 활용
- 앱 혹은 웹 전체를 만들고 업로드하는 것이 아닌 기능들을 세분화하여 부위 별로 history를 업로드하고 관리하는 것이 이상적

</br>

### git others


#### git ingnore 
- `gitignore` 파일 안에 `특정 파일확장자를 무시하고 싶음 : *.log` `특정 풀더 안의 파일을 모두 무시하고 싶음 : 파일이름/`   
 `합쳐서 특정 파일 안의 특정 파일확장자를 무시하고 싶음 : 파일이름/*.log`
 
</br>

#### git diff
- git diff 는 파일의 내용을 비교하여 수정 여부와 수정 상세 내용을 확인할 수 있게해줌
- git diff 명령어를 입력하면 아래와 같이 출력됨
```
diff --git a/a.txt b/a.txt // 여기서 a는 이전 버전, b는 현재 버전을 의미함 
index 7c4a013..4797c58 100644 
--- a/a.txt // 비교 대상 파일 
+++ b/a.txt // 현재 파일 
@@ -1 +1,2 @@ // -는 이전 버전을 의미하고 1은 첫번 째 줄을 의미함, +는 현재 버전을 의미하고 2는 둘째줄을 의미함
// 해석하면 이전 버전 첫번 째 줄에서 현재버전은 2번째 줄까지 추가 되었다는 의미임
-aaa
+aaa bbbhi
+new! // - 는 없어진 것이고 + 추가된 
```

</br>

#### commit 
- `git commit -m "commit title"` Staging area 에 있는 파일들을 repository 에 업로드 할 수 있음
- `git commit -am "commit title"` Working directory, Staging area 에 있는 모든 파일들을 repository 에 업로드 할 수 있음
