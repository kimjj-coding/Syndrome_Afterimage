# 《신드롬: 잔상》 상세 조사 통합 보고서 v0.1

> **기준일:** 2026-10-24 (Asia/Seoul)  
> **단계:** 조사·설계 검증 전 — 최종 게임 기획서가 아님  
> **목적:** 기존 조사 기록과 이번 일반 웹 조사를 합쳐, 다음에 무엇을 결정하고 무엇을 아직 결정하면 안 되는지 근거 중심으로 구분한다.

## 1. 결론 요약

현재 가장 타당한 다음 작업은 게임 전체의 설계 방향을 고르는 것이 아니라, **한 화면/작은 공간에서 단서를 조사하고 그 결과가 환경이나 텍스트에 반영되는 루프를 검증하는 것**이다. 이 시작점은 구현과 테스트의 범위를 줄이기 위한 연구 우선순위이지, 최종 장르나 카메라의 확정이 아니다.

기존 보고서에서 반복되었던 “탐험 + 퍼즐 + 추격 + 선택 + 다중 엔딩을 한 게임에 모두 넣는다”는 제안은 지금은 채택하지 않는다. 각 요소는 개별적으로 확인할 수 있어도 이들을 한꺼번에 묶었을 때 플레이 경험이 나아진다는 직접 근거는 없다. 특히 추격은 입력 타이밍·장애물·실패·재시작·애니메이션·사운드·접근성 테스트를 추가하므로, 기초 루프가 작동하는지 확인하기 전에 필수 기능으로 지정하면 안 된다.

기술 선택도 보류한다. Phaser에는 씬 관리와 키보드·마우스·터치 입력, 오디오 문서가 있고, PixiJS에는 프레임별 업데이트용 Ticker가 있다. 이는 기능의 존재를 확인하는 자료이지, 초보자가 해당 프로젝트를 더 빨리 완성한다는 증거가 아니다. 작은 POC(실행 검증)를 통해 비교해야 한다.

또한 정신건강을 묘사하는 허구적 연출은 의학적 진단과 분리해야 한다. PTSD, 해리·이인감·비현실감, 정신증적 경험, 조현병을 한 개념으로 묶거나, 진단·증상 수치를 플레이어의 도덕성이나 엔딩의 좋고 나쁨에 직결하는 설계는 채택하지 않는다. 시각·청각 효과는 실제 접근성 검사 대상이며, 효과를 줄여도 필수 게임 정보는 유지되어야 한다.

## 2. 연구 방법과 근거의 한계

이 문서는 기존 조사계획서, 진행현황표, 주장·출처 감사표, 과거 요약 보고서 및 공식 개발사·기술·보건기관·표준 자료를 바탕으로 작성했다. 조사 결과는 다음 분류로 다룬다.

- **확인된 사실:** 해당 공식 출처가 직접 설명하는 내용 또는 반복 가능한 공식 기준. 출처가 뒷받침하는 범위를 넘어 일반화하지 않는다.
- **출처 기반 해석:** 작품의 설명·특성에서 도출한 설계적 해석. 출처 자체가 보편 법칙을 증명하는 것은 아니다.
- **가설:** 이 프로젝트에서 실제 프로토타입이나 사용자 테스트로 검증해야 하는 제안.
- **보류/폐기:** 근거 부족, 안전 문제 또는 현재 범위와 맞지 않아 구현 지침으로 사용하지 않을 주장.

이번 작업은 일반 웹 조사이며, 심층리서치 도구를 사용한 결과가 아니다. 또한 여섯 게임을 처음부터 끝까지 직접 플레이하며 프레임 단위로 계측한 실험이나 임상 전문가의 검토를 수행한 것은 아니다. 공식 제품 소개는 기능을 확인하는 데 유용하지만, 어떤 기법이 재미·몰입·공포를 일으키는지, 제작에 실제로 얼마나 걸리는지, 이 프로젝트에서 더 잘 작동하는지는 별도의 관찰과 테스트가 필요하다. 출처가 제공하지 않는 제작 비용·플레이어 반응 수치를 만들어 내지 않았다.

## 3. 사례 조사: 작품의 기능과 적용 가능성은 다르다

### INSIDE — 환경 퍼즐 플랫폼 게임

