# github 사용법



## 1. git bash 이용

```shell
git init : git 시작

git remote add origin + repository address : repository와 local directory를 연결

git status : 변경사항 확인

git add . : 변경 사항이 있는 모든 파일들을 stage 시킴

git commit -m "message" : 변경 사항을 저장, 저장에 대한 message입력

git push origin master : 원격저장소 github에 push

git pull origin master : 원격저장소에 있는 파일을 local로 불러옴
```



## 2. cmd이용

```shell
git clone + repository address : 현재 directory에 repository 불러오기

git status : 변경 사항 확인

git add . : 변경 사항이 있는 모든 파일들을 stage 시킴

git reset : add 파일 취소

git commit : staging된 파일을 변경 사항에 반영, 커밋 로그를 작성할 수 있는 창이 생성

git log : 깃 로그 확인

git log --oneline : 한 줄로 로그 확인

git log --graph : 그래프의 형태로 로그 확인

git log --oineline --graph : 두 옵션을 한번에 사용 가능

git push : 원격저장소 github에 push

<참고>
로그 작성 방법 : i -> 로그 작성(추가 설명까지 작성 가능) -> ESC -> :wq -> Enter
```

