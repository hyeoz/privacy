# privacy

앱 개인정보처리방침과 고객 지원 페이지를 모아 관리하는 정적 사이트입니다. GitHub Pages로 게시합니다.

## 구조

```text
.
├── index.html                    서비스 목록 랜딩
├── assets/style.css              모든 페이지 공통 스타일
├── support/index.html            공통 지원·문의 페이지
├── jjigeuljido/index.html        찍을지도
├── wedding-peach-camera/index.html  웨피캠
├── vitamango/index.html          비타망고 (준비 중)
└── .nojekyll                     Jekyll 빌드 비활성화
```

빌드 도구가 없습니다. HTML을 수정해 push하면 그대로 게시됩니다.

## 게시 URL

| 페이지 | URL |
| --- | --- |
| 랜딩 | `https://<username>.github.io/privacy/` |
| 지원 | `https://<username>.github.io/privacy/support/` |
| 찍을지도 | `https://<username>.github.io/privacy/jjigeuljido/` |
| 웨피캠 | `https://<username>.github.io/privacy/wedding-peach-camera/` |
| 비타망고 | `https://<username>.github.io/privacy/vitamango/` |

## 최초 설정

1. GitHub에서 **public** 레포 `privacy`를 만듭니다. (Pages는 public 레포에서 무료입니다.)
2. 이 폴더를 push합니다.

   ```bash
   git init
   git add .
   git commit -m "chore: add privacy policy and support pages"
   git branch -M main
   git remote add origin https://github.com/<username>/privacy.git
   git push -u origin main
   ```

3. 레포 **Settings → Pages**에서 Source를 `Deploy from a branch`, 브랜치를 `main` / `/ (root)`로 설정합니다.
4. 1~2분 후 위 URL이 열리는지 확인합니다.

## 새 서비스 추가

1. 서비스 슬러그로 폴더를 만들고 기존 페이지의 `index.html`을 복사합니다.
2. `<link rel="stylesheet" href="../assets/style.css">` 경로가 맞는지 확인합니다.
3. 루트 `index.html`의 `.cards` 목록에 항목을 추가합니다.
4. `support/index.html` 하단의 방침 링크 목록에도 추가합니다.

## 운영자 정보

현재 값은 운영자 **이혜원**, 문의 **official.hyeoz@gmail.com** 이며 모든 페이지 하단(및 일부 페이지의 `<title>`)에 들어 있습니다. 한 번에 바꾸려면:

```bash
find . -name '*.html' -exec sed -i '' \
  -e 's/이혜원/새 이름/g' \
  -e 's/official\.hyeoz@gmail\.com/새 이메일/g' {} +
```

(macOS 기준입니다. Linux에서는 `sed -i` 뒤의 `''`를 빼십시오.)

App Store Connect의 개발자 표시 이름은 `HyeWon Lee`입니다. 방침의 운영자명과 표기가 다르면 심사에서 동일인 확인을 요청받을 수 있으므로, 한쪽을 바꿀 때 다른 쪽도 함께 검토하십시오.

## 방침을 수정할 때

내용이 실질적으로 바뀌면 해당 페이지 상단과 하단의 **시행일**을 함께 갱신하고, 무엇이 바뀌었는지 커밋 메시지에 남깁니다. 앱 스토어에 제출한 방침과 실제 앱 동작이 어긋나면 심사에서 지적받을 수 있으므로, 앱에 SDK를 추가하거나 권한을 늘릴 때마다 해당 방침을 함께 확인합니다.