Playdead 및 PlayStation의 공식 소개는 INSIDE를 2D 퍼즐 플랫폼 게임으로 다루며, 퍼즐과 행동이 결합한 경험임을 확인하는 근거가 된다. 이 작품을 참고할 질문은 “배경 설명을 길게 제공하지 않을 때, 환경과 장애물은 다음 행동을 어떻게 유도하는가?”이다. 작은 프로젝트에 옮길 수 있는 후보 원리는 배경·상호작용·진행 피드백의 연결이다. 반대로 고품질 애니메이션, 독특한 물리 상호작용, 촘촘한 시네마틱 연출을 복제하는 것은 범위와 제작 부담이 크다. 공식 소개만으로 환경 서사의 세부 작동 방식이나 특정 연출이 재미를 높인다는 인과를 증명하지는 못한다.

출처: [Playdead — INSIDE](https://www.playdead.com/games/inside/index.php), [PlayStation — INSIDE](https://www.playstation.com/ko-kr/games/inside/).

### Little Nightmares — 방 단위 위협과 탐색

Bandai Namco의 공식 소개는 탐색, 적대적인 주민을 피하는 행동, 위협과 퍼즐이 되는 방, 사운드 디자인을 강조한다. 여기서 조사할 질문은 “위험을 읽을 수 있는 공간과 명확한 행동 목표가 어떻게 연결되는가?”이다. 작은 프로젝트에서는 거대한 적 AI보다 하나의 방에 명확한 위험 표시·안전 지점·관찰 가능한 결과가 있는 실험이 더 현실적일 수 있다. 다만 “주인공이 약하면 언제나 공포가 강해진다”는 보편 법칙은 확인되지 않는다. 3D 환경과 고유한 적 애니메이션을 그대로 복제하는 것도 권하지 않는다.

출처: [Bandai Namco — Little Nightmares](https://www.bandainamcoent.com/games/little-nightmares).

### Detention — 장소 조사와 이야기 맥락

Red Candle Games의 공식 프레스 키트는 계엄령 시기의 1960년대 대만을 배경으로 한 호러, 2D 사이드 스크롤 및 포인트 앤 클릭 요소를 설명한다. 검토할 질문은 “조사하는 장소·물체가 단순한 퍼즐 조각을 넘어 더 넓은 이야기의 해석을 바꾸는가?”이다. 프로젝트에 적용할 수 있는 후보는 상호작용 규칙은 단순하게 두되, 단서가 장소의 의미를 바꾸도록 구성하는 방식이다. 역사·문화 맥락을 표면적인 장식으로 차용하면 안 되며, 관련 내용을 사용한다면 별도 출처와 맥락 검토가 필요하다.

출처: [Red Candle Games — Detention Press Kit](https://redcandlegames.com/presskit/sheet.php?l=en&p=detention), [한국어 소개](https://redcandlegames.com/presskit/sheet.php?l=kr&p=detention).

### Oxenfree — 대화와 선택의 가시적 반응

Night School Studio는 대화 선택이 스토리와 인물 관계에 영향을 주고, 라디오 장치가 게임 세계에 영향을 미치는 메커니즘을 공식 소개에서 설명한다. 이 사례를 통해 확인할 질문은 “선택 결과가 대화·관계·환경의 반응으로 어떻게 전달되는가?”이다. 소규모 프로젝트에 적용할 수 있는 후보는 전체 분기 트리보다, 선택 이후 짧은 대사나 다음 단서가 달라지는 제한적인 상태 변화다. 큰 대화량, 음성 연기, 모든 분기에 대응하는 별도 콘텐츠를 복제하면 제작·검수 비용이 빠르게 늘 수 있다.

출처: [Night School Studio — OXENFREE](https://nightschoolstudio.com/oxenfree/).

### Slay the Princess — 반복과 분기 서사

공식 사이트는 플레이어가 말하고 믿는 방식이 진행과 분기 서사에 영향을 주는 작품으로 소개한다. 여기서 조사할 질문은 “선택이 단순한 갈림길이 아닌 해석의 변화로 작동하려면, 이전 정보와 이후 반응을 어떻게 엮어야 하는가?”이다. 이 원리는 작은 상태 변화 실험에 참고할 수 있지만, 많은 분기와 변형 콘텐츠를 복제할 근거는 아니다. 이 프로젝트의 상태 변수나 엔딩 수는 작품 사례만으로 정하면 안 된다.

출처: [Slay the Princess — 공식 사이트](https://www.slaytheprincess.com/).

### What Remains of Edith Finch — 공간을 통한 이야기 발견

Giant Sparrow와 배급사 Annapurna Interactive는 집을 탐색하며 가족 이야기들을 발견하는 작품으로 소개한다. 이를 통해 볼 수 있는 질문은 “공간 이동과 오브젝트 조사가 이야기 접근 방식과 연결되는가?”이다. 적용할 수 있는 후보 원리는 탐색 동선과 이야기의 발견 순서를 연결하는 것이다. 반대로 많은 독립 미니게임, 연출, 고유한 상호작용 장면을 만드는 방식은 혼자 개발하는 작은 프로젝트에서 부담이 될 수 있다.

출처: [Giant Sparrow — What Remains of Edith Finch](https://www.giantsparrow.com/games/finch/), [Annapurna Interactive](https://new.annapurnainteractive.com/en/games/what-remains-of-edith-finch).

### 사례에서 얻을 수 있는 공통점

1. **메커니즘이 있다고 해서 도입 이유가 되는 것은 아니다.** 각 작품에서 선택·숨기·퍼즐·탐색이 확인되더라도, 프로젝트에서의 필요성은 별도 질문이다.
2. **피드백을 검증 대상으로 삼는다.** 플레이어가 무엇을 조사했으며 그 결과 무엇이 바뀌었는지 이해하는지를 테스트한다.
3. **제작 규모를 제품의 표면만 보고 추정하지 않는다.** 공식 페이지는 애니메이션 프레임, 레벨 수, 상태 조합, QA 작업량 같은 완전한 비용 자료를 제공하지 않는다.
4. **작품의 이야기와 자산을 복제하지 않고, 한 가지 작동 원리를 추출한다.** 예를 들어 “방 하나에서 단서가 의미를 바꾼다”를 실험하는 것과 특정 작품의 장면을 재현하는 것은 다르다.

## 4. 핵심 루프 후보 비교

### A. 탐색 → 단서 조사/비교 → 세계 반응

플레이어가 작은 공간에서 대상 두세 개를 관찰하고, 단서의 관계를 추론한 뒤 행동의 결과를 환경이나 텍스트 변화로 확인한다. 이는 상시적인 적 AI와 시간 제한 없이도 상호작용의 이해도, 단서의 명료함, 반응의 가시성을 분리해서 시험하기 쉽다. 위험은 변화가 너무 작거나 다음 목표가 보이지 않으면 반복 클릭이 될 수 있다는 점이다.

### B. 탐색 → 짧은 위협/회피 → 안전 구역 → 단서 해석

기초 단서 루프에 시간 압박과 위험 경고를 추가한다. 긴장감과 취약감을 강화할 수 있다는 것은 가설이며, 실제로는 플레이어가 단서를 잊거나 구간을 불공정하게 느낄 수도 있다. 실패 처리, 충돌 감지, 재시작, 위험 예고, 타이밍 접근성, 사운드·애니메이션 제작량을 함께 시험해야 한다.

### C. 정보 충돌/불확실성 → 선택 → 관찰 가능한 반응

상충하는 정보나 그럴듯한 두 선택지를 제시하고, 결정 이후 대사·방·후속 단서 중 일부만 바꾼다. 대규모 분기 트리 없이도 선택과 해석의 관계를 시험할 수 있다. 다만 선택지가 실제로 구분되지 않거나, 결과 반응이 없거나, 반응 이유를 나중에도 추론할 수 없다면 선택은 속임수 또는 무작위로 느껴질 수 있다.

### 권장하는 순서

먼저 A를 만들어 플레이어가 단서를 찾아 행동 후 변화를 알아차리는지 시험한다. A가 이해 가능해진 뒤에도 긴장감의 부족이 관찰되면 B를 추가해 비교한다. C는 이후 한두 개의 작은 상태 전이만으로 시험한다. 이 순서는 기능의 최종 우선순위가 아니라, 한 번에 하나의 중요한 질문을 검증하기 위한 실험 순서다.

## 5. 기술 선택: 문서에서 확인된 기능과 아직 모르는 것

| 선택지 | 확인 가능한 근거 | 지금 판단할 수 없는 점 | 가장 작은 검증 |
|---|---|---|---|
| Phaser | 공식 문서는 씬, 입력 시스템, 키보드·마우스·터치·게임패드, 오디오 지원을 설명한다. | 초보자가 프로젝트 요구사항을 더 빠르게 완성하는지, 예제 코드가 유지보수 가능한지. | 한 화면, 두세 개 상호작용, 씬 재시작, 크기 변경, 오디오 활성화, 빌드 실행. |
| PixiJS | 공식 문서는 프레임마다 콜백을 실행하는 Ticker를 설명한다. | 이동·충돌·상태·게임 흐름을 별도 구성하는 비용이 감당 가능한지. | 동일한 작은 화면에서 상태·입력·재시작 구조를 만들고 Phaser와 작업량을 비교. |
| DOM/CSS | 텍스트, 선택지, 설명, 포커스 및 표준 브라우저 UI에 적합한 기본 도구다. | 지속적인 이동·정교한 화면 효과가 핵심일 때 얼마나 추가 작업이 드는지. | 단서 조사 및 선택 중심 화면을 만들고 키보드 포커스, 반응, 반응형 크기를 확인. |
| Canvas 2D | 브라우저에서 스크립트로 직접 그리는 표준 API다. | 직접 렌더링·히트테스트·상태·게임 루프를 구현하는 것이 실제로 더 단순한지. | 같은 작은 화면을 구현하고 직접 작성해야 하는 코드와 오류를 기록. |
| Three.js / 3D | 공식 문서는 3D 그래픽 라이브러리 기능을 설명한다. | 3D가 프로젝트의 핵심 경험을 반드시 개선하는지와 작은 예산의 제작 부담. | 콘셉트 테스트가 3D 없이는 검증할 수 없을 때만 재검토. |

공식 문서: [Phaser Scenes](https://docs.phaser.io/phaser/concepts/scenes), [Phaser Input](https://docs.phaser.io/phaser/concepts/input), [Phaser Audio](https://docs.phaser.io/phaser/concepts/audio), [PixiJS Ticker](https://pixijs.com/8.x/guides/components/ticker), [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API), [Three.js Documentation](https://threejs.org/docs/).

비교 실험은 최대 두 후보로 제한하고, 같은 요구사항을 구현한다. 성공 여부는 “코드를 한 번 실행했다”가 아니라, 목표 브라우저에서 빌드·입력·상태 전이·재시작·화면 크기·접근성 요구를 재현할 수 있는지로 판단한다. 테스트하지 않은 프레임률 목표나 생산성 수치를 만들지 않는다.

웹 플랫폼의 추가 제약도 확인해야 한다. 브라우저는 사용자 동작 없이 시작하는 가청 재생을 차단할 수 있으며, 저장 API는 데이터 규모·동기성·실패 처리에 따라 적합성이 다르다. 작은 프로토타입에 복잡한 저장 시스템을 먼저 추가하기보다, 요구되는 데이터와 실패 시 동작을 확인한 뒤 가장 단순한 방법을 선택한다.

출처: [MDN — Autoplay guide](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Autoplay), [MDN — Web Audio best practices](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Best_practices), [MDN — IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API), [MDN — localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage).

## 6. 정신건강 표현: 검수 기준이지 진단 모델이 아님

NIMH의 PTSD 자료는 재경험, 회피, 각성·반응성, 인지·기분 변화 등 여러 증상 범주를 설명한다. 한 가지 시각·행동 특징만으로 진단을 내리는 것은 적절하지 않다. NHS는 해리성 경험 가운데 이인감(자신을 멀리서 관찰하는 것처럼 느껴짐)과 비현실감(주변 세계가 비현실적 또는 흐릿하게 느껴짐)을 설명하지만, 이를 모든 사람에게 동일하게 나타나는 “보호 모드”로 단순화하면 안 된다. 정신증적 경험과 조현병도 같은 말이 아니다. NIMH는 조현병의 증상이 개인마다 다르며 대부분의 조현병 환자가 폭력적이지 않다고 명시한다.

설계에 적용할 원칙은 다음과 같다.

- 진단명을 직접 쓰지 않고도 기억·두려움·불확실성·사회적 압박을 묘사할 수 있는지 먼저 살핀다.
- 초현실적인 방, 왜곡, 소리, 기억 조각은 창작적 은유임을 구분한다. 그것을 진단의 지표라고 단정하지 않는다.
- MBV/RI, 임계값, `뒤돌아보기 +5`, 6개 엔딩은 검증되지 않은 설계 아이디어다. 생존하더라도 의학적 측정값이나 임상 점수로 정의하지 않는다.
- 고통을 도덕 점수·벌·나쁜 사람의 표식으로 만들지 않는다. 정신질환을 폭력성·악행·예측 불가능성의 기본 원인으로 쓰지 않는다.
- 민감한 주제를 포함하게 될 경우 비그래픽 표현, 내용 안내, 효과 감소 옵션, 적절한 전문가/당사자 검토를 고려한다. 자해를 구체적으로 묘사하거나 미화하는 방향은 채택하지 않는다.

출처: [NIMH — PTSD](https://www.nimh.nih.gov/health/publications/post-traumatic-stress-disorder-ptsd), [NIMH — Schizophrenia](https://www.nimh.nih.gov/health/publications/schizophrenia), [NHS — Dissociative disorders](https://www.nhs.uk/mental-health/conditions/dissociative-disorders/). 이 자료는 개념 구분과 주의점을 뒷받침하며, 특정 게임 효과의 임상적 정확성을 인증하지 않는다.

## 7. 접근성: 표준 요구와 좋은 설계 권고 분리

WCAG 2.2 성공 기준 SC 2.3.1(Level A)은 어떤 1초 구간에서도 세 번을 초과하는 깜박임을 허용하지 않거나, 정의된 일반·적색 깜박임 임계값 아래일 것을 요구한다. 이는 흔히 “3Hz 이하”라고 단순화되지만, 깜박임의 정의와 휘도·적색 변화 및 화면 면적 조건을 함께 봐야 한다. SC 2.3.2(Level AAA)는 한 1초 구간에서 세 번을 초과하는 깜박임을 허용하지 않는 더 엄격한 기준이다. 상호작용으로 유발되는 불필요한 움직임을 끌 수 있게 하는 SC 2.3.3(Level AAA)도 참고할 수 있으나, 각 기준의 적용 범위와 적합성 등급을 구분해 기록해야 한다.

프로젝트 수준의 권고는 다음과 같다.

- 강한 깜박임을 사용하지 않는 것이 우선이며, 실제 효과가 기준을 충족하는지 빌드/녹화 화면으로 검토한다.
- 효과 감소 모드에서 블러·노이즈·왜곡을 줄이거나 끌 수 있게 하되, 퍼즐 정보와 상호작용 결과는 남긴다.
- 중요한 소리 정보를 오디오만으로, 중요한 상태를 색상만으로 전달하지 않도록 대체 큐를 고려한다. 다만 WCAG의 자막 조항을 게임 내 모든 효과음에 무차별적으로 확대 해석하지 않는다.
- 키보드·포인터, 포커스 표시, 텍스트 가독성, 화면 크기 변화, 오디오 시작/음소거/볼륨을 목표 브라우저에서 테스트한다.
- 일부 항목의 검사만으로 “WCAG 전체 준수”를 주장하지 않는다.

출처: [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/), [SC 2.3.1](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold), [SC 2.3.2](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes.html), [SC 2.3.3](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html).

## 8. MVP 후보와 플레이테스트

### 첫 번째 실험

- 공간 하나 또는 한 화면.
- 상호작용 대상 2~4개.
- 단서 2~3개.
- 행동 후 확인 가능한 텍스트/환경 반응 하나.
- 재시작 방법 하나.
- 선택을 실험한다면 엔딩 대신 짧은 반응만 바꾸는 두 선택지.
- 적 AI, 대규모 분기, 여러 스테이지, 큰 인벤토리, 고빈도 왜곡, 3D를 기본 요구사항으로 넣지 않는다.

테스터에게 해법을 미리 설명하지 않는다. 첫 행동과 이유, 어떤 대상을 단서로 봤는지, 무엇을 이해했는지, 행동 이후의 변화를 알아차렸는지, 언제 반복 클릭했는지, 다음 행동을 무엇으로 예상했는지 관찰한다. 효과·텍스트·조작의 불편함도 기록한다.

### 임시 통과 신호

1. 실행 가능한 단서를 하나 이상 찾는다.
2. 단서의 의미 또는 무엇이 아직 불분명한지 말할 수 있다.
3. 핵심 행동 이후 상태 변화를 알아차린다.
4. 도움 없이 재시작할 수 있다.
5. 필수 정보가 색상·오디오·왜곡 하나에만 의존하지 않는다.

이는 첫 실험을 위한 가설이며 업계 표준 수치가 아니다. 실패하면 기능을 더 추가하기 전에 목표, 상호작용 표시, 단서 내용, 반응의 가시성을 단순화한다.

### 후속 실험

- **위협/회피:** 기초 루프가 이해 가능해진 후 한 장면만 추가해 긴장감 증가와 단서 이해 방해를 비교한다. 위험 예고와 실패·재시작이 공정하다고 느껴지는지도 관찰한다.
- **선택:** 의미 있게 다른 두 선택지를 두고 의도와 반응을 사후에 설명할 수 있는지 본다. 한 가지 선택을 시험하는 데 다중 엔딩 전체를 만들 필요는 없다.
- **기술:** 같은 기능을 최대 두 후보 기술로 구현하고 빌드, 입력, 재시작, 크기 변경, 오디오 시작, 상태 추적의 오류와 작업량을 기록한다.

## 9. 단계별 로드맵과 완료 조건

| 단계 | 작업 | 통과 조건 | 실패 시 대안 |
|---|---|---|---|
| G0 범위 | 플랫폼·예산·제약 기록 | 브라우저 목표와 미결정 항목이 명확함 | 범위를 축소하고 요구사항을 다시 정리 |
| G1 근거 감사 | 핵심 주장과 원문 대조 | URL이 열리고 주장 범위가 정확히 기록됨 | 근거 없는 주장을 가설/보류로 낮춤 |
| G2 루프 | A를 명세하고 B/C와 질문 기준 비교 | 각 실험이 하나의 질문과 관찰 기준을 가짐 | 탐색/단서 상호작용으로 축소 |
| G3 프로토타입 | 작은 공간·단서·반응·재시작 | 플레이어가 핵심 행동과 변화를 설명 가능 | 정보 및 상호작용 피드백 수정 |
| G4 기술 검증 | 최대 두 후보에서 같은 기능 실행 | 빌드·입력·상태·재시작·크기 변경 테스트 가능 | 더 단순한 DOM/Canvas 또는 다른 후보 실험 |
| G5 접근성·안전 | 효과·키보드·텍스트·사운드 점검 | 효과 감소 모드에서 정보와 조작이 유지됨 | 효과 제거 또는 대체 단서 제공 |
| G6 선택·서사 | 루프 뒤에 작은 분기 추가 | 상태 변화가 테스트 가능하고 결과 근거가 있음 | 분기 수 감소 또는 반응형 선택으로 대체 |
| G7 제작 규모 | 에셋·라이선스·콘텐츠 목록 | 사용 조건과 작업량을 기록 | 에셋·애니메이션·장면 수 축소 |
| G8 Copilot 명세 | 승인 기능을 입력/상태/출력/예외/테스트로 명세 | 생성 코드의 검증 조건이 구체적임 | 구현 프롬프트 전에 명세 보완 |
| G9 수직 슬라이스 | 확인된 루프의 짧은 플레이 구간 | 재현 가능하고 확장 가치가 있음 | 수정·축소 또는 기능/프로젝트 중단 판단 |

## 10. 기존 주장의 갱신 상태

| 기존 주장/제안 | 현재 상태 | 이유 |
|---|---|---|
| 브라우저 게임 | 유지 | 사용자 목표로 확정된 범위. |
| 탐색 + 단서 해석 | 첫 실험 후보 | 낮은 범위로 핵심 상호작용을 시험하기에 적합한 시작점이지만, 재미는 검증되지 않음. |
| 추격은 MVP 필수 | 보류/철회 | 필요성을 뒷받침할 비교 실험이 없고 구현·접근성 비용이 높음. |
| 탑다운/사이드스크롤/2.5D 중 하나 확정 | 보류 | 지금은 루프와 정보 흐름도 미검증. |
| Phaser + TypeScript | 후보 | 공식 기능이 있어도 개인별 생산성을 증명하지 않음. |
| PixiJS에는 게임 루프가 없다 | 철회 | PixiJS 공식 Ticker는 프레임별 콜백을 실행할 수 있음. |
| `MBV/RI`, 임계값, `뒤돌아보기 +5`, 6개 엔딩 | 미검증 | 공식·임상 근거가 없고 실제 플레이 테스트도 없음. |
| 정신건강 수치가 엔딩의 도덕/임상 점수 역할 | 채택하지 않음 | 낙인과 근거 없는 진단적 의미를 만들 위험. |
| “3Hz 이하”만으로 WCAG 적합 판정 | 정밀화 | SC 2.3.1의 기준에는 1초 구간뿐 아니라 임계값·깜박임 정의도 포함됨. |
| 무료 에셋은 자유롭게 사용 가능 | 폐기 | 에셋마다 라이선스·수정·배포 조건을 확인해야 함. |

## 11. 다음 조사 우선순위

1. **P1 — 단서와 피드백:** 상호작용 대상을 알아보는 데 필요한 신호, 단서의 관계, 반응의 가시성을 테스트한다.
2. **P1 — 소수 사례 심층 관찰:** 위 여섯 사례 중 실제로 볼 수 있는 플레이 영상/플레이 구간을 선택해 행동–피드백–실패/재시도–정보 전달을 타임라인으로 기록한다. 공식 소개로 확인되지 않는 세부를 추측하지 않는다.
3. **P1 — 접근성 체크 절차:** 실제 효과를 SC 2.3.1 및 다른 적용 가능한 기준과 연결하고, 키보드/포커스/대체 단서를 직접 시험한다.
4. **P2 — 기술 POC:** 루프의 입력 요구가 좁혀진 뒤 Phaser 대 DOM/Canvas를 먼저 비교하고, PixiJS는 렌더링 요구가 이를 정당화할 때 포함한다.
5. **P2 — 저장·오디오·배포:** 실제 필요한 데이터만 저장하고 브라우저 자동재생 제한, 빌드·호스팅, 권한, 에셋 라이선스를 확인한다.
6. **P3 — 스토리/엔딩/GDD:** 루프와 안전·접근성 원칙이 검증된 다음에 작성한다.

## 12. 출처 목록

### 게임 공식 자료
- [Playdead — INSIDE](https://www.playdead.com/games/inside/index.php)
- [PlayStation — INSIDE](https://www.playstation.com/ko-kr/games/inside/)
- [Bandai Namco — Little Nightmares](https://www.bandainamcoent.com/games/little-nightmares)
- [Red Candle Games — Detention Press Kit](https://redcandlegames.com/presskit/sheet.php?l=en&p=detention)
- [Night School Studio — OXENFREE](https://nightschoolstudio.com/oxenfree/)
- [Slay the Princess — Official Site](https://www.slaytheprincess.com/)
- [Giant Sparrow — What Remains of Edith Finch](https://www.giantsparrow.com/games/finch/)
- [Annapurna Interactive — What Remains of Edith Finch](https://new.annapurnainteractive.com/en/games/what-remains-of-edith-finch)

### 기술·표준·공공보건
- [W3C — Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/)
- [W3C — SC 2.3.1 Three Flashes or Below Threshold](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold)
- [W3C — SC 2.3.2 Three Flashes](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes.html)
- [W3C — SC 2.3.3 Animation from Interactions](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html)
- [Phaser — Scenes](https://docs.phaser.io/phaser/concepts/scenes)
- [Phaser — Input](https://docs.phaser.io/phaser/concepts/input)
- [Phaser — Audio](https://docs.phaser.io/phaser/concepts/audio)
- [PixiJS — Ticker](https://pixijs.com/8.x/guides/components/ticker)
- [MDN — Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN — Autoplay](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Autoplay)
- [MDN — Web Audio best practices](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Best_practices)
- [MDN — IndexedDB API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
- [MDN — localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [NIMH — PTSD](https://www.nimh.nih.gov/health/publications/post-traumatic-stress-disorder-ptsd)
- [NIMH — Schizophrenia](https://www.nimh.nih.gov/health/publications/schizophrenia)
- [NHS — Dissociative disorders](https://www.nhs.uk/mental-health/conditions/dissociative-disorders/)
- [GitHub Docs — Repository instructions for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/customize-copilot/configure-custom-instructions/add-repository-instructions-in-your-ide)

## 13. 최종 판단

현재 단계에서 “무엇을 만들기로 결정했는가?”보다 중요한 것은 “어떤 가정이 아직 증명되지 않았는가?”를 보존하는 것이다. 먼저 작은 단서·반응 루프를 시험하고, 결과가 관찰 가능하고 재현될 때에만 위협·회피·분기·고급 시각 효과를 차례로 비교한다. 검증에 실패하면 기능을 더하는 것이 아니라 축소·수정·제외 중 하나를 선택한다.