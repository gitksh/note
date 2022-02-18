# KSH`s NOTE
> 다양한 기록을 정리하는 공간

> https://note.ksh.one

## Auto Deploy
> Github Action을 사용

### Process
1. NOTE repository에 push event 발생
2. Builder Repository에 webhook post
3. Builder repository의 Action에서 자동 Build
4. github pages에 deploy