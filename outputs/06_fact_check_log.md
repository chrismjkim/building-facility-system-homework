# 06. Fact-check and consistency log

검토일: 2026-05-31  
검토 대상: `outputs/00_assignment_scope.md` ~ `outputs/05_heat_pump_smart_grid_review.md`  
수정 대상: 이 파일(`outputs/06_fact_check_log.md`)만 해당

## 검토 한계

- 로컬 강의 PDF와 과제 PDF는 존재를 확인했으나, 현재 작업환경에서 PDF 텍스트 추출 도구가 없어 페이지 단위 직접 인용은 남기지 못했다.
- 외부 문헌과 최신 동향 주장은 웹 원문 또는 기관 페이지로 대조했다.
- 강의 PDF 기반이라고 표시된 항목은 제출 전 사람이 PDF를 열어 해당 슬라이드/페이지를 한 번 더 대조하는 것이 안전하다.

## 분류 기준

| classification | 의미 |
|---|---|
| A | 강의 PDF 또는 과제 PDF에서 직접 지지 |
| B | 신뢰 가능한 외부 출처로 지지 |
| C | 표준 열역학 식에서 유도 |
| D | 개연성은 있으나 조건·표현상 주의 필요 |
| E | 삭제 또는 재작성 필요 |

## 핵심 주장 검토

