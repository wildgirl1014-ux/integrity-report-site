# 청렴 신고 사건 조회 페이지

## 구성
- index.html : 정적 페이지 (카드·필터·결과 건수·RSS 표시)
- data/cases.json : 청렴신고_사건데이터.csv 500건을 JSON으로 변환 (빈 값은 null)
- api/rss.js : korea.kr 보도자료 RSS(https://www.korea.kr/rss/pressrelease.xml)를 받아 JSON으로 중계하는 Vercel 함수 (CORS 회피, 10분 캐시)
- vercel.json : 배포 설정

## 배포 (둘 중 하나)
1) CLI: 이 폴더에서 `npx vercel` → 로그인 → 질문은 모두 Enter → 확인 후 `npx vercel --prod`
2) 웹: GitHub 저장소에 이 폴더를 올린 뒤 vercel.com → Add New → Project → Import (Framework Preset: Other)

## 확인 체크리스트
- 탭 제목에 "청렴", "신고" 포함
- 카드에 신고일자·신고유형·지역·처리상태 표시
- 신고유형/처리상태 칩으로 필터링
- "결과N건" 표시 (예: 금품수수+처리완료 → 결과71건)
- 오른쪽(모바일은 아래) 정책브리핑 보도자료 최신 8건
