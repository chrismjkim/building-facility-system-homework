# 히트펌프와 스마트그리드 연계 검토

## 한국어 요약

히트펌프는 냉난방과 급탕을 전기로 구동하며, 압축기·팬·펌프·보조히터의 운전 시점과 일부 출력 수준을 제어할 수 있기 때문에 수요반응(DR)과 부하이동의 후보 부하가 된다. 다만 제어는 실내 온도, 급탕 온도, 재실자 쾌적 범위 안에서 이루어져야 하며, 건물 외피·내부 마감·가구 등이 가진 열용량과 온수탱크·축열조가 짧은 시간의 완충 역할을 한다. DOE의 GEB(Grid-interactive Efficient Buildings) 관점에서는 효율, 연결성, 센서·제어·분석, 부하 유연성을 결합하여 건물이 전력망 요구와 재실자 요구를 동시에 만족하도록 운전한다. 히트펌프와 열저장을 결합하면 피크 시간에는 전력 사용을 줄이고, 저가 시간대나 재생전력 잉여 시간대에는 미리 냉난방 또는 급탕을 수행하여 열로 저장할 수 있다. 그러나 동시 복귀로 인한 rebound peak, 쾌적성 저하, 제어 복잡도, 통신 인프라·개인정보·사이버보안 문제를 함께 관리해야 한다. [S1][S3][S4][S5][S8][S9][S10]

## 과제에 넣을 수 있는 짧은 문단

히트펌프는 냉난방 에너지를 전기로 공급하는 장치이므로, 전력망 신호나 시간대별 요금에 따라 운전 시점과 출력을 조절할 수 있는 제어 가능한 부하로 볼 수 있다. 건물은 벽체, 바닥, 실내 공기, 가구 등에 열을 일시적으로 저장하므로, 실내쾌적 범위를 벗어나지 않는 한 냉난방 부하를 피크 시간 전후로 이동시킬 수 있다. 온수탱크나 축열조가 있으면 전기가 저렴하거나 재생전력이 많이 생산되는 시간에 열을 저장하고, 피크 시간에는 히트펌프 운전을 줄이는 방식으로 수요반응과 피크저감에 기여할 수 있다. 따라서 히트펌프는 ZEB와 그린빌딩에서 에너지 효율뿐 아니라 스마트그리드 유연성을 제공하는 설비로 해석할 수 있다. [S3][S4][S5][S8]

## 참고문헌 표

