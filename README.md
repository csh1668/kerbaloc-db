# kerbaloc-db

[KerbaLoc](https://github.com/csh1668/kerbaloc) 번역팩 데이터베이스 — KSP 1.12.x 한국어(ko) 번역팩의 정본 저장소.

- **다운로드**: 계정 불필요. `kerbaloc db list` / `kerbaloc db install <ModId>` 또는 이 레포에서 직접.
- **기여**: 팩 디렉터리를 추가하는 PR. (원클릭 익명 업로드 프록시는 준비 중 — 그 전까지는 GitHub PR로.)
- 모든 PR은 CI가 자동 검증(cfg 라운드트립, 스키마, variantId 형식)하고 머지 후 인덱스가 자동 재생성됩니다.

## 구조

```
packs/<ModId>/ko/variants/<variantId>/
├── pack.json            # kerbaloc/pack@1 — 메타(대상 소스 해시, 커버리지, 모델)
├── Localization/ko.cfg  # Localization { ko { … } } — BOM 없는 UTF-8
└── Patches/*.cfg        # (선택) 비태그형 모드용 ModuleManager 패치
glossary/core.ko.json    # 코어 용어집
blacklist.json           # 번역 금지 목록 (모드/키/패턴)
index/ko.json            # CI 자동 생성 — 직접 수정 금지
```

- `variantId` = `YYYY-MM-DD-<method>-<nick>` (소문자·숫자·하이픈). 같은 모드에 여러 변형 공존 가능.
- 팩은 게임의 en-us를 **교체하지 않고 ko 노드를 추가**합니다 — 미번역 키는 자동 영어 폴백.

설계 문서: kerbaloc 레포의 `docs/superpowers/specs/`
