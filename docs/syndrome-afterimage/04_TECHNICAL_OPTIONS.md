# 웹 기술 후보 비교 — 선택 전 검증

**결론:** 엔진/프레임워크는 아직 선택하지 않는다. 공식 문서에서 기능이 존재한다는 사실과, 초보자가 이 프로젝트를 더 빠르고 안정적으로 완성할 수 있다는 주장은 다르다.

## 후보

| 후보 | 확인 가능한 장점 | 추가로 책임져야 할 부분 | 작은 POC |
|---|---|---|---|
| Phaser | 씬, 입력, 오디오 등 게임 개발용 시스템을 제공 | 라이프사이클, 스케일링, 자산 로딩, 모바일 브라우저 동작을 실제로 익혀야 함 | 한 화면, 대상 2–4개, 상호작용, 재시작, 크기 변경 |
| PixiJS | 2D 렌더링과 Ticker 기반 업데이트 제공 | 게임 상태·충돌·씬 흐름 등의 구성을 더 직접 설계할 수 있음 | 같은 상호작용을 구현하고 필요한 보조 코드 기록 |
| DOM/CSS + Canvas | 브라우저 기본 요소와 텍스트/UI를 활용할 수 있음 | 움직임·충돌·애니메이션을 어디까지 직접 구현할지 결정 필요 | 정적인 탐색/선택형 프로토타입부터 시작 |
| Three.js | 3D 그래픽을 위한 웹 라이브러리 | 3D 카메라·자산·조명·성능·조작 부담이 추가됨 | 3D가 핵심 요구로 확인되기 전에는 보류 |

## 비교 방법

두 후보를 넘겨짚어 동시에 선택하지 말고, 필요한 경우 Phaser와 DOM/Canvas 또는 Phaser와 PixiJS 중 최대 두 개만 동일한 요구사항으로 비교한다.

각 POC에서 기록할 항목:
- 첫 실행까지 걸린 실제 작업 단계
- 의존성·설정 파일 수와 이해하기 어려웠던 부분
- 입력 처리와 상태 변경의 복잡도
- 재시작·오류 처리·화면 크기 변경
- 브라우저에서 실제 실행한 결과
- 키보드/포인터 조작과 텍스트 가독성
- 테스트 작성·수정 난이도
- 실패한 시도와 해결에 든 시간

시간 기록은 해당 실험에서 관찰한 값으로만 보고하고 업계 표준이나 다른 사람의 생산성으로 일반화하지 않는다.

## 공식 문서

- [Phaser Scenes](https://docs.phaser.io/phaser/concepts/scenes)
- [Phaser Input](https://docs.phaser.io/phaser/concepts/input)
- [Phaser Audio](https://docs.phaser.io/phaser/concepts/audio)
- [PixiJS Ticker](https://pixijs.com/8.x/guides/components/ticker)
- [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN Web Audio autoplay](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Autoplay)

## 선택 금지 조건

프로토타입도 실행하지 않았거나, 후보별 요구사항이 서로 다르거나, 선택 근거가 단지 유명세/선호/공식 기능 목록뿐이라면 기술 선택은 보류한다.
