# 소책자 웹 뷰어 (PC·모바일 반응형 페이지 플립)

`web_viewer` 폴더 = 인터넷에 올릴 한 세트입니다.

```
web_viewer/
├─ index.html   ← 뷰어 (PDF.js + StPageFlip)
└─ book.pdf     ← 빈 표지 1장 + 본문 17장 = 18페이지
```

- PC: 책 펼침면(좌우 2면), 모바일: 한 장씩 자동 전환
- 마우스/터치로 모서리를 잡아 넘기거나, 하단 ‹ › 버튼·키보드 ←→ 사용
- 인터넷 연결 시 CDN에서 라이브러리를 불러옵니다(별도 설치 없음)

## ⚠️ 먼저 알아둘 점
`index.html`을 더블클릭(file://)으로 열면 PDF가 안 보입니다.
브라우저 보안 정책 때문이며, **반드시 웹 서버에서** 열어야 합니다.

### 내 컴퓨터에서 미리보기 (둘 중 하나)
터미널에서 `web_viewer` 폴더로 이동 후:
```bash
python3 -m http.server 8000
```
→ 브라우저에서 `http://localhost:8000` 접속

## 무료 배포: GitHub Pages
1. github.com 가입 → 새 저장소(Repository) 생성 (Public)
2. `index.html`과 `book.pdf` 두 파일을 업로드(드래그&드롭) → Commit
3. 저장소 **Settings → Pages → Source: main 브랜치 / root** 선택 → Save
4. 1~2분 뒤 `https://아이디.github.io/저장소이름/` 주소로 전 세계 공개
   - 이 주소를 그대로 공유하면 PC·모바일 어디서든 열립니다.

> Netlify(netlify.com)도 가능: `web_viewer` 폴더를 사이트에 드래그하면 즉시 링크 생성.

## 표지 교체
나중에 표지가 나오면 `book.pdf`의 1페이지(빈 표지)만 교체하면 됩니다. 요청 주시면 합쳐 드릴게요.

## 참고
- 라이브러리: [PDF.js](https://mozilla.github.io/pdf.js/) · [StPageFlip](https://github.com/Nodlik/StPageFlip) (둘 다 무료/오픈소스)
- book.pdf가 약 27MB라 모바일에서 처음 로딩에 몇 초 걸릴 수 있습니다. 더 가볍게 원하면 PDF 화질 압축도 가능합니다.
