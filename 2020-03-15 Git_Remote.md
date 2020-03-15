# 원격 저장소 만들기

## 원격 저장소

![DVCS](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2016/11/Distributed-Version-Control-System-Workflow-What-Is-Git-Edureka-768x508.png)

Git 은 분산 버전 관리 시스템으로 2개의 저장소, 즉 지역(로컬) 저장소와 원격 저장소가 존재한다.
* 지역 저장소 : 개발자들이 실제 개발을 진행하는 장소로, 버전 관리가 수행된다.

* 원격 저장소 : 여러 사람들이 협업을 위해 버전을 공동 관리하는 곳으로, 자신의 버전 관리 내역을 반영하거나 다른 개발자의 변경 내용을 가져올 때 사용한다.
버전관리가 지역 저장소에서 진행되므로 버전 관리가 신속하게 처리되고, 원격 저장소나 네트워크에 문제가 있어도 작업이 가능하다.

### git remote
`git remote`는 원격 저장소를 등록하는 명령어이다. 원격 저장소를 `git remote add` 이름 저장소_주소로 등록하면, 이후로는 긴 저장소_주조를 입력하지 않아도 등록한 이름을 이용하여 `fetch/push/pull` 등의 명령을 수행할 수 있다.

    $ git remote
    $ git remote add 이름 저장소_주소
    $ git remote show 이름

### 등록되어 있는 remote repository 확인

    $ git remote
    origin

origin이라는 이름의 원격저장소로 등록되어 있다. 기본적인 원격저장소 이름으로 origin을 주로 사용한다.

    $ git remote -v
    origin  https://github.com/parksimis/Git.git (fetch)
    origin  https://github.com/parksimis/Git.git (push)
-v 옵션을 사용하면 URL 주소까지 알 수 있다.

### 새로운 Remote repository 추가

    $ git remote add [이름] [저장소_주소]
    =========================================
    $ git remote add test https://github.com/parksimis/Git.git
    =========================================
    $ git remote
    origin
    test


`add` 명령어를 통해 test라는 이름의 원격 저장소를 추가하였다.

### 추가한 Remote repository 확인

    $ git remote show [이름]
    =====================================
    $ git remote show test
    * remote test
      Fetch URL: https://github.com/parksimis/Git.git
      Push  URL: https://github.com/parksimis/Git.git
      HEAD branch: master
      Remote branch:
        master new (next fetch will store in remotes/test)
      Local ref configured for 'git push':
        master pushes to master (up to date)

`show` 명령어를 통해 지정한 원격 저장소의 정보를 출력할 수 있다.

### 지정된 Remote Repository 제거

    $ git remote rm [이름]
    ===========================
    $ git remote rm test
    ===========================
    $ git remote show
    origin

`rm` 명령어를 통해 지정한 원격 저장소를 삭제할 수 있다.
