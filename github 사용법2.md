# Github 사용법2



### Branch

독립적으로 어떤 작업을 진행하기 위함, 처음 저장소를 만들면 Git은 'master'라는 이름의 브랜치를 만든다.

* 통합 브랜치 : 언제든지 배포할 수 있는 버전을 만들 수 있어야 하는 브랜치, 일반적으로 master 브랜치를 통합 브랜치로 사용
* 토픽 브랜치 : 기능 추가나 버그 수정과 같은 단위 작업을 위한 브랜치, 피처 브랜치라고 부르기도 함



### Branch 전환

checkout 명령어 사용

* HEAD : 현재 사용 중인 브랜치의 선두 부분을 나타내는 이름

  * 커밋을 지정할 때, ~(틸트) 와 ^(캐럿)을 사용하여 현재 커밋으로부터 특정 커밋의 위치를 가리킬 수 있음

    ![image-20200926190006603](C:\Users\pc\AppData\Roaming\Typora\typora-user-images\image-20200926190006603.png)

    출처 : https://backlog.com/git-tutorial/kr/stepup/stepup1_3.html

* Stash :  파일의 변경 내용을 일시적으로 기록해두는 영역

  커밋안하고 checkout했는데 이동 branch에서도 변경 사항이 있을때 checkout 실패할 수 있음. 따라서 변경 내용을 저장할 수 있는 장소가 필요하고 그것이 stash



### Branch 통합

* merge : 변경 내용의 이력이 모두 그대로 남아 있기 때문에 이력이 복잡해짐.
  * 통합 브랜치에 토픽 브랜치를 불러올 경우에는 우선 rebase 를 한 후 merge
* rebase : 이력은 단순해지지만, 원래의 커밋 이력이 변경됨. 정확한 이력을 남겨야 할 필요가 있을 경우에는 사용하면 안됨.
  * 토픽 브랜치에 통합 브랜치의 최신 코드를 적용할 경우에는 rebase 를 사용



### 명령어

```shell
git branch <branchname> : branch 생성

git branch : 브랜치 목록 전체 확인

git checkout <branchname> : branch 이동

git checkout -b <branchname> : branch 생성과 이동을 동시에 실행

git merge <commit> : HEAD가 가리키고 있는 브랜치에 지정한 commit이 병함됨

git branch -d <branchname> : branch 삭제

git reset --hard HEAD~ : 마지막으로 진행했던 병합 명령을 취소

git rebase <branchname> :  HEAD가 병합하려고하는 branch의 앞쪽으로 옮겨졌을뿐, 이후에 HEAD를 바꿔서 git merge 해줘야함.

git rebase --continue : 충돌 부분을 수정 한 후에는 --continue 써줘야함

git rebase --absort : rebase자체를 취소
```



### pull

원격저장소에서 가져온 후, 병합



### fetch

단순 가져오기, FETCH_HEAD로 checkout 가능

pull = fetch + merge



### push

원격저장소에 저장



### 태그

커밋을 참조하기 쉽도록 알기 쉬운 이름을 붙이는 것

* 일반 테그
* 주석 태그

```shell
git tag <tagname> : HEAD가 가리키고 있는 커밋에 태그 달아줌

git tag : tag 확인

git log --decorate : 태그 정보를 포함한 이력을 확인 가능

git tag -a <tagname> : 주석이 달린 태그를 추가

git tag -am"<주석>" <tagname>

git tag -n : 태그 목록과 주석 내용 확인

git tag -d <tagname> : tag삭제
```