| ID | 출처 | 유형 | 이 문서에서 사용한 핵심 근거 | 링크 |
|---|---|---|---|---|
| S1 | IEA, `Demand Response` | 국제기구 추적 자료 | DR은 전력 수요를 이동·감축하여 전력망 균형을 돕는 수단이며, 가격 기반 프로그램과 인센티브 기반 프로그램으로 구분된다. IEA는 분산자원·연결기기·스마트미터·디지털 관리시스템이 소규모 자원의 aggregation과 원격제어를 가능하게 한다고 설명한다. | https://www.iea.org/energy-system/energy-efficiency-and-demand/demand-response |
| S2 | IEA, `Technology: Heat pumps`, Global Energy Review 2026 | 국제기구 최신 시장 자료 | IEA는 2025년 전세계 히트펌프 판매가 약 2% 감소했고, 유럽은 11% 증가, 미국은 약 13% 감소했다고 보고한다. 이는 시장 보급이 지역별 정책·건설 경기·냉매 규제 등의 영향을 받는다는 배경 정보로만 사용한다. | https://www.iea.org/reports/global-energy-review-2026/technology-heat-pumps |
| S3 | DOE, `Grid-Interactive Efficient Buildings` 및 GEB fact sheet | 정부 프로그램 자료 | GEB는 에너지효율, 수요 유연성, 스마트 기술, 통신을 결합하여 건물을 유연한 에너지 자원으로 활용하는 접근이다. GEB fact sheet는 HVAC, PV, EV, 저장장치, 가격 신호, 기상예보, 재실 패턴을 함께 최적화할 수 있다고 설명한다. | https://www.energy.gov/cmei/buildings/grid-interactive-efficient-buildings / https://www.energy.gov/eere/buildings/articles/grid-interactive-efficient-buildings-fact-sheet |
| S4 | DOE/NREL, `GEB Technical Report Series: HVAC; Water Heating; Appliances; and Refrigeration` | 국립연구소 기술보고서 | HVAC와 급탕 설비는 load shed, load shift, modulation의 후보이며, 저장식 온수기는 열저장을 통해 전력 수요와 실제 온수 사용 시점을 분리할 수 있다. 이 보고서는 load shift가 피크 회피, 저가 전력 이용, 재생전력 curtailment 감소와 연결될 수 있다고 설명한다. | https://www.nrel.gov/docs/fy20osti/75473.pdf |
| S5 | Lee et al., `Providing Grid Services With Heat Pumps: A Review`, LBNL/ASME, 2020 | peer-reviewed journal article | 전기식 건물 냉난방 시스템과 히트펌프는 건물 열용량에 열을 저장함으로써 수요 유연성을 제공할 수 있으며, 피크요금·DR 프로그램은 일부 적용되었지만 주파수 조정·부하추종·예비력 같은 보조서비스는 아직 널리 구현되지 않았다고 정리한다. | https://ets.lbl.gov/publications/providing-grid-services-heat-pumps |
| S6 | Fischer & Madani, `On heat pumps in smart grids: A review`, Renewable and Sustainable Energy Reviews, 2017 | peer-reviewed review paper | 히트펌프의 스마트그리드 적용 분야와 제어 접근법을 문헌 기반으로 정리한 리뷰이다. 본 문서에서는 히트펌프-스마트그리드 연계를 문헌검토 주제로 다루는 근거로 사용한다. | https://doi.org/10.1016/j.rser.2016.11.182 |
| S7 | Sultan & Gluesenkamp, `The State of Art of Heat-Pump integrated Thermal Energy Storage for Demand Response`, ORNL, 2021 | 국립연구소/전문지 논문 | 히트펌프 통합 열저장을 GEB의 DR 관점에서 검토하고, 능동·수동 저장 구성의 수요 영향, 에너지 절감, 비용 절감을 문헌 기반으로 분석했다. | https://www.ornl.gov/publication/state-art-heat-pump-integrated-thermal-energy-storage-demand-response |
| S8 | Li et al., `Quantification of Energy Savings and Demand Reduction for a Heat Pump Integrated with Thermal Energy Storage`, ORNL/OSTI, 2023 | 국립연구소 최종보고서 | PCM 열저장 탱크를 비피크 시간에 충전하고 피크 시간에 방전하는 방식으로 부하이동을 분석했다. Chicago 사례 시뮬레이션에서 PCM 통합 히트펌프가 기존 전기 히트펌프보다 load shifting과 utility cost reduction에서 우수했으며, 보고서 조건에서 냉방 24.6%, 난방 25.8%의 utility saving을 제시했다. | https://www.osti.gov/biblio/1965265 |
| S9 | DOE/FEMP, `Cybersecurity Considerations and Research Pathways for Grid-Interactive Efficient Buildings`, 2024 | 정부 사이버보안 자료 | GEB의 스마트 기기, AMI, IoT, HVAC 제어, BAS, 유틸리티 연계는 데이터 교환과 원격제어를 가능하게 하지만, 보안 설계가 부족하면 공격 경로와 운영 중단 위험을 만든다. PII 유출과 레거시 통신 프로토콜 위험도 명시한다. | https://www.energy.gov/sites/default/files/2024-10/cybersecurity-considerations-gebs_0.pdf |
| S10 | NIST TN 1832, `Facility Smart Grid Interface and a Demand Response Conceptual Model`, 2014 | 정부 표준/기술노트 | DR 참여 성과는 시설 시스템의 다양성에 맞는 통신 인터페이스 선택에 부분적으로 의존한다고 설명한다. | https://www.nist.gov/publications/facility-smart-grid-interface-and-demand-response-conceptual-model |
| S11 | Montrose, Gardner & Satici, `Centralized and Decentralized Optimal Control of Variable Speed Heat Pumps`, Energies, 2021 | peer-reviewed journal article | DR 종료 후 다수의 thermostatically controlled loads가 동시에 켜질 경우, 회피하려던 피크보다 큰 즉시 피크와 진동이 발생할 수 있다고 설명한다. 분산·국소 통신 기반 제어는 동기화를 줄이는 접근으로 제시된다. | https://doi.org/10.3390/en14134012 |
| S12 | IEA HPT Annex 42, `Heat Pumps in Smart Grids: Roadmap` | 국제 연구협력/국가 연구사업 자료 | 스마트 히트펌프 시스템의 기술 장벽으로 통신·계량 인프라, 열저장 용량, 수요 유연성 가용성 이해를 제시한다. 외피 품질과 열용량, 사전 경고, 스마트미터, 동적 TOU 요금, 고객 쾌적 보호의 중요성을 설명한다. | https://assets.publishing.service.gov.uk/media/5a7d8988ed915d497af700a2/heat-pumps-smart-grids-roadmap.pdf |

