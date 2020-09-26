# Github 사용법3



### 커밋 변경하기

* --amend  : 같은 브랜치 상에서 이전에 커밋했던 내용에 새로운 내용을 추가하거나 설명을 수정할 수 있음
  * 누락 파일 추가, 기존 파일 업데이터
  * 커밋 설명 변경

  

* revert : 특정 커밋의 내용 삭제, rebase -i와 reset과 다르게 특정 커밋의 내용을 지우는 새로운 커밋을 만든다.



* reset : 더 이상 필요 없어진 커밋들을 버릴 수 있음

  <모드> : 일반적으로 mixed

  | 모드명 | HEAD의 위치 | 인덱스    | 작업 트리  |
  | ------ | ----------- | --------- | ---------- |
  | soft   | 변경함      | 변경 안함 | 변경 안 함 |
  | mixed  | 변경함      | 변경함    | 변경 안 함 |
  | hard   | 변경함      | 변경함    | 변경함     |

  * 커밋만 되돌리고 싶을 때 (soft)
  * 변경한 인덱스의 상태를 원래대로 되돌리고 싶을 때 (mixed)
  * 최근의 커밋을 완전히 버리고 이전의 상태로 되돌리고 싶을 때 (hard)

  

* cherry-pick : 다른 브랜치에서 지정한 커밋을 복사하여 현재 브랜치로 가져올 수 있음

  * 특정 브랜치에 잘못 추가한 커밋을 올바른 브랜치로 옮기려고 할 때
  * 다른 브랜치의 커밋을 현재 브랜치에도 추가하고 싶을 때

  

* rebase -i : 커밋을 다시 쓰거나 다른 커밋과 바꿔 넣을 수 있음, 특정 위치의 커밋을 삭제하거나 여러 커밋을 통합도 가능
  * push 하기 전에 이전의 커밋 내용을 정리하고자 할 때
  * 그룹으로 묶을 수 있는 커밋들을 알기 쉽게 하나로 통합하려고 할 때
  * 이전 커밋에 누락된 파일들을 나중에 추가하고자 할 때



* squash : merge할 때 사용가능한 옵션, squash 이용하여 브랜치 병합 시 브랜치의 커밋 전체를 통합한 커밋이 추가됨
  * 토픽 브랜치 안의 커밋을 한꺼번에 모아서 통합 브랜치에 병합하고자 할 때



### 명령어

```shell
git commit --amend : 커밋 설명 변경

git revert <commitname> : <commitname>의 커밋을 지우는 커밋 생성

git reset --hard HEAD~~ : amster 브랜치 앞의 두 개의 커밋을 삭제

git reset --hard ORIG_HEAD : reset 실행 전의 상태로 되돌림

git cherry-pick <commit number> : <commit number>를 현재의 HEAD에서 commit

git rebase -i HEAD~~ : HEAD에서 HEAD~~까지의 커밋병합 -> pick을 squash로 변경

git rebase -i HEAD~~ : pick 문자를 edit으로 변경하고 변경사항 변경 -> git commit --amend로 변경사항 저장 -> git rebase --continue로 커밋 작업을 종료

git merge --squash <commitname> : <commitname> 브랜치 상의 모든 커밋을 하나로 병합한 내용이 HEAD에 추가 

```

