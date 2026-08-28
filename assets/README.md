# assets

배경/프로필 사진을 이 폴더에 넣습니다. (권장: 가로 1600px 이상, JPG, 각 300KB 내외로 압축)

## 치료실 사진 슬라이드 (필수 파일)

"치료실에서" 섹션의 가로 슬라이드는 아래 파일 이름을 그대로 사용합니다. 이 폴더에 저장만 하면 바로 표시됩니다.

| 파일 이름 | 내용 |
|-----------|------|
| `studio-1.jpg` | 핸드벨·타악기 앞에 앉아 있는 사진 |
| `studio-2.jpg` | 기타를 연주하는 사진 |

- 사진을 더 추가하려면 `index.html`의 `<ul class="carousel-track">` 안에 `<li class="carousel-slide"><img src="assets/studio-3.jpg" alt="..."></li>` 를 추가하면 됩니다. (슬라이드 개수·점 인디케이터는 자동)
- 저장 후 `git add assets && git commit -m "add studio photos"` 하면 자동으로 배포됩니다.

## 사진 교체 방법

`index.html` 상단 `:root` 안의 자리표시자를 실제 파일 경로로 바꾸면 됩니다.

```css
/* 변경 전 (그라데이션 자리표시자) */
--photo-1: radial-gradient(...), linear-gradient(...);

/* 변경 후 (실제 사진) */
--photo-1: linear-gradient(180deg, rgba(18,36,32,.5), rgba(18,36,32,.55)),
           url("assets/session-1.jpg");
```

- `--photo-1` : 프로그램 다음의 "음악이 머무는 자리에서…" 배경
- `--photo-2` : 하단 "지금 시작하세요" CTA 배경
- 히어로 배경 사진을 넣으려면 `.hero{ background: ... }` 규칙에도 같은 방식으로 `url("assets/hero.jpg")` 를 추가

앞의 `linear-gradient(...)` 는 사진 위에 덧씌우는 어두운 반투명 레이어라, 흰 글씨 가독성을 위해 그대로 두세요.

> 참고: GitHub Pages 버전에서만 사진 파일이 반영됩니다. Claude 아티팩트(미리보기)는 단일 파일이라 그라데이션 자리표시자가 유지됩니다.