## 메커니즘 표

| 관점 | 작동 메커니즘 | 히트펌프·건물 요소 | 기대 효과 | 적용 조건 및 주의 | 근거 |
|---|---|---|---|---|---|
| 수요반응(DR) | 전력망 또는 요금 신호가 오면 히트펌프 운전을 줄이거나 미루거나, 사전에 예열·예냉한다. | 압축기 운전, 팬, 펌프, thermostat setpoint, 급탕 setpoint | 피크 시간 전력 사용 감소, 비상 상황 부하 감축 | 지나친 setpoint 변경은 쾌적성 저하와 rebound peak를 만들 수 있다. | [S1][S4][S11] |
| 부하이동(load shifting) | 피크 시간 전에는 열을 저장하고, 피크 시간에는 저장된 열 또는 건물 열관성으로 버틴다. | 건물 열용량, 축열조, 온수탱크, PCM 저장 | 피크 회피, TOU 요금 절감, 전력망 혼잡 완화 | 저장 용량, 외기조건, 재실 패턴, 사전 예측 정확도가 중요하다. | [S3][S4][S8][S12] |
| 열저장(TES) | 전기 에너지를 즉시 쓰지 않고 냉열·온열 형태로 저장한다. | 온수탱크, 물/글리콜, 얼음 저장, PCM, 건물 자체 열질량 | 전기 배터리 없이도 단시간 부하 이동 가능 | 저장 손실, 설치 공간, 비용, 제어전략을 함께 검토해야 한다. | [S4][S7][S8][S12] |
| 온수탱크와 급탕 | 저장식 온수기는 물을 미리 데워 저장하고 실제 온수 사용 시점과 전력 사용 시점을 분리한다. | HPWH, 저장식 전기온수기, 혼합밸브, 단열 탱크 | 피크 시간 급탕 전력 감소, TOU 대응 | 탱크 없는 급탕기는 저장 능력이 작아 부하이동 가치가 낮다. HPWH는 전기저항식보다 단위당 전력은 낮아 같은 집합 유연성을 얻으려면 더 많은 대수가 필요할 수 있다. | [S4] |
| 피크저감 | 전력망 피크 또는 배전망 제약 시간에 히트펌프 전력 사용을 낮춘다. | thermostat setback/setup, compressor cycling, 예냉·예열, 열저장 방전 | 발전·송배전 피크 부담 완화, 수요요금 절감 가능 | 모든 건물이 같은 시간에 복귀하면 피크가 다시 커질 수 있으므로 순차 복귀와 분산 제어가 필요하다. | [S1][S4][S11] |
| GEB | 건물의 효율, 연결성, 센서·제어·분석, 유연 부하를 통합 최적화한다. | BAS, 스마트 thermostat, HVAC, PV, 저장장치, 재실·기상·가격 데이터 | 건물 운영비와 전력망 요구를 동시에 고려 | GEB는 단일 장비가 아니라 건물-설비-통신-운영 체계의 통합 문제이다. | [S3][S4][S9] |
| TOU 요금 | 전기요금이 낮은 시간에 히트펌프를 더 운전하고 높은 시간에는 줄인다. | 동적 setpoint, 예측제어, 온수탱크, PCM 저장 | 전기요금 절감, 피크 회피 | TOU 피크가 실제 전력망 피크와 항상 일치하지 않을 수 있으므로 요금 설계가 중요하다. | [S1][S4][S8][S12] |
| 재생전력 통합 | 태양광·풍력 잉여 시간에 부하를 늘려 열로 저장하고, 공급 부족 시간에는 부하를 줄인다. | 예냉·예열, 온수탱크, 축열조, grid signal 기반 제어 | curtailment 감소, 재생전력 흡수, 잔여부하 완화 | 잉여전력 신호, 예측, 저장 가능 열수요가 있어야 한다. | [S1][S4][S8] |
| 예측·그리드 신호 기반 제어 | 기상예보, 가격, DR 이벤트, 재실 패턴, 실내온도 모델을 이용해 앞으로의 운전 계획을 갱신한다. | MPC, 스마트 thermostat, BAS, 센서, 통신 인터페이스 | 쾌적성을 유지하면서 부하 이동 정밀도 향상 | 모델 오차, 통신 장애, 사용자 override, 데이터 품질이 성능을 좌우한다. | [S3][S4][S5][S10] |
| 분산 히트펌프 aggregation | 여러 건물의 히트펌프를 묶어 하나의 가상 유연 자원처럼 제어하거나 시장에 참여시킨다. | aggregator, VPP, 스마트미터, 원격제어, 표준 통신 | 개별 장비의 작은 유연성을 집합하여 의미 있는 피크저감·DR 자원으로 전환 | 동시 제어로 인한 동기화, 통신·개인정보·사이버보안, 보상 배분 문제가 생긴다. | [S1][S5][S8][S9][S11] |

