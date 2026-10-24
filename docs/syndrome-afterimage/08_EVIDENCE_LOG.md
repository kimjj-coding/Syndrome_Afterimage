# 근거 기록 및 출처 목록

**마지막 확인:** 2026-10-24 (Asia/Seoul). 웹페이지와 기술 문서는 바뀔 수 있으므로 실제 구현 전에 링크와 내용이 여전히 유효한지 재확인한다.

## 주장별 기록

| ID | 주장 | 주요 출처 | 등급 | 분류 | 현재 결론과 한계 |
|---|---|---|---|---|---|
| E-01 | WCAG 2.2 SC 2.3.1에는 깜박임 빈도와 임계값 조건이 있다 | [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/), [SC 2.3.1 설명](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold) | A — 규범/공식 설명 | 확인됨 | 완전한 적합성 검토를 FPS나 “3Hz”만으로 끝내지 않는다. |
| E-02 | SC 2.3.2는 Level AAA이며 1초 구간 내 3회 초과 깜박임을 허용하지 않는다 | [W3C SC 2.3.2](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes.html) | A | 확인됨 | SC 2.3.1의 임계값 예외와 구분한다. |
| E-03 | Phaser는 씬을 논리적 게임 구간으로 다룬다 | [Phaser Scenes](https://docs.phaser.io/phaser/concepts/scenes) | A — 공식 기술 문서 | 기능 확인 | 이 프로젝트에서 더 쉽다는 증거는 아님. |
| E-04 | Phaser 입력 시스템은 키보드·마우스·터치·게임패드 이벤트를 처리한다 | [Phaser Input](https://docs.phaser.io/phaser/concepts/input) | A | 기능 확인 | 실제 입력 방식과 기기 지원 테스트가 남음. |
| E-05 | Phaser 사운드 매니저는 지원되면 Web Audio를 사용하고 Audio Tag로 대체할 수 있다 | [Phaser Audio](https://docs.phaser.io/phaser/concepts/audio) | A | 기능 확인 | 자동재생 제한은 별도 테스트 필요. |
| E-06 | PixiJS에는 프레임별 콜백을 처리하는 Ticker가 있다 | [PixiJS Ticker](https://pixijs.com/8.x/guides/components/ticker) | A | 기능 확인 | “PixiJS에는 게임 루프가 없다”는 과거의 과장된 주장은 폐기. 다른 게임 시스템은 별도로 필요할 수 있음. |
| E-07 | 브라우저는 사용자 동작 없이 시작하는 가청 재생을 막을 수 있다 | [MDN 자동재생](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Autoplay), [MDN Web Audio](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Best_practices) | A — 웹 플랫폼 문서 | 확인됨 | 소리 켜기 동작을 두고 실제 브라우저에서 시험. |
| E-08 | IndexedDB는 구조화된 대용량 클라이언트 데이터에 적합하고 Web Storage는 작은 데이터에 더 적합하다 | [MDN IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) | A | 확인됨 | 저장 요구가 작은 프로토타입은 더 단순한 방식부터 시험. |
| E-09 | PTSD는 여러 증상 범주와 다양한 경과를 보인다 | [NIMH PTSD](https://www.nimh.nih.gov/health/publications/post-traumatic-stress-disorder-ptsd) | A — 공공 보건기관 | 개괄적 사실 확인 | 행동 하나나 효과 하나로 진단하지 않는다. |
| E-10 | 조현병 증상은 다양하며 정신병적·음성·인지 범주를 포함하고, 대부분의 조현병 환자는 폭력적이지 않다 | [NIMH 조현병](https://www.nimh.nih.gov/health/publications/schizophrenia) | A | 개괄적 사실 확인 | 정신질환을 위험한 악당의 고정 원인으로 쓰지 않는다. |
| E-11 | 해리 경험은 다양하며 자신/세계와 단절된 느낌, 이인감·비현실감 등을 포함할 수 있다 | [NHS 해리성 장애](https://www.nhs.uk/mental-health/conditions/dissociative-disorders/) | A — 공공 의료기관 | 개괄적 사실 확인 | 시각적 표현은 창작적 은유이지 임상 지표가 아니다. |
| E-12 | INSIDE는 2D 퍼즐 플랫폼 게임으로 소개된다 | [Playdead](https://www.playdead.com/games/inside/index.php), [PlayStation 공식 소개](https://www.playstation.com/ko-kr/games/inside/) | A — 공식 소개 | 제품 설명 확인 | 저비용으로 같은 품질을 만들 수 있음을 증명하지 않는다. |
| E-13 | Little Nightmares는 탐색, 적대적 주민, 방 단위 위협/퍼즐, 사운드 디자인을 강조한다 | [Bandai Namco](https://www.bandainamcoent.com/games/little-nightmares) | A | 제품 설명 확인 | 취약한 주인공이면 공포가 자동으로 강해진다는 주장은 가설이다. |
| E-14 | Detention은 2D 사이드 스크롤·포인트 앤 클릭 요소를 사용하며 1960년대 대만을 배경으로 한다 | [Red Candle Games](https://redcandlegames.com/presskit/sheet.php?l=en&p=detention) | A | 개발사 설명 확인 | 문화·역사 요소는 별도 맥락 조사가 필요. |
| E-15 | Oxenfree는 대화 결정이 이야기와 관계에 영향을 주고 라디오가 세계를 조작하는 기능을 가진다 | [Night School Studio](https://nightschoolstudio.com/oxenfree/) | A | 개발사 설명 확인 | 큰 분기 구조가 이 프로젝트에 적합하다는 증거는 아님. |
| E-16 | Slay the Princess는 말하고 믿는 방식이 분기 서사에 영향을 준다고 소개된다 | [공식 사이트](https://www.slaytheprincess.com/) | A | 개발사 설명 확인 | 분기·아트·음성 분량은 비용 위험이며 그대로 복사할 기능이 아님. |
| E-17 | Edith Finch는 집을 탐색하며 가족 구성원의 이야기를 발견하는 구조다 | [Giant Sparrow](https://www.giantsparrow.com/games/finch/), [배급사](https://new.annapurnainteractive.com/en/games/what-remains-of-edith-finch) | A | 개발사/배급사 설명 확인 | 개별 미니게임을 많이 제작하는 것은 부담이 클 수 있음. |
| E-18 | Copilot 저장소 지침은 `.github/copilot-instructions.md`에 둘 수 있다 | [GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/customize-copilot/configure-custom-instructions/add-repository-instructions-in-your-ide) | A — 공식 제품 문서 | 기능 확인 | 지침은 결과를 돕지만 코드의 정확성을 보장하지 않는다. |
| E-19 | 탐색+추격+분기 선택이 이 프로젝트에 최선이다 | 이 프로젝트에 대한 직접 근거 없음 | — | 가설/보류 | 비교 실험 없이는 결정하지 않는다. |
| E-20 | MBV/RI 임계값이나 `뒤돌아보기 +5`가 검증된 심리 모델이다 | 검증 근거 확인되지 않음 | — | 미검증/임상 사실로 사용 금지 | 실제로 필요한지 재검토한다. |
| E-21 | 숨겨진 수치나 HUD 제거는 반드시 몰입을 높인다 | 보편적 법칙을 입증하는 근거 없음 | — | 가설 | UI가 있는 버전과 없는 버전을 시험하고 정보 접근성을 고려한다. |

## 출처 원칙

- 공식 문서는 해당 출처가 다루는 주장에 대해서는 높은 등급이지만, 무관한 설계 결론까지 증명하지는 않는다.
- 전문 보도·비평은 플레이 경험과 제작 선택을 해석하는 데 활용하되, 해석임을 표시한다.
- 위키·커뮤니티는 탐색용으로 쓰고 핵심 사실은 더 신뢰할 출처로 확인한다.
- 재미·공포·몰입·불안·동기·이해도에 대한 주장은 테스트로 뒷받침될 때까지 가설로 분류한다.
- 여러 요약에 복사된 문장을 독립적인 근거 여러 개로 세지 않는다.

## 추가 기술 문서

- [Phaser 씬](https://docs.phaser.io/phaser/concepts/scenes)
- [Phaser 입력](https://docs.phaser.io/phaser/concepts/input)
- [Phaser 오디오](https://docs.phaser.io/phaser/concepts/audio)
- [PixiJS Ticker](https://pixijs.com/8.x/guides/components/ticker)
- [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [MDN IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
- [MDN Web Audio 자동재생](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Autoplay)
- [GitHub Copilot 저장소 지침](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/customize-copilot/configure-custom-instructions/add-repository-instructions-in-your-ide)