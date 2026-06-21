# SANG SUB Game - Claude 작업 컨텍스트

## 저장소 정보
- **GitHub 저장소**: `ParkMura/sang-sub-game`
- **게임 URL**: https://parkmura.github.io/sang-sub-game/ringed.html
- **모바일 URL**: https://parkmura.github.io/sang-sub-game/ringed.html?mobile=1
- **메인 파일**: `ringed.html` (단일 HTML+JS 파일에 전체 게임 로직 포함)
- **원본 저장소**: https://github.com/programmer119/new-chat (bullet-noir-v2 폴더)

## 수정 방법
- `ringed.html` 파일을 직접 수정 후 master 브랜치에 push
- GitHub Pages가 자동 배포 (약 1~2분 소요)
- GitHub API 또는 gh CLI로 파일 수정 가능

## 지금까지 적용된 수정사항

| 항목 | 내용 |
|------|------|
| SPECIAL FORCES 버튼 | 숨김 (`drawSpecialForcesToggle` 함수에 return 추가) |
| CAM1/CAM2 버튼 | 숨김 (`drawCameraButtons` 함수에 return 추가) |
| 화면 밝기 | +40% (`filter: brightness(1.4)`) |
| 플레이어 총 색상 | 황금색 `rgba(255, 200, 50, 0.96)` |
| Kill/Wave 글씨 | 삭제 |
| HUD 크기 | 축소 (HP바, SKILL바 작게) |
| 시야각 | 140도 확장, 뒤쪽 어둡게 (darknes 0.88) |
| 미니맵 | 우상단 추가 (플레이어=황금점, 적=빨간점) |
| 이동속도 | 플레이어/적 모두 20% 감소 |
| 줌 | 10% 아웃 |
| 적 외관 | 빨간 얇은 테두리 |
| STA → SKILL | 스킬 에너지바로 교체 (킬 8마리 = 풀충전) |
| 비장의 스킬 | E키 또는 SKILL 버튼 → 3초 발칸포 광역 연사, 이동 불가 |

## 주요 코드 위치 (ringed.html)
- `drawHud()` - HUD 그리기 (HP바, SKILL바, 미니맵)
- `drawWeapon()` / `drawRifle()` - 총 색상
- `enemySpeed()` - 적 이동속도
- `drawEnemy()` - 적 그리기 (빨간 테두리)
- `drawSoftConeLight()` - 시야각 조명 콘
- `skillEnergy`, `skillActive`, `skillTimer` - 비장의 스킬 변수
- `handleSkillButtonClick()` - 스킬 버튼 클릭
- `drawMinimap()` - 미니맵
- `drawSkillButton()` - 스킬 버튼 UI

## 미구현 항목 (요청됨)
- 슬라이드 1: 브롤스타즈식 사선 시야
- 슬라이드 2: 주소창 숨기기
- 슬라이드 9~12: 발사 방식 변경 (산탄총/마취총/수류탄 조작 개편)
- 슬라이드 15-③④⑤⑥: 산탄총 데미지, 카메라 추적속도, 시야거리, 벽 뒤 차단
