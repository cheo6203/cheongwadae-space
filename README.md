# 청와대 공간 변천도

대통령기록관 「이달의 기록 — 청와대」(2022년 5월)에 실린 관련기록 61건과 공개 자료를 바탕으로, 청와대 경내 건축 공간의 변천(1939년~현재)을 CAD·블루프린트풍 3D 투시도로 재구성한 웹페이지입니다. 실측 설계도가 아닌 참고용 재구성 자료입니다.

## 주요 기능

- **시간 슬라이더**: 9개 시기 탭(1939 총독관사기 ~ 2025 대통령비서실 복귀)과 슬라이더로 연도를 옮기면 건물이 그려지고(공사) 철거됩니다.
- **3D 투시도**: 투시·전경·평면·남측 입면 4가지 보기, 북악산 지형(공개 DEM)과 담장·도로·수목(OpenStreetMap).
- **실사 보기**: 현재 모습을 사진 참고 색상으로 표현합니다.
- **건물 정보**: 건물을 누르면 그 시점의 상태, 연혁, 관련기록, 사진·영상 링크가 나옵니다.
- **층별 평면·내부 보기**: 구 본관(1988년 평면도 판독), 본관·영빈관(공식 설명·사진 참고 추정).
- **다운로드 센터**: 배치도·투시도·건물별 평면도(A3 PDF), 투시도 원본 PNG, 3D 프린트용 모형(STL), 데이터(JSON·GeoJSON·CSV·Markdown)를 골라 ZIP 한 개로 받습니다. 배치도·투시도·경내 지형 모형은 슬라이더 시점에 존재가 확인된 건물만 담습니다.
- **3D 프린트 모형**: 경내 지형 모형(지형+건물, 가로 200mm 이내 자동 축척)과 건물 10동의 개별 모형(받침판 포함). 단위 mm, 닫힌 입체로 만들어 슬라이서에서 바로 불러올 수 있습니다.
- **레고 모형**: 메뉴의 「레고 모형」에서 본관·영빈관 1:300 브릭 모형을 3D로 보고, 슬라이더로 조립 순서(본관 102단계, 영빈관 58단계)를 따라갈 수 있습니다. 「실사 배치에 앉히기」를 누르면 실사 보기 화면의 원래 건물 자리에 레고 모형이 내려앉습니다. 부품 목록(CSV)·BrickLink 주문 목록(XML)·LDraw 설계(.ldr)는 페이지에서 바로 만들어 내려받고, 조립 설명서 PDF와 조립 영상은 `lego/` 폴더 파일을 씁니다. 비공식 자료이며 LEGO® 그룹과 무관합니다.
- **기록물 바로가기**: 관련기록 61건은 대통령기록관 기록 상세 페이지(`https://www.pa.go.kr/View/기록건번호_I.do`)로 연결됩니다. 참고문헌 링크도 새 창으로 열립니다.

## 근거 등급

| 등급 | 뜻 |
|---|---|
| A | 외곽선은 OpenStreetMap 실측, 높이·지붕은 사진 참고 추정 |
| B | 1988년 촬영 평면도 사진 판독(구 본관) |
| C | 공식 설명·사진 참고 형태 추정(본관) |
| D | 면적만 알려진 건물의 표현 |

건립 연도를 확인하지 못한 건물(서별관·칠궁 등)과 주변 시가지 건물은 현재 시기에만 그립니다. 담장·도로·녹지·경내 경계는 현재(2026) 기준입니다.

## 파일 구성

```
index.html   페이지 전체(단일 파일, 레고 모형 데이터 포함)
lego/        레고 조립 설명서 PDF(본관·영빈관)와 조립 영상 MP4
.nojekyll    GitHub Pages가 Jekyll 처리를 건너뛰도록 하는 빈 파일
README.md    이 문서
```

외부 라이브러리는 CDN에서 불러옵니다: three.js 0.160(jsDelivr), jsPDF 2.5.1·JSZip 3.10.1(cdnjs), 글꼴 IBM Plex Mono·Nanum Gothic Coding(Google Fonts). 인터넷이 연결된 환경에서 열어야 합니다.

## GitHub Pages로 발행하기

