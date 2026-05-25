# DH Solution Homepage

Wix로 구축되어 있던 `www.dhsolu.com`의 정적 페이지를 GitHub Pages에서 서비스할 수 있도록 복제한 정적 홈페이지입니다.

## 배포 URL
https://tellamon.github.io/dh-solution-homepage
추후에 https://dhsolu.com 으로 연결되어야 함.

## Local Test

별도 빌드 과정은 없습니다. 저장소 루트에서 정적 웹 서버를 실행한 뒤 브라우저에서 확인합니다.

```sh
python3 -m http.server 4173
```

브라우저에서 `http://127.0.0.1:4173/`로 접속합니다.

다른 서비스가 이미 `4173` 포트를 사용 중이면 원하는 포트로 바꿔 실행합니다.

```sh
python3 -m http.server 8080
```

## Deploy

GitHub 저장소에 쓰기 권한이 있는 계정으로 인증한 뒤 업로드합니다.

```sh
gh auth login
git remote add origin https://github.com/tellamon/dh-solution-homepage.git
git push -u origin main
```

이미 `origin`이 등록되어 있으면 `git remote add` 대신 아래 명령으로 확인합니다.

```sh
git remote -v
```

GitHub Pages 설정은 저장소 관리자 권한이 필요할 수 있습니다. 저장소 화면에서 `Settings` → `Pages`로 이동한 뒤 아래처럼 설정합니다.

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/ (root)`

CLI 권한이 있으면 아래 API 호출로도 설정할 수 있습니다.

```sh
gh api \
  --method POST \
  repos/tellamon/dh-solution-homepage/pages \
  --input - <<'JSON'
{"source":{"branch":"main","path":"/"}}
JSON
```

## Routes

- `/`
- `/solution/`
- `/hw/`
- `/sw/`
- `/products/dhs-hw-a100/`
- `/contact/`
- `/en/`
- `/en/solution/`
- `/en/hw/`
- `/en/sw/`
- `/en/contact/`

호환 경로 `/복제-솔루션`, `/복제-hw`, `/en/복제-hw`는 정적 리다이렉트 페이지로 처리합니다.
