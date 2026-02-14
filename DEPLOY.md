# 모션 코딩 웹앱 배포 가이드 (Motion Coding Web App Deployment)

현재 시스템에 **Git**이 설치되어 있지 않아 자동 배포를 진행할 수 없습니다.
GitHub에 배포하기 위해서는 먼저 Git을 설치해야 합니다.

## 1단계: Git 설치하기 (필수)

1.  **Git 다운로드**: [https://git-scm.com/download/win](https://git-scm.com/download/win) 에 접속하여 "Click here to download"를 클릭합니다.
2.  **설치 진행**: 다운로드된 설치 파일을 실행하고, 모든 옵션을 기본값(Next 계속 클릭)으로 두고 설치를 완료합니다.
3.  **설치 확인**: 설치가 완료되면 컴퓨터를 재부팅하거나, 사용 중인 터미널(VS Code 등)을 껐다가 다시 켭니다.

## 2단계: GitHub 저장소 만들기

1.  [GitHub](https://github.com/)에 로그인합니다.
2.  우측 상단 `+` 버튼 -> **New repository**를 클릭합니다.
3.  **Repository name**에 `motion-coding-app` 등 원하는 이름을 입력합니다.
4.  **Public**으로 설정하고 **Create repository**를 클릭합니다.

## 3단계: 코드 올리기 (Git 설치 후)

저장소가 생성되면 다음과 같은 명령어를 터미널에 입력하여 코드를 올릴 수 있습니다. (제가 도와드릴 수도 있습니다!)

```bash
git init
git add .
git commit -m "First commit"
git branch -M main
git remote add origin https://github.com/사용자이름/저장소이름.git
git push -u origin main
```

## 4단계: 배포 확인

1.  GitHub 저장소의 **Settings** -> **Pages** 메뉴로 이동합니다.
2.  **Branch**를 `master`, 폴더를 `/(root)`로 설정하고 **Save**를 누릅니다.
3.  잠시 후 상단에 생성된 주소로 접속하면 웹앱이 배포된 것을 확인할 수 있습니다.

