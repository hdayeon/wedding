# 모바일 청첩장

빌드 도구 없는 정적 페이지. `index.html` 한 파일이 전부입니다.

**배포 주소:** https://hdayeon.github.io/wedding/

## 수정하기

- **이름·날짜·연락처·식장 주소** → `index.html` 안 `CONFIG` 객체 (달력, D-day, 길찾기 링크가 전부 여기에 연동됩니다)
- **인사말 문구, 혼주, 계좌번호** → `index.html` 본문 HTML
- **사진** → `images/` 폴더 ([안내](images/README.md))

## 로컬에서 보기

```sh
python3 -m http.server 8877
```

`file://`로 직접 열면 계좌 복사(Clipboard API)가 막히므로 서버로 여는 편이 정확합니다.

## 배포

`main` 브랜치에 push하면 1~2분 뒤 자동 반영됩니다.

## 주의

- `<head>`의 `og:image`는 카카오톡 미리보기용입니다. 절대경로(https://...)여야 하고, 1200×630 이미지를 `images/og.jpg`에 넣어야 합니다.
- 사진을 교체해도 카카오톡이 예전 미리보기를 캐싱합니다. [카카오 디버거](https://developers.kakao.com/tool/debugger/sharing)에서 캐시를 초기화하세요.
- 지도를 표시하려면 `index.html`의 `KAKAO_JS_KEY`에 카카오 JavaScript 키를 넣고, 카카오 개발자 콘솔의 플랫폼 > Web에 `https://hdayeon.github.io`를 등록해야 합니다. 키가 없어도 길찾기 버튼 3개는 동작합니다.