| claim | classification | source or reasoning | action needed | final status |
|---|---:|---|---|---|
| 과제는 냉동기 문제와 히트펌프 문제 2개로 구성되며, 9장 냉동기와 11장 히트펌프 강의자료를 기반으로 한다. | A | `outputs/00_assignment_scope.md`의 과제 PDF/강의 PDF 확인 기록. 로컬 파일 `과제/hw2.../Homework-02.pdf`, `10주차_9장_냉동기.pdf`, `12주차_11장_히트펌프.pdf` 존재 확인. | 제출 전 과제 PDF의 배점·문항 페이지 수동 확인 권장. | 유지, 수동 확인 권장 |
| 필수 답안과 추가학습을 분리해야 한다. | A | 과제 범위 문서 및 AGENTS.md 작업 규칙과 일치. | 유지. | 통과 |
| 냉매 종류가 지정되지 않았으므로 특정 냉매명이나 엔탈피 수치를 임의 가정하지 않는다. | A | AGENTS.md 명시 규칙 및 `outputs/00`, `01`, `02`, `03`의 일관된 처리. | 유지. | 통과 |
| 냉매 증발·응축은 화학반응이 아니라 물리적 상변화로 설명해야 한다. | C | 상변화는 물질 조성이 바뀌지 않는 물리 변화이며, AGENTS.md 금지 규칙과 일치. 대상 파일 전체에서 화학반응으로 단정한 표현 없음. | 유지. | 통과 |
| 증기압축 냉동사이클 순서는 `압축 -> 응축 -> 팽창 -> 증발`로 설명한다. | A | `10주차_9장_냉동기.pdf` 기반이라고 `outputs/00`, `01`, `03`에 기록되어 있고 표준 사이클 순서와 일치. | 강의 슬라이드의 번호 표기와 최종 제출 답안 번호가 일치하는지 수동 확인. | 유지, 수동 확인 권장 |
| 상태점 1은 증발기 출구/압축기 흡입, 2는 압축기 출구/응축기 입구, 3은 응축기 출구/팽창밸브 입구, 4는 팽창밸브 출구/증발기 입구이다. | A | 강의 수준의 표준 증기압축 사이클 배치와 일치. | 과제 그림 1-a, 1-b의 번호와 일치하는지 수동 확인. | 유지 |
| `w_comp = h2 - h1`은 냉매 1 kg 기준 압축기 투입 일이다. | C | 정상류 에너지 방정식의 단열 압축기 근사에서 유도. | 부호 convention이 “투입일 양수”임을 유지. | 통과 |
| `q_H = h2 - h3`은 응축기 방열량이다. | C | 응축기에서 냉매가 잃는 엔탈피 차이로 정리. | 외부로 방출되는 열량 기준임을 유지. | 통과 |
| `h3 ≈ h4`는 팽창밸브 교축 과정의 등엔탈피 근사이다. | C | 이상 교축은 축일·열전달이 작아 등엔탈피로 다룬다. `≈` 표기는 실제 손실을 고려한 강의 수준 표현으로 적절. | 이상해석에서는 `h3 = h4`, 실제/교육용 설명에서는 `≈`라고 구분하면 더 명확. | 통과 |
| `q_L = h1 - h4`는 증발기 흡열량이다. | C | 증발기에서 냉매가 얻는 엔탈피 차이로 정리. | 유지. | 통과 |
| `COP_R = (h1 - h4)/(h2 - h1)` | C | 냉동효과/압축기일 정의에서 유도. | 압축기 효율, 압력강하 등 실제 조건은 제외한 기본식임을 유지. | 통과 |
| `COP_HP = (h2 - h3)/(h2 - h1)` | C | 난방효과/압축기일 정의에서 유도. | 난방효과를 응축기 방열량으로 둔 기본식임을 유지. | 통과 |
| 포화 혼합물 엔탈피 `h = (1 - x)h_f + xh_g`, 건도 `x = (h - h_f)/(h_g - h_f)`, `h_fg = h_g - h_f` | C | 포화 혼합영역에서 질량가중 평균과 정의식으로 유도. | 건도는 포화 혼합영역에만 적용한다고 계속 제한. | 통과 |
| P-h 선도에서 x축은 엔탈피, y축은 압력이며 포화액선·포화증기선·습증기·과열증기 영역을 읽는다. | A | `outputs/03`의 강의 근거 기록 및 표준 P-h 선도 해석과 일치. | 강의 그림의 축 표기와 최종 제출 그림 표기가 일치하는지 확인. | 유지 |
| 증발기와 응축기는 강의 수준에서 정압 열교환 과정으로 설명할 수 있다. | A | 냉동기 기본 사이클 강의 수준과 일치. | 실제 압력강하는 생략한 모델임을 유지. | 통과 |
| 포화 혼합영역에서 증발·응축은 등압이면서 포화온도 기준의 등온적 상변화로도 설명할 수 있다. | D | 순수냉매 기본 해석에서는 타당하나, 냉매가 특정되지 않았고 일부 혼합냉매는 temperature glide가 있을 수 있다. | 최종 답안에서는 “강의 수준/순수냉매 기본 해석에서” 또는 “대체로”라는 제한어 유지. | 주의 후 유지 |
| 팽창밸브 후 일부 냉매가 flash vapor가 되어 액체+증기 혼합물로 증발기에 들어간다. | B | 표준 냉동공학 설명과 일치. `outputs/03`은 수치 가정 없이 정성 설명으로 제한. | 유지. | 통과 |
| 압축기 내부 suction valve는 흡입측 저압 증기를 들이고 역류를 막는다. | B | Copeland Refrigeration Manual 및 IIAR Module 4의 왕복동 압축기 설명과 일치. | 과제 답안에서는 왕복동 압축기 기준임을 계속 표시. | 통과 |
| discharge valve는 압축실 압력이 토출측보다 커질 때 열려 고온·고압 증기를 응축기로 보낸다. | B | Copeland/IIAR 왕복동 압축기 설명과 일치. | 유지. | 통과 |
| suction/discharge valve를 외부 서비스 밸브와 구분해야 한다. | B | Copeland manual의 service valve 설명과 논리적으로 일치. | 유지. | 통과 |
| 히트펌프는 열을 생성하기보다 외부 열원에서 열을 옮기고 압축기 일로 온도 수준을 높인다. | B | IEA, The Future of Heat Pumps: https://www.iea.org/reports/the-future-of-heat-pumps/how-a-heat-pump-works | 유지. | 통과 |
| 히트펌프는 전력 투입 없이 재생에너지를 생산하는 장치가 아니다. | B | IEA는 대부분의 열이 “전달”되는 것이며 전력 투입이 필요하다고 설명. EU 지침도 heat pump 구동 입력보다 최종 열출력이 충분히 커야 재생열 산정 가능하다고 조건화. | “공짜 에너지”, “무배출 장치” 표현 금지 유지. | 통과 |
| 일부 시장에서 히트펌프 공급열을 재생에너지로 인정한다. | B | IEA Heat Pumps page 및 EU Renewable Energy Directive 확인. EU 원문: https://eur-lex.europa.eu/eli/dir/2018/2001/oj/eng | 정책 일반화 금지. 국가별 제도 차이를 명시. | 통과 |
| ZEB/넷제로에서 히트펌프는 단독 해결책이 아니라 고효율 HVAC·급탕·PV·축열·제어와 결합되는 설비 요소이다. | B | NIST NZEB review: https://www.nist.gov/publications/residential-net-zero-energy-buildings-review-and-perspective | 유지. | 통과 |
| 건물 전기화는 저탄소 전력, 효율, 저장, 수요 유연성, 냉매 관리가 함께 필요하다. | B | ASHRAE Building Electrification brief: https://www.ashrae.org/file%20library/about/government%20affairs/public%20policy%20resources/briefs/ashrae-building-electrification-ppib-approved-feb-2025.pdf | 유지. | 통과 |
| 건물 배출은 직접배출뿐 아니라 전기·열 공급 간접배출과 내재배출까지 포함해 보아야 한다. | B | IPCC AR6 WGIII Chapter 9: https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-9/ | 유지. | 통과 |
| 2025년 세계 히트펌프 판매는 약 2% 감소했고 유럽은 11% 증가, 미국은 약 13% 감소했다. | B | IEA Global Energy Review 2026, Technology: Heat pumps: https://www.iea.org/reports/global-energy-review-2026/technology-heat-pumps | 날짜를 “2026년 IEA 보고서 기준, 2025년 판매”로 명확히 유지. | 통과 |
| 히트펌프의 온실가스 효과는 COP와 전력 탄소집약도에 의존한다. | B | IEA Heat Pumps, IPCC AR6, Knobloch et al. Nature Sustainability 2020: https://www.nature.com/articles/s41893-020-0488-7 | “모든 지역·모든 시간에 자동 성립”으로 쓰지 않기. | 통과 |
| 히트펌프는 DR, 부하이동, 피크저감 후보 전기부하이다. | B | IEA Demand Response 및 DOE/NREL GEB 자료. IEA DR: https://www.iea.org/energy-system/energy-efficiency-and-demand/demand-response | 실내쾌적·급탕 서비스 제약을 함께 적을 것. | 통과 |
| GEB는 에너지효율, 수요 유연성, 스마트 기술, 통신을 결합해 건물을 유연한 에너지 자원으로 활용하는 접근이다. | B | DOE GEB: https://www.energy.gov/cmei/buildings/grid-interactive-efficient-buildings | 유지. | 통과 |
| GEB 제어는 재실 패턴, 선호, 가격 신호, 기상예보, 현장 발전·저장 정보를 활용할 수 있다. | B | DOE GEB fact sheet: https://www.energy.gov/eere/buildings/articles/grid-interactive-efficient-buildings-fact-sheet | 유지. | 통과 |
| HVAC·급탕 설비는 load shed, load shift, modulation 후보이며 저장식 온수기는 전력 사용 시점과 온수 사용 시점을 분리할 수 있다. | B | NREL GEB Technical Report Series: https://www.nrel.gov/docs/fy20osti/75473.pdf | 유지. | 통과 |
| PCM 통합 히트펌프의 24.6% 냉방, 25.8% 난방 utility saving 수치는 특정 Chicago 사례와 TOU 구조 조건에서 나온 결과이다. | B | ORNL/OSTI Final Report: https://www.osti.gov/biblio/1965265 | 일반 설계값처럼 쓰지 말고 “해당 사례 조건” 제한 유지. | 통과 |
| DR 종료 후 rebound peak와 동시 복귀 위험이 있다. | B | Montrose et al. 2021 및 LBNL review에서 TCL 동기화/제어 과제를 다룸. | “복귀 제어 필요” 문구 유지. | 통과 |
| 스마트그리드 연계는 통신·개인정보·사이버보안 리스크를 동반한다. | B | DOE/FEMP Cybersecurity for GEB: https://www.energy.gov/sites/default/files/2024-10/cybersecurity-considerations-gebs_0.pdf | 유지. | 통과 |
| `outputs/05`의 외부 스마트그리드 주장은 문장 또는 문단에 출처 ID가 붙어 있다. | B | 파일 전체 citation ID 점검 결과 `[S1]`~`[S12]` 중 핵심 주장에 출처 연결 확인. | 긴 요약문은 최종 제출 시 핵심 문장별 출처를 더 촘촘히 달면 좋음. | 통과, 보강 권장 |
| 제상운전과 인버터/부분부하 제어가 강의 PDF에서 확인된다는 `outputs/00`의 문구 | D | 로컬 `12주차_11장_히트펌프.pdf` 텍스트를 자동 추출하지 못해 페이지 단위 재확인 불가. | 제출 전 해당 슬라이드 수동 확인. 확인되지 않으면 “검증 필요”로 낮출 것. | 수동 확인 필요 |