1. GitHub에서 새 저장소를 만듭니다(예: `cheongwadae-space`, Public).
2. 이 폴더의 파일을 올립니다.
   - 웹에서: 저장소의 **Add file → Upload files**로 `index.html`, `README.md`, `.nojekyll`과 `lego` 폴더를 통째로 끌어 넣고 커밋합니다(폴더 구조를 그대로 유지해야 설명서·영상 버튼이 동작합니다).
   - 명령줄에서:
     ```
     git remote add origin https://github.com/<계정>/cheongwadae-space.git
     git push -u origin main
     ```
3. 저장소의 **Settings → Pages**에서 Source를 **Deploy from a branch**, Branch를 `main` / `/(root)`로 저장합니다.
4. 1~2분 뒤 `https://<계정>.github.io/cheongwadae-space/`에서 열립니다.

주소 끝에 `#y1994`처럼 연도를 붙이면 그 시점으로 열리고, `#y1994-gubon`처럼 건물 id를 붙이면 그 건물이 선택된 상태로 열립니다.

## 로컬에서 보기

`index.html`은 ES 모듈을 쓰므로 파일을 더블클릭하지 말고 간단한 웹서버로 엽니다.

```
python3 -m http.server 8000
# 브라우저에서 http://localhost:8000
```

## 자료 출처

1. 대통령기록관 대통령기록포털, 이달의 기록 「청와대」(2022.5). 소개글과 관련기록 61건. https://www.pa.go.kr/portal/online_contents/instant_record/instantRecordList.do
2. 대통령기록관 대통령웹기록, 제19대 대통령 청와대 누리집 「청와대 소개 및 역사」. http://webarchives.pa.go.kr/19th/www.president.go.kr/about/history?section=0
3. 국사편찬위원회 우리역사넷 e영상역사관, 「청와대 본관 평면도」(1988.01.06 촬영). https://www.ehistory.go.kr/view/photo?mediaid=10811&mediasrcgbn=PT
4. OpenStreetMap contributors, 건물·정원·경계·도로·수목(ODbL). https://www.openstreetmap.org/copyright
5. 서울경제, 「[건축과 도시-청와대 본관] 품격을 짓고 국격을 담다」. https://www.sedaily.com/NewsView/269QSVA2RI
6. 위키백과, 「청와대」(여민관 준공 연도, 2차 자료). https://ko.wikipedia.org/wiki/청와대
7. 뉴시스, 「청와대 '모형 복원' 논란…옛 본관은 어떤 곳?」(2022.07.24). https://www.newsis.com/view/NISX20220724_0001954109
8. AWS Open Data, Terrain Tiles(Terrarium). https://registry.opendata.aws/terrain-tiles/
9. 서울시 내 손안에 서울, 「청와대의 정수! 본관 내부는 어떤 모습일까?」(2022). https://mediahub.seoul.go.kr/archives/2004832
10. 사진·영상 링크 목록: e영상역사관·정책브리핑·KTV·언론사 공개 자료(2026.09.27 조사). 링크만 제공하며 원 저작물은 각 출처에 있습니다.
11. 세계일보, 「청와대 관람 8월 1일부터 중단…집무실 이전 완료 후 재개」(2025.06.10). https://www.segye.com/newsView/20250610517191
12. 서울신문, 「오늘부터 청와대 관람 일시 중단」(2025.08.01). https://www1.seoul.co.kr/news/society/2025/08/01/20250801017009
13. 한국일보, 「청와대 새 본관 어제 준공」(1991.09.05). https://www.hankookilbo.com/news/article/199109050084985557
14. 경향신문, 「청와대 시대에도 '관저 복귀'는 언제」(2026.02.15). https://www.khan.co.kr/article/202602150955001

## 이용 고지

- 지도 데이터 © OpenStreetMap contributors, Open Database License(ODbL). 이 페이지에서 내려받은 GeoJSON 등 파생 데이터를 다시 배포할 때도 같은 표시가 필요합니다.
- 지형 자료는 AWS Terrain Tiles(Mapzen, SRTM 등 공개 표고자료)를 25m 격자로 보간한 것입니다.
- 사진·영상은 이 저장소에 포함되지 않으며, 페이지는 원 출처로 가는 링크만 제공합니다.
- 코드 라이선스는 저장소 소유자가 정해 `LICENSE` 파일로 추가하십시오.