## 핵심 검토 내용

### 1. 히트펌프가 제어 가능한 전기부하인 이유

- 히트펌프는 압축기와 보조기기 전력으로 냉난방 또는 급탕 열을 공급하므로, 운전 시작·정지, setpoint, 일부 장비의 출력 조절을 통해 전력 사용 시점을 조정할 수 있다. [S4][S5]
- HVAC와 급탕은 건물에서 재실자 서비스를 제공하는 부하이지만, 적절한 통신과 제어가 있으면 특정 시간에 전기를 더 쓰거나 덜 쓰도록 관리할 수 있다. [S3][S4]
- IEA는 heat pumps, heating systems, water boilers 같은 고전력 기기에 연결성과 smart functionality를 부여하면 가격 신호와 인센티브에 응답하는 분산자원으로 활용할 수 있다고 제안한다. [S1]

### 2. 건물 열용량과 실내쾌적 범위가 유연성을 제공하는 방식

- 건물 외피, 내부 마감, 가구, 실내 공기는 열을 흡수하거나 방출하므로, 실내온도가 허용 쾌적 범위 안에 머무르는 동안 HVAC 전력 사용을 앞당기거나 늦출 수 있다. [S3][S5]
- 예냉·예열은 피크 시간 전에 실내 또는 구조체에 냉열·온열을 저장하고, 피크 시간에는 히트펌프 운전을 줄이는 방식이다. DOE/NREL GEB 보고서는 이러한 부하이동이 피크 회피, 저가 전력 이용, 재생전력 curtailment 감소와 연결될 수 있다고 정리한다. [S4]
- 외피 성능과 열용량이 클수록 같은 쾌적성 제약 아래에서 히트펌프를 꺼둘 수 있는 시간이 길어질 수 있으나, 이는 건물 유형과 외기조건에 따라 달라져 일반화에는 주의가 필요하다. [S12]

### 3. 온수탱크와 열저장의 부하이동 기여

- 저장식 온수기는 물 자체가 열저장 매체이므로, 전력 사용 시점과 온수 사용 시점을 분리할 수 있다. DOE/NREL은 저장식 온수기가 열저장을 통해 피크 시간 전력 사용을 줄이면서 소비자 기능을 유지할 수 있다고 설명한다. [S4]
- 열저장 방식은 물, 물/글리콜, 얼음, PCM, 건물 열질량 등으로 구현될 수 있으며, 피크 시간 전후의 열수요를 시간적으로 재배치하는 데 쓰인다. [S4][S7]
- ORNL의 PCM 통합 히트펌프 연구는 비피크 시간에 PCM 탱크를 충전하고 피크 시간에 방전하는 제어를 모델링했으며, 해당 Chicago 사례 조건에서 utility cost reduction을 보였다. 이 수치는 특정 모델·지역·TOU 구조에 대한 결과이므로 일반 설계값으로 쓰면 안 된다. [S8]

### 4. 재생전력 잉여 흡수 가능성

- 풍력·태양광 비중이 커질수록 전력망은 시간대별 공급 변동을 더 크게 경험하며, IEA는 DR이 변동성 재생전원 비중이 커지는 전력망에서 중요해진다고 설명한다. [S1]
- GEB의 load shift는 재생전력 출력이 많아 curtailment가 예상되는 시간에 전력 사용을 늘리고, 공급 부족 또는 피크 시간에는 줄이는 방식으로 해석할 수 있다. [S4]
- 히트펌프가 잉여 재생전력을 흡수하려면 열저장 여유, 쾌적성 여유, 가격·탄소·전력망 신호, 장비 통신 인터페이스가 필요하다. [S1][S3][S4][S10]

### 5. 예측·그리드 신호 기반 제어

- DOE GEB 자료는 재실 패턴, 선호, 유틸리티 가격 신호, 기상예보, 현장 발전·저장 정보를 이용해 건물 에너지 사용을 최적화하는 방향을 제시한다. [S3]
- 예측제어는 외기온, 실내 열응답, 가격 또는 DR 이벤트를 미리 반영해 예냉·예열, 저장 충전·방전, 피크 시간 운전 제한을 조합할 수 있다. [S3][S5]
- 실제 적용에서는 baseline 산정, 사용자 override, 통신 지연, 모델 오차, 장비별 제어 권한 차이 때문에 단순한 스케줄보다 구현 난도가 높다. [S5][S10][S12]

