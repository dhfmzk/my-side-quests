# My Side Quests Design

## Goal

`My Side Quests`를 vibe-coding 사이드 프로젝트용 가벼운 GitHub 아카이브로 설계한다.
최초 설계는 퀘스트 감성을 강하게 두었지만, 사용자 피드백에 따라 실제 산출물은 작업 기록과
회고록에 더 가깝게 수정한다. `Side Quest`는 레포 이름에서 오는 분위기일 뿐, 기록 규칙이
되어서는 안 된다.

## Reference Findings

- `multitudes/portfolio`: 기능 목록보다 맥락, 취향, 회고를 섞는 방식.
- `TheSherlockHomie/100DaysOfCode-log`, `james-priest/100-days-of-code-log`:
  진행, 배움, 생각을 읽히는 로그로 남기는 방식.
- `filipecalegario/awesome-vibe-coding`: vibe-coding 용어와 맥락.
- `bradtraversy/50projects50days`: 많은 작은 프로젝트를 간결한 표로 정리하는 방식.

## Subagent Draft Review

세 서브에이전트가 독립 초안을 냈다.

- Draft 1: `Quest Brief`, `Why I Started`, `Built So Far`, `Loot`,
  `If I Revisit This` 같은 절제된 퀘스트 로그 은유를 제안했다.
- Draft 2: `quests/<year>-<slug>/quest.md`, 선택적 스크린샷, 단순 frontmatter,
  명확한 상태 분류를 제안했다.
- Draft 3: 과한 게임 말투, 유지보수 부담, 포트폴리오화, 모호한 회고, 깨진 링크를 주요 실패
  모드로 공격했다.

적대적 리뷰가 가장 중요한 제약이었지만, 첫 결과물은 여전히 빡빡했다. 최종 수정안은 퀘스트
은유를 더 줄이고, 사용자가 오래된 작업을 부담 없이 회고할 수 있는 질문형 메모장에 가깝게 둔다.

## Architecture

레포는 세 문서 층으로 구성한다.

- `README.md`: 짧은 선언, 수동 작업 목록, 느슨한 작성 기준, 레퍼런스.
- `templates/work-log.template.md`: 단일 작업 회고를 위한 복사 가능한 템플릿.
- `quests/<year>-<slug>/README.md`: 앞으로 템플릿을 복사해 만들 실제 작업 기록.

첫 버전에는 정적 사이트 생성기, JSON 인덱스, 자동화, 별도 블로그 엔진을 넣지 않는다. 이
아카이브는 피하는 것보다 업데이트하는 것이 더 쉬워야 한다.

## Entry Shape

각 기록은 아래 질문에 느슨하게 답하면 충분하다.

- 이 작업은 뭐였나?
- 왜 만들었나?
- 실제로 무엇을 했나?
- 지금 돌아보면 어떤 기억이나 판단이 남나?
- 남은 링크나 스크린샷이 있나?
- 지금의 한 줄 회고는 무엇인가?

완성도보다 기억과 회고가 더 중요하다.

## Removed Strictness

아래 요소는 과해서 제거했다.

- 상태 taxonomy
- machine-readable frontmatter
- `Keep / Drop`, `Continue?` 같은 판정 강제
- "규칙"이라는 강한 섹션명
- 퀘스트스러운 표시명

## Tone Direction

- 퀘스트 언어는 README의 이름과 약한 분위기에만 남긴다.
- 제목과 템플릿은 작업 기록처럼 읽혀야 한다.
- 중단작과 실패작도 기록할 수 있다.
- 일반적인 교훈을 강제하지 않는다.
- 스크린샷과 라이브 데모를 필수로 만들지 않는다.
- 결론은 교훈, 감상, 미련, 포기 모두 가능하다.

## File Decisions

생성 또는 수정한 파일:

- `README.md`: 루트 아카이브 안내와 인덱스.
- `templates/work-log.template.md`: 느슨한 작업 회고 템플릿.
- `docs/superpowers/specs/2026-05-06-my-side-quests-design.md`: 이 설계 기록.

미룬 것:

- `quests/`: 첫 실제 작업을 보관할 때 생성한다.
- `meta/status-taxonomy.md`: 상태 분류를 쓰지 않기로 해서 필요 없다.
- GitHub Pages: 둘러볼 만한 항목 수가 생기기 전까지는 필요 없다.

## Self-Review

- Placeholder scan: `templates/work-log.template.md`의 꺾쇠 placeholder는 템플릿 마커로 의도된 것이다.
- Scope check: 애플리케이션이 아니라 문서와 템플릿 변경이다.
- Ambiguity check: 작업 기록 중심, 선택 산출물, 느슨한 톤이 명시되어 있다.
- Maintenance check: 기본값은 작업 하나당 markdown 파일 하나다.
