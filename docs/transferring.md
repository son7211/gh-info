### Repository Transfer
 - 새로운 owner에게 해당 저장소의 admin 권한을 넘기는 것
 - 저장소의 모든 데이터 : 이슈, pull requests, releases, project boards, and settings
 - 새로운 owner는 관련 이메일을 수신하고 저장소 권한 이전에 관해 수용할 것인지 거부할 것인지를 하루안에 결정해야 함 (하루를 넘기면 not complete)
 - 새로운 owner는 동일한 이름의 저장소가 없어야 함 (또는 fork된)
 - 원래의 owner는 이전된 저장소의 collaborator로 추가됨 
 - Private fork는 이전되지 않음

### What's transferred with a repository?
  - 저장소내 모든 데이터
  - issue, pull requests, wiki
  - stars, watchers
  - webhooks, services, deploy keys는 이전후에도 계속 연결된 상태를 유지
  - commit횟수, contributors 
  - 이전 되기 전에 갖고 있던 fork들도 이전후에 계속 유지
  - Git LFS파일들 (큰 파일들이 옮겨지려면 시간이 소요됨. 이전은 백그라운드로 실행됨) - 이전을 실행하기에 앞서, 이전받을 account가 Git LFS 파일들을 받을 수 있도록 충분한 data pack을 갖고 있는지 확인필요.
  - Issue assignees 이전
     - User간 저장소 이전에서 issue assignment는 그대로 유지됨. 
     - User에서 org로의 저장소 이전에서는 해당 조직내에 member에게 assign된 이슈는 그대로 유지되나, 그러치 않은 이슈 assignees들은 삭제됨. 해당 조직 owner만이 신규로 issue assignment를 수행할 수 있음.
     - Org에서 user로의 저장소 이전에서는 해당 user로 할당된 issue assignment만 유지되고, 다른 issue assignees들은 삭제됨
  - 이전되는 저장소가 GitHub Page사이트를 갖고 있다면, 해당 web link와 이전된 Git repository로의 접속은 redirect됨.  
  - 그밖의 모든 저장소의 위치들은 이전 후에 자동으로 신규 위치로 redirect됨. git clone, git fetch, git push등도 이전 후의 신규 저장소 위치 또는 URL로 redirect. 하지만, 혼란을 방지하기 위해 local clone들을 신규 저장소 URL로 업데이트 하는 것을 권고 : 
  ``` 
    git remote set-url origin new_url
  ```