### 6. 분산 히트펌프 aggregation

- 개별 주택 또는 소형 건물의 히트펌프 한 대가 제공하는 유연성은 작을 수 있으므로, 여러 장비를 aggregator 또는 VPP가 묶어 제어해야 전력망 관점에서 의미 있는 자원이 된다. [S1][S5]
- ORNL은 열저장의 가치가 건물주에게만 귀속되면 경제성이 낮게 보일 수 있고, 피크 발전 설비 회피 같은 전력망 가치를 실현하려면 큰 보급률과 aggregation이 필요하다고 분석했다. [S8]
- aggregation은 유연성을 키우지만, 동시에 동시 복귀, 통신 실패, 개인정보, 사이버보안, 보상 배분 문제가 생기므로 제어 전략과 제도 설계가 함께 필요하다. [S1][S8][S9][S11]

## Limitations / Risks

| 리스크 | 내용 | 과제 작성 시 표현 |
|---|---|---|
| Rebound peak | DR 종료 후 다수 히트펌프가 동시에 켜지면 전력 수요가 급증할 수 있다. Montrose et al.은 동기화된 thermostatically controlled loads가 DR 이벤트 해제 후 회피하려던 피크보다 큰 즉시 피크를 만들 수 있다고 설명한다. [S11] | "피크저감 효과는 복귀 제어가 없으면 반감될 수 있다." |
| Comfort degradation | setpoint를 과도하게 조정하거나 히트펌프 정지 시간이 길어지면 실내온도와 급탕 서비스가 쾌적 범위를 벗어날 수 있다. IEA HPT Annex 42는 스마트 히트펌프가 외부 신호에 동적으로 반응하되, 수요반응 이벤트가 최종 사용자 쾌적성에 주는 영향을 최소화해야 한다고 설명한다. [S12] | "수요반응은 재실자 쾌적을 전제로 해야 한다." |
| Control complexity | 가격, 날씨, 재실, 열응답, 장비 상태, DR 신호를 동시에 고려해야 하므로 제어 알고리즘과 baseline 산정이 복잡하다. LBNL 리뷰는 히트펌프의 grid service 제공을 위해 모델링, 제어, aggregation 방법과 전력계통 영향 분석이 필요하다고 정리한다. [S5] | "스마트 제어가 없으면 단순 on/off보다 정밀한 유연성 제공이 어렵다." |
| Privacy / communication infrastructure | 스마트미터, 원격제어, BAS, IoT 장치가 필요하며, 이 과정에서 통신 인터페이스 선택, 데이터 접근, 개인정보, 사이버보안이 핵심 이슈가 된다. DOE/FEMP는 GEB의 스마트 기기와 HVAC/BAS 제어가 공격 경로, PII 유출, 레거시 통신 프로토콜 위험을 만들 수 있다고 설명한다. [S9][S10] | "스마트그리드 연계는 설비 기술뿐 아니라 통신·보안 인프라 문제이다." |

## 사실점검 로그

| 항목 | 점검 결과 |
|---|---|
| 냉매 증발·응축 표현 | 화학반응으로 표현하지 않고 물리적 상변화 또는 열 이동 관점으로만 다루었다. |
| 특정 냉매 가정 | 과제 조건에서 냉매가 지정되지 않았으므로 특정 냉매를 가정하지 않았다. |
| 엔탈피 수치 | 엔탈피 수치를 사용하지 않았다. |
| 방정식 | 방정식을 사용하지 않았다. |
| 외부 문헌 주장 | 문장 또는 표 행마다 출처 ID를 붙였다. |
| 수치 사용 | IEA 2026 시장 수치와 ORNL 2023 PCM 통합 히트펌프 시뮬레이션 수치만 사용했으며, 출처·조건을 함께 적었다. |

## 결론

히트펌프는 단순히 고효율 냉난방 설비가 아니라, 건물 열용량·온수탱크·축열조·스마트 제어와 결합될 때 전력망 유연성 자원으로 활용될 수 있다. 과제 수준에서는 "히트펌프는 전기부하이지만 열저장과 쾌적 범위를 활용하면 운전 시간을 이동할 수 있고, 이 특성이 수요반응·피크저감·재생전력 통합에 기여한다"는 논리로 정리하면 충분하다. 추가학습 수준에서는 GEB, TOU 요금, 예측제어, aggregation, cybersecurity를 함께 언급하되, 보편적 성능 수치처럼 단정하지 않는 것이 안전하다. [S3][S4][S5][S8][S9]
