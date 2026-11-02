# SecTools

인하우스 보안 담당자의 취약점 진단 · 자동화 도구 모음 포털 (GitHub Pages)

## 구조
```
.
├── index.html        # 포털 UI (카테고리 탭, 검색, 도구 카드)
├── data/tools.json   # 사이트 정보 · 카테고리 · 도구 목록
└── .nojekyll         # Jekyll 처리 비활성화
```

## 도구 추가 방법
`data/tools.json`의 `tools` 배열에 항목 추가만 하면 됨. HTML 수정 불필요.

```json
{
  "name": "도구명(레포명 권장)",
  "category": "web",            // categories[].id 중 하나
  "status": "active",           // active | planned | research
  "summary": "한 줄 설명",
  "tags": ["Recon"],
  "repo": "https://github.com/yun-sectools/도구명",
  "docs": ""
}
```

## 카테고리 추가
`categories` 배열에 `{ "id", "name", "icon", "desc" }` 추가 시 탭·섹션 자동 생성.

## 로컬 확인
```bash
python3 -m http.server 8000
# http://localhost:8000
```

## 사용 원칙
허가된 자산에 한해 사용. 운영 환경 스캔 시 사전 승인 및 영향도 검토 필요.
