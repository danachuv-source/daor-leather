# DAOR Leather 웹사이트 (팔라디오 · 암브라 · 마스트로또)

다오르(주)(DAOR CO., LTD.)의 가죽 브랜드 사이트. 정적 HTML 한 장(index.html) + img/ + media/. 빌드 없음.
미리보기: 이 폴더에서 `npx serve .` 또는 `python -m http.server` 후 브라우저로 열기.
배포: Netlify Drop(app.netlify.com/drop)에 폴더 또는 zip을 그대로 업로드.

## 구조
- index.html: CSS·JS 모두 인라인. 해시 라우팅.
  - `#home` 대문(팔라디오/암브라 두 패널만, 헤더·푸터 없음)
  - `#palladio`, `#ambra`, `#mastrotto` 브랜드 화면, `#palladio-{intro|articles|colors|house|craft|lwg|contact}`
  - 대문은 팔라디오·암브라 투톱만. 마스트로또는 메뉴·브랜드 화면에서만 노출
  - 브랜드 목록은 스크립트의 `BR`, 아티클 필터는 `LINES`
- 데이터: 스크립트 상단 `C`(컬러 hex·코드), `FAM`(컬러 계열), `A`(아티클 목록: key, name, line, thick, pvc, colors, desc)
  - line: PALLADIO / AMBRA / MASTROTTO. thick를 비우면 "두께 확인 중"으로 표시
- 검색: 왼쪽 위 검색창. `ART_KO`, `COL_KO`, `SEC_IX`에 한글 검색어·바로가기 키워드
- 아티클 상세: `openArt(key, color)` — 큰 사진 갤러리, 커서 위치 확대(마우스), 컬러 클릭 시 해당 사진으로 이동
- 문의: 방문자 정보를 수집하지 않음(폼 없음). 버튼을 누르면 대표전화 031-591-3900, info@daor.it 표시

## 가죽 사진 교체
- img/leather/<아티클 key>/ 안의 파일을 같은 이름으로 덮어쓰기
  - drape.jpg 대표 사진(목록 호버 확대, 상세 첫 장), detail.jpg 결 클로즈업, <컬러>.jpg 컬러별 사진
  - 컬러 파일명 규칙: 컬러명을 소문자로, 영문·숫자 외 문자는 '-' (예: "7733 L.GREY" → 7733-l-grey.jpg)
- 현재 사진은 모두 코드로 만든 예시. 교체 후 index.html의 `const PLACEHOLDER=true`를 false로 바꾸면 "예시 이미지" 표시가 사라짐
- 권장: 정사각형 1200px 이상 JPG. 전체 목록은 사진교체안내.txt

## 문구·디자인 원칙 (사용자 요청 사항)
- 클래식/프리미엄/협력/서비스/개척 같은 키워드를 직접적으로 쓰지 말 것. 에르메스 등 명품 사이트 톤의 절제된 표현
- 모던과 클래식, 프리미엄과 대중성의 공존. 너무 어둡거나 고전적이지 않게
- 팔라디오 = 프리미엄, 암브라 = 일상적이지만 고급스러운 라인. 두 브랜드 문구를 같게 쓰지 말 것
- 기간·시즌 표기 금지 (LWG 인증도 기간 없이 "LWG 골드 등급 인증")
- 실무 용어(출고, 재고, 거래처 등) 대신 브랜드 표현. "거래처"는 "파트너"
- 영어 표기가 필요하면 회사명은 "Daor", 로고 아래 "Dream Leather"
- AI 티 나는 이미지·영상은 쓰지 않음 (실사 선호)
- 방문자 연락처 등 개인정보 수집 기능 추가 금지

## 회사 정보 (푸터)
DAOR CO., LTD. · 다오르(주) / 경기도 남양주시 수동면 남가로 1589 / 대표이사 남찬우 · 사업자등록번호 132-81-88466 / 대표전화 031-591-3900 / www.daoritaly.it
