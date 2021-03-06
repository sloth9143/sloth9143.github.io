---
layout: post
title:  "[Github] Git/Github 기본 개념 정리"
date:   2020-03-13
excerpt: "Git/Github에서 기본적으로 사용되는 명령어 및 개념 설명"
github: true
tag:
- git
- github
- command
feature: https://sloth9143.github.io/assets/img/back01.png
comments: true
---

<style type="text/css">
    .blog_tbl th, .blog_tbl tr, .blog_tbl td{border: 1px solid #e2e2e2; border-radius: 4px; font-size: 9pt; padding: 5px;}
    .blog_tbl th{text-align: center;}
</style>

<br/>

## Git
 - 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 **분산 버전 관리 시스템**

 - **작업 트리(Work Tree)**
   - 우리가 작업하고 있는 폴더, 디렉터리를 말함
 - **인덱스**
   - 커밋을 실행하기 전의 **저장소와 작업 트리 사이에 존재하는 공간**
   - Staging Area라고도 불림
 - **스테이징(Staging)**
   - 인덱스에 파일 상태를 기록하는 것

<br/>

## Github
 - **Git을 호스팅해주는 웹 서비스**
 - Git 저장소 서버를 대신 유지 및 관리해주는 서비스
 
<br/>

## Git Repository (저장소)
 - 파일이나 폴더를 저장해 두는 곳

 - **원격 저장소(Remote Repository)**
   - 파일이 원격 저장소 전용 서버에서 관리되며 여러 사람이 함께 공유하기 위한 저장소
 - **로컬 저장소(Local Repository)**
   - 내 PC에 파일이 저장되는 개인 전용 저장소

<br/>

---
## Git 기본 명령어

<table class="blog_tbl">
    <tr>
        <th style="width:20%; background:#49483e; color:#f8f8f2;">명령어</th>
        <th style="width:5%; background:#49483e; color:#f8f8f2;">옵션</th>
        <th style="width:20%; background:#49483e; color:#f8f8f2;">예시</th>
        <th style="width:55%; background:#49483e; color:#f8f8f2;">설명</th>
    </tr>
    <tr>
        <td>init<br/>(생성하기)</td>
        <td></td>
        <td>git init</td>
        <td>새로운 git 저장소 생성</td>
    </tr>
    <tr>
        <td>pull<br/>(가져와 병합하기)</td>
        <td></td>
        <td>git pull</td>
        <td>
            원격 저장소에서 로컬 저장소로 업데이트<br/>
            원격 저장소에서 최신 변경 이력을 다운로드하여 내 로컬 저장소에 그 내용을 적용
        </td>
    </tr>
    <tr>
        <td>fetch<br/>(가져오기)</td>
        <td></td>
        <td>git fetch origin</td>
        <td>
            원격 저장소의 내용을 확인만 하고 로컬 데이터와 병합은 하고 싶지 않은 경우 사용하는 명령어<br/>
            원격 저장소의 최신 이력을 확인, 가져온 최신 커밋 이력은 이름 없는 브랜치로 로컬에 가져옴, 'FETCH_HEAD'의 이름으로 체크아웃 가능<br/>
            fetch 명령어 후 merge 를 수행하는 것은 pull 명령어와 동일한 기능
        </td>
    </tr>
    <tr>
        <td>add<br/>(추가하기)</td>
        <td></td>
        <td>git add &#60;인덱스에 등록할 파일명&#62;</td>
        <td>변경사항을 인덱스에 등록</td>
    </tr>
    <tr>
        <td rowspan="1">commit<br/>(기록하기)</td>
        <td>-m</td>
        <td>git commit -m "커밋 내용"</td>
        <td>
            이전 커밋 상태부터 현재 상태까지의 변경 이력이 기록된 커밋(혹은 리비전)이 생성<br/>
            '작업 트리'에 있는 변경 내용을 저장소에 바로 기록하는 것이 아니라 그 사이 공간인 '인덱스'에 파일 상태를 기록(stage - 스테이징 한다고 표현)<br/>
            commit 진행 시, 내용 입력 필수
        </td>
    </tr>
    <tr>
        <td>push<br/>(밀어넣기)</td>
        <td></td>
        <td>git push</td>
        <td>원격 저장소로 변경된 파일을 업로드하는 것</td>
    </tr>
    <tr>
        <td>clone<br/>(복제하기)</td>
        <td></td>
        <td>git clone &#60;URL&#62;</td>
        <td>
            원격 저장소를 복제(원격 저장소의 내용을 통째로 다운로드하는 것)<br/>
            변경 이력도 함께 로컬 저장소에 복제되어 오므로, 원래 원격 저장소와 똑같이 이력을 참조하고 커밋 진행 가능
        </td>
    </tr>
    <tr>
        <td>reset<br/>(되돌리기, 이력 x)</td>
        <td></td>
        <td>git reset &#60;옵션&#62; &#60;돌아가고싶은 커밋&#62;</td>
        <td>돌아가려는 커밋으로 리파지토리는 재설정, 해당 커밋 이후의 이력은 없애는 명령어</td>
    </tr>
    <tr>
        <td>revert<br/>(되돌리기, 이력 o)</td>
        <td></td>
        <td>git revert &#60;되돌릴 커밋&#62;</td>
        <td>상태를 되돌리는 명령어, reset 명령어와 달리 이전 이력은 그대로 유지</td>
    </tr>
    <tr>
        <td>merge<br/>(병합하기)<br/>(바로 합치기)</td>
        <td></td>
        <td></td>
        <td>
            여러 개의 브랜치를 하나로 모을 수 있음<br/>
            내가 끌어온 저장소가 최신 버전이 아닌 경우, 즉 내가 pull 을 실행한 후 다른 사람이 push 를 하여 원격 저장소를 업데이트 해버린 경우에는 위의 그림과 같이 내 push 요청이 거부될 수 있음<br/>
            다른 사람의 업데이트 이력을 내 저장소에도 갱신 해야함
        </td>
    </tr>
    <tr>
        <td>rebase<br/>(병합하기)<br/>(브랜치 이력 재정렬하기)</td>
        <td></td>
        <td></td>
        <td>히스토리 관리를 별로 신경쓰지 않고 혼자서만 커밋하거나 아니면 믿을수 있는 소수만 커밋한다면 merge 대신 rebase 사용 권장</td>
    </tr>
    <tr>
        <td>stash<br/>(임시 저장하기)</td>
        <td></td>
        <td></td>
        <td>
            파일의 변경 내용을 일시적으로 기록해두는 영역<br/>
            작업 트리와 인덱스 내에서 아직 커밋하지 않은 변경을 일시적으로 저장해 둘 수 있음<br/>
            stash 에 저장된 변경 내용은 나중에 다시 불러와 원래의 브랜치나 다른 브랜치에 커밋할 수 있음
        </td>
    </tr>
    <tr>
        <td>checkout<br/>(전환하기)</td>
        <td></td>
        <td>git checkout &#60;브랜치명&#62;</td>
        <td>원하는 다른 브랜치로 전환 시 사용하는 명령어</td>
    </tr>
</table>

<br/>

## merge (바로 합치기) vs rebase (브랜치 이력 재정렬하기)

 - **merge**
   - 변경 내용의 이력이 모두 그대로 남아 있기 때문에 이력이 복잡해짐

 - **rebase**
   - 이력은 단순해지지만, 원래의 커밋 이력이 변경됨. 정확한 이력을 남겨야 할 필요가 있을 경우에는 사용하면 안됨.

<br/>

---

<br/>

## 리모트(Remote) 저장소
 - 인터넷이나 네트워크 어딘가에 있는 저장소

<table class="blog_tbl">
    <tr>
        <th style="width:30%; background:#49483e; color:#f8f8f2;">기능</th>
        <th style="width:70%; background:#49483e; color:#f8f8f2;">예시</th>
    </tr>
    <tr>
        <td>리모트 저장소 확인</td>
        <td>git remote</td>
    </tr>
    <tr>
        <td>리모트 저장소 추가</td>
        <td>git remote add &#60;단축이름&#62; &#60;url&#62;</td>
    </tr>
    <tr>
        <td>리모트 저장소 살펴보기</td>
        <td>git remote show &#60;리모트 저장소 이름&#62;</td>
    </tr>
    <tr>
        <td>리모트 저장소 이름 변경</td>
        <td>git remote rename &#60;기존 리모트 저장소 이름&#62; &#60;변경할 리모트 저장소 이름&#62;</td>
    </tr>
    <tr>
        <td>리모트 저장소 삭제</td>
        <td>git remote remove &#60;리모트 저장소 이름&#62;</td>
    </tr>
</table>

<br/>

---

<br/>

## Branch
 - 독립적으로 어떤 작업을 진행하기 위한 개념
 - 각자 독립적인 작업 영역(저장소) 안에서 여러 개발자들이 동시에 다양한 작업을 할 수 있게 만들어 주는 기능

<br/>

<table class="blog_tbl">
    <tr>
        <th style="width:20%; background:#49483e; color:#f8f8f2;">기능</th>
        <th style="width:35%; background:#49483e; color:#f8f8f2;">예시</th>
        <th style="width:45%; background:#49483e; color:#f8f8f2;">설명</th>
    </tr>
    <tr>
        <td>브랜치 생성</td>
        <td>git branch &#60;branchname&#62;</td>
        <td></td>
    </tr>
    <tr>
        <td>브랜치 조회</td>
        <td>git branch</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2">브랜치 전환</td>
        <td>git checkout &#60;branchname&#62;</td>
        <td></td>
    </tr>
    <tr>
        <td>git checkout -b &#60;branchname&#62;</td>
        <td>브랜치 작성과 체크아웃을 한꺼번에 실행</td>
    </tr>
    <tr>
        <td>브랜치 병합</td>
        <td>git merge &#60;commit&#62;</td>
        <td>이 명령어에 병합할 커밋 이름을 넣어 실행하면, 지정한 커밋 내용이 'HEAD'가 가리키고 있는 브랜치에 넣어지며, 'HEAD'는 현재 사용중인 브랜치에 위치하게 됨<br/>
		'master' 브랜치에 넣기 위해서는 우선 'master' 브랜치에 'HEAD'가 위치하게 만들어야 함</td>
    </tr>
    <tr>
        <td>브랜치 삭제</td>
        <td>git branch -d &#60;branchname&#62;</td>
        <td></td>
    </tr>
</table>

<br/>

## Branch 종류 [Git-Flow]

### * Master Branch : 제품으로 출시될 수 있는 브랜치 (배포)
 - 저장소 생성시 master branch 생성됨
 - 배포 가능한 상태만을 관리, 커밋할 때에는 태그를 사용하여 배포 번호를 기록

### * Develop Branch : 다음 출시 버전을 개발하는 브랜치 (개발) (병합 대상)
 - 이 브랜치를 기반으로 개발을 진행

### * Feature Branch : 기능을 개발하는 브랜치 
 - 기능 개발, 개발 완료 시 Develop Branch로 병합
 - 기본적으로 공유할 필요가 없기 때문에, 원격으로는 관리하지 않음
 - Feature/{branch-name}

### * Release Branch : 이번 출시 버전을 준비하는 브랜치 (출시)
 - 릴리즈를 위한 최종적인 버그 수정 등의 개발을 수행
 - 버그를 수정하거나 새로운 기능을 포함한 상태로 모든 기능이 정상적으로 동작하는지 확인
 - 브랜치의 이름은 관례적으로 브랜치 이름 앞에 'release-' 를 붙임

### * Hotfix Branch : 출시 버전에서 발생한 버그를 수정 하는 브랜치 (버그)
 - 배포한 버전에 긴급하게 수정을 해야 할 필요가 있을 경우, 'master' 브랜치에서 분기하는 브랜치
 - 브랜치 이름 앞에 'hotfix-'를 붙입

<br/>

## Git-Flow
 - 저장소를 보다 고수준으로 관리하기 위한 브랜칭 관리 전략(branch management strategy)
![](https://sloth9143.github.io/assets/img/blog/develop/total-branch.png){: style="width:500px;"}

<br/>

---

<br/>

## Fork
 - 다른 사람의 Github repository에서 내가 어떤 부분을 수정하거나 추가 기능을 넣고 싶을 때 해당 respository를 내 Github repository로 그대로 복제하는 기능

## Pull Request
 - fork 및 파일 수정 후, 다른 사람의 Github repository에 변경 사항을 적용하고 싶으면 해당 저장소에 요청하는 것
 - pull request가 original repository의 관리자로 부터 승인 되었으면 내가 만든 코드가 commit, merge되어 original 에 반영

<br/>

---

<br/>

## Collaborators
 - 프로젝트의 공동 책임자로 GitHub의 push, pull 권한을 모두 가지고 있는 사람
 - 하나의 프로젝트를 중점적으로 개발하는 개발자들은 Collaborator로 등록하여 작업하는 것이 효율적
 - Private일때는 최대 3명까지 Collaborators을 지정해 줄 수 있다. 그 이상을 지정해 주려면 비용을 지불해야 함

## Contributor
 - 한 프로젝트의 커밋에 관여하는 모든 사람 (Pull Request가 받아들여진 사람)

<br/>

---

<br/>

## 소스트리 (SourceTree)
 - GIT을 GUI로 사용자가 더 쉽게 사용할 수 있도록 하는 Atlassian에서 개발한 프로그램
 - 개인과 기업 모두 무료
 - 이클립스에서도 GIT 플러그인은 지원하지만,,,,,,, 많은 사람들이 소스트리를 더 추천하는 듯함

![](https://sloth9143.github.io/assets/img/blog/develop/sourcetree.png){: style="width:600px;"}

<br/>

---

#### [ reference ]
   - [Git 브랜치의 종류 및 사용법(5가지), https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html](https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html)
   - [누구나 쉽게 이해할 수 있는 Git 입문, https://backlog.com/git-tutorial/kr/](https://backlog.com/git-tutorial/kr/)
   - [GitHub Collaborator 추가하기, https://hyoje420.tistory.com/41](https://hyoje420.tistory.com/41)

<br/>
