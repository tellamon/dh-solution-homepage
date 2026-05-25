# DH Solution Homepage

Wix로 구축되어 있던 `www.dhsolu.com`의 정적 페이지를 GitHub Pages에서 서비스할 수 있도록 복제한 정적 홈페이지입니다.

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
