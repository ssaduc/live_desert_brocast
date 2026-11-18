# 연서 & 예서의 라이브 디저트 방송국

빌드 과정 없는 정적 사이트입니다. 폴더를 그대로 Vercel에 올리면 됩니다.

## 폴더 구성
- `index.html` : 게임 전체 (화면·소리·로직)
- `img/` : 연서(c1)·예서(c2) 표정 그림 12장 (normal, open, chew, spicy, yum, wink)
- `icons/` : 홈 화면 아이콘
- `manifest.webmanifest` : 휴대폰 홈 화면에 앱처럼 추가하기 위한 설정
- `vercel.json` : 그림 캐시 설정

## 배포 방법 1 — GitHub 연결 (추천: 나중에 고치기 쉬움)
1. GitHub에 새 저장소를 만들고 이 폴더의 파일을 모두 올립니다.
2. vercel.com → Add New → Project → 그 저장소를 Import 합니다.
3. Framework Preset은 **Other**, Build Command·Output Directory는 비워 둔 채 Deploy를 누릅니다.
4. 이후 GitHub에 파일을 바꿔 올리면 자동으로 다시 배포됩니다.

## 배포 방법 2 — Vercel CLI
```bash
npm i -g vercel
cd 이_폴더
vercel          # 처음: 로그인 후 질문에 Enter
vercel --prod   # 실제 주소로 배포
```

## 알아둘 점
- 이름·코인·상점 아이템·도감·등록한 그림은 각 기기 브라우저(localStorage)에 저장됩니다. 주소(도메인)가 바뀌면 처음부터 시작합니다.
- 제미나이 AI 목소리는 게임 안 🔑 AI 설정에서 기기마다 API 키를 넣어야 합니다. 키는 그 기기 브라우저에만 저장되고 사이트에는 들어 있지 않습니다.
- 휴대폰에서 주소를 연 뒤 Safari 공유 → 홈 화면에 추가 / Chrome 메뉴 → 홈 화면에 추가 를 하면 앱처럼 전체 화면으로 열립니다.
- 표정 그림을 바꾸려면 `img/` 안의 같은 이름 파일을 교체하면 됩니다 (투명 배경 WebP, 같은 크기 권장).
