# remote collabo

## remote 저장소에서의 협업
다수의 팀원과 함께 프로젝트를 진행할 때, 원격 저장소를 사용하는 것은 필수적입니다.  
git을 사용해 버전관리를 하면서 어떤 방법으로 커밋을 할지, 어떤 방식으로 브랜치를 만들고 관리할지에 대해 합의하는 과정이 필요합니다.  
[git-flow](https://jeffkreeftmeijer.com/git-flow/)외에도 방법론의 종류는 다양하지만, 그에 앞서 기본적인 협업 방식을 알아보겠습니다.  

## remote 저장소에 올리기(push)
remote 저장소로 `push`할 때, 현재 로컬의 내 헤드의 위치, 브랜치의 위치는 중요하지 않습니다.  
remote 저장소에는 브랜치를 따로 만들지 않아도 새로운 브랜치를 `push` 하면 자동 생성합니다.  

```bash
git push <remote-name> <local-branch-name_to_push>
git push origin master
# origin에 Local master 브랜치를 push
git push origin a
# origin에 Local a 브랜치를 push 한다.
```

`push`로 인해 새로운 커밋이 올라가면 pull request를 할 수 있습니다.  
pull request는 원격 저장소의 master와 내가 만든 원격 브랜치의 merge라고 생각하면 됩니다.


## remote 저장소에서 가져오기(pull)
공동으로 작업하는 remote 저장소가 있고, 나는 브랜치 `feat`을 만들어 그곳에서 계속 작업한다고 합시다.  
push할 때는 현재 로컬의 head 위치가 중요하지 않지만, pull을 할 때는 로컬의 head가 어딘지가 결과에 영향을 줍니다.  

```bash
git pull <remote-name> <remote-branch-name_to_pull>
git pull origin master
```
`feat` 브랜치에 head가 있는 상태에서 위와 같이 치면,
내 로컬 `feat` 브랜치에 origin master 브랜치를 가져온다는 뜻이 됩니다.  

`feat` 브랜치에서 pull을 했든, `master` 브랜치에서 pull을 했든 두 브랜치를 merge 하여 다시 `feat` 브랜치에서 다음 작업을 시작하면 됩니다.