## 출처 진위 점검

| source claim | classification | source or reasoning | action needed | final status |
|---|---:|---|---|---|
| ASHRAE Handbook Chapter 38 Compressors 출처 | B | 공식 ASHRAE handbook URL 확인: https://handbook.ashrae.org/Handbooks/S20/IP/S20_Ch38/S20_ch38_ip.aspx | 접근권한 문제 가능성은 있으나 출처 자체는 실재. | 조작 아님 |
| Copeland Refrigeration Manual 출처 | B | 공식 Copeland 문서 URL 확인: https://www.copeland.com/documents/refrigeration-system-components-en-ca-6653618.pdf | 유지. | 조작 아님 |
| IIAR Series 1 Module 4 Workbook 출처 | B | IIAR 공식 PDF URL 확인. 암모니아 교육자료이므로 일반 냉매로 확대하지 않는다는 제한이 이미 있음. | 제한 문구 유지. | 조작 아님 |
| IEA The Future of Heat Pumps | B | IEA 원문에서 열원 추출, 열 전달, COP 예시, 압축기/냉매 사이클 설명 확인. | 유지. | 조작 아님 |
| IEA Heat Pumps - Energy System | B | IEA 페이지에서 2023년 10% 이상 난방 수요, 재생에너지 인정 시장, 전력망 투자 필요성 확인. | 유지. | 조작 아님 |
| IEA Global Energy Review 2026 Technology: Heat pumps | B | 2025년 판매 동향 수치 확인. | 최신 동향은 기준일을 계속 명시. | 조작 아님 |
| IEA Buildings - Energy System / zero-carbon-ready buildings | B | IEA Buildings page에서 zero-carbon-ready 정의 확인. | 유지. | 조작 아님 |
| IPCC AR6 WGIII Chapter 9 Buildings | B | 직접·간접·내재배출 비중 및 건물부문 배출 관점 확인. | 유지. | 조작 아님 |
| NIST Residential net-zero energy buildings review | B | NIST 공식 publication page와 DOI 확인. | 유지. | 조작 아님 |
| ASHRAE Building Electrification 2025 brief | B | ASHRAE PDF에서 전기화 조건, 저탄소 전력, 효율, 저장, 냉매 관리 확인. | 유지. | 조작 아님 |
| DOE Decarbonizing HVAC and Water Heating in Commercial Buildings | B | OSTI DOI `10.2172/1832100` 확인. | 유지. | 조작 아님 |
| EU Directive 2018/2001 | B | EUR-Lex OJ URL에서 ambient/geothermal energy와 heat pump 산정 조건 확인. | 기존 consolidated URL이 JS 차단될 수 있으므로 OJ ELI URL 병기 권장. | 조작 아님, 링크 보강 권장 |
| Knobloch et al. 2020 Nature Sustainability | B | Nature 페이지에서 59개 지역/53개 지역 분석 문구 확인. | 유료/미리보기 제한이 있으나 초록에서 핵심 주장 확인 가능. | 조작 아님 |
| IEA Demand Response | B | IEA DR page에서 shift/shed, 가격 기반·인센티브 기반 프로그램, aggregation/remote control 확인. | 유지. | 조작 아님 |
| DOE Grid-Interactive Efficient Buildings | B | DOE GEB page에서 효율, demand flexibility, smart technologies, communications 확인. | 유지. | 조작 아님 |
| NREL GEB Technical Report Series 75473 | B | PDF에서 HVAC/급탕/저장식 온수기 load shifting 근거 확인. | 유지. | 조작 아님 |
| LBNL/ASME Providing Grid Services With Heat Pumps | B | LBNL page에서 heat pump demand flexibility, thermal mass, ancillary services 미구현 과제 확인. | 유지. | 조작 아님 |
| Fischer & Madani 2017 review | B | DOI `10.1016/j.rser.2016.11.182` 및 논문 메타데이터 확인. | 유지. | 조작 아님 |
| ORNL heat-pump integrated TES state-of-art | B | ORNL publication page 확인. | 유지. | 조작 아님 |
| ORNL/OSTI 1965265 PCM integrated heat pump report | B | OSTI page에서 Chicago 사례, TOU 제어, 24.6%/25.8% utility saving 확인. | 수치 일반화 금지. | 조작 아님 |
| DOE/FEMP GEB cybersecurity | B | DOE PDF에서 remote control, attack paths, PII leakage, legacy BACnet 위험 확인. | 유지. | 조작 아님 |
| NIST TN 1832 | B | NIST publication page에서 DR conceptual model과 communication interface 확인. | 유지. | 조작 아님 |
| Montrose, Gardner & Satici 2021 Energies | B | Boise State/Energies 메타데이터와 DOI `10.3390/en14134012` 확인. | 유지. | 조작 아님 |
| IEA HPT Annex 42 Heat Pumps in Smart Grids | B | IEA Research Cooperation page에서 load balancing, thermal storage, peak shaving, smart-grid functionality 확인. | 유지. | 조작 아님 |

## unsupported environmental / policy / smart-grid claims

| claim | classification | source or reasoning | action needed | final status |
|---|---:|---|---|---|
| 출처 없는 환경·정책·스마트그리드 단정 | B | `outputs/04`, `outputs/05`에서 환경·정책·스마트그리드 주장은 출처 ID가 붙어 있고, 주요 ID는 원문으로 확인됨. | 별도 E 판정 항목 없음. 긴 문단은 출처를 더 촘촘히 달면 좋음. | 문제 없음 |
| “히트펌프는 친환경/무배출” 같은 무조건적 결론 | D | 실제 문서들은 이를 피하고 COP, 전력 탄소집약도, 냉매 관리, 피크부하 조건을 함께 제시함. | 최종 답안에서도 조건부 표현 유지. | 주의 후 유지 |
| “히트펌프는 재생에너지 생산 장치” 표현 | E | 대상 파일에는 그런 표현이 없음. 해당 표현이 최종 답안에 들어가면 삭제 또는 재작성 필요. | 계속 금지. | 현재 해당 없음 |

## 용어 및 일관성 점검

| claim | classification | source or reasoning | action needed | final status |
|---|---:|---|---|---|
| 냉매, 엔탈피, COP 수치 임의 생성 없음 | C | 대상 파일 검색 결과 특정 냉매명·임의 엔탈피값·임의 COP 계산값 없음. | 유지. | 통과 |
| “추가학습”과 필수 답안 분리 | A | `outputs/00`에서 구조를 명시하고, `04`, `05`는 문헌 검토/추가학습 성격으로 분리됨. | 최종 제출 답안 작성 시 필수 답안 본문에 외부 문헌 검토를 과도하게 넣지 않기. | 통과 |
| lecture-level 명확성 | D | `01`~`03`은 강의 수준의 기본식과 정성 해석으로 적절하나, `03`의 등온 설명은 순수냉매 기본 해석이라는 제한이 필요. | “혼합냉매 temperature glide 제외” 또는 “강의 수준” 제한어 유지. | 주의 후 유지 |
| 외부 문헌 신뢰성 | B | 대부분 국제기구, 정부기관, 표준기관, 학술논문, 국립연구소 자료. 블로그/마케팅 자료 사용 없음. | 유지. | 통과 |

## 종합 판정

- E로 판정해 즉시 삭제해야 할 기존 산출물 문장은 발견하지 못했다.
- D 주의 항목은 2개이다: 강의 PDF 페이지 단위 수동 확인 필요, 그리고 포화 혼합영역의 등온 설명을 순수냉매/강의수준으로 제한할 필요.
- 냉매 증발·응축을 화학반응으로 오해시키는 표현은 발견하지 못했다.
- 외부 환경·정책·스마트그리드 주장은 주요 문헌 원문으로 확인되었고, 출처 조작 정황은 발견하지 못했다.
- 수식은 표준 열역학 식과 부호 convention에 맞는다.
