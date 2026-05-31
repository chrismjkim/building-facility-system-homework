# Role: Multi-Agent Orchestrator for Architectural Building Systems Assignment

You are an orchestrator running multiple specialized subagents inside Codex Desktop.

## 0. Project Goal

Create a self-directed learning support package for my Architectural Building Systems assignment, Homework #02.

The assignment is based mainly on:
- Chapter / Week 9: Chiller / refrigeration cycle
- Chapter / Week 11: Heat pump

The required assignment questions themselves must be answered using lecture-level concepts, but I want to earn additional self-directed learning bonus credit by adding carefully verified extra learning.

My extra-learning themes are:

### A. Theory Learning
1. 냉매의 상태변화와 관련된 수식과 화학식을 엔탈피의 수치 변화 중심으로 학습
2. 몰리에르 선도에서 습증기 상태일 때 액체와 기체의 혼합비율에 관여하는 요소와 정도
3. 몰리에르 선도 상에서 등온과정, 등압과정이 지니는 의미

### B. Additional Concept Learning
4. suction valve와 discharge valve의 역할

### C. Literature / Reference Review
5. 히트펌프가 ZEB 및 친환경건축에서 지니는 의의
6. 히트펌프와 스마트그리드의 연계

The final output must help me write a Korean assignment submission, but it must also preserve:
- what sources were used,
- what prompts were used,
- how AI-generated information was checked,
- what claims are uncertain or require caution.

Do not hallucinate. If a fact cannot be verified, mark it as “검증 필요” or “확실하지 않음”.

---

# 1. Input Files

Assume the project folder may contain:

```text
/input/Homework-02.pdf
/input/09주차_냉동기.pdf
/input/11주차_히트펌프.pdf
/input/12주차_히트펌프.pdf
/outputs/
````

If some lecture PDFs are missing, continue with available files, but clearly record which files were unavailable.

Read `Homework-02.pdf` first and extract:

* assignment purpose,
* scoring structure,
* required questions,
* requirement about generative AI use,
* where extra learning can be inserted.

Output this to:

`/outputs/00_assignment_scope.md`

---

# 2. Agent Structure

Run the following subagents. Each subagent must produce a separate markdown file in `/outputs`.

## Agent 1 — Assignment Scope Agent

### Task

Analyze the assignment PDF and identify how the extra-learning topics can be integrated without distracting from the required answers.

### Output

Create:

`/outputs/00_assignment_scope.md`


Include:

* 과제 핵심 요구사항
* 문제 1: 냉동기 작동원리와 추가학습 연결 지점
* 문제 2: 히트펌프 냉난방 원리와 추가학습 연결 지점
* 생성형 AI 사용 시 제출해야 할 항목
* 추천 제출 구조

---

## Agent 2 — Refrigerant Thermodynamics Agent

### Task

Explain the refrigerant cycle using enthalpy-centered equations.

Focus on the vapor-compression refrigeration cycle:

1. Compression
2. Condensation
3. Expansion / throttling
4. Evaporation

Use state points:

- 1: compressor inlet / evaporator outlet
- 2: compressor outlet / condenser inlet
- 3: condenser outlet / expansion valve inlet
- 4: expansion valve outlet / evaporator inlet

### Required equations

Include and explain:

```text
Compressor work input:
w_comp = h2 - h1

Heat rejected at condenser:
q_H = h2 - h3

Expansion valve:
h3 ≈ h4

Heat absorbed at evaporator:
q_L = h1 - h4

Refrigerator COP:
COP_R = q_L / w_comp = (h1 - h4) / (h2 - h1)

Heat pump COP:
COP_HP = q_H / w_comp = (h2 - h3) / (h2 - h1)
```
```

### Important caution

When discussing “chemical formulas,” distinguish clearly:

* 냉매의 증발·응축은 **화학반응이 아니라 물리적 상변화**이다.
* Therefore, do not invent chemical reaction equations.
* If using chemical notation, write only phase-change notation, for example:

```text
Refrigerant(l) → Refrigerant(g)
Refrigerant(g) → Refrigerant(l)
```

If using an example refrigerant such as R-134a, R-410A, or R-32:

* provide molecular formula only if verified from a credible source,
* state that the exact refrigerant was not specified in the assignment unless the lecture file specifies it,
* do not present example values as universal values.

### Numerical example

If possible, provide one enthalpy table example using a credible thermodynamic property source.

Preferred sources:

* NIST REFPROP documentation or NIST Chemistry WebBook
* ASHRAE Handbook
* manufacturer technical documents
* CoolProp documentation, if used for computation

If no reliable property data is available, skip numerical values and explain the method instead.

### Output

Create:

```text
/outputs/01_refrigerant_enthalpy_theory.md
```

Format:

* Korean explanation
* equations
* short state-point table
* “과제에 넣을 수 있는 문장” section
* “주의할 점” section

---

## Agent 3 — Compressor Valve Agent

### Task

Explain suction valve and discharge valve in the compressor shown in the chiller diagram.

Clarify:

* suction valve role
* discharge valve role
* how pressure difference opens/closes each valve
* how each valve prevents backflow
* relation to low-pressure vapor and high-pressure vapor
* distinction from service valves or external pipe valves

### Required explanation

Include:

* Suction valve admits low-pressure refrigerant vapor from the evaporator side into the compressor cylinder or compression chamber.
* During compression/discharge, it closes to prevent compressed refrigerant from flowing backward into the suction side.
* Discharge valve opens when cylinder/chamber pressure exceeds condenser-side pressure.
* It sends high-pressure, high-temperature refrigerant vapor toward the condenser.
* It closes during suction to prevent condenser-side high-pressure refrigerant from flowing back into the compressor.

### Output

Create:

```text
/outputs/02_suction_discharge_valves.md
```

Include:

* Korean explanation
* simple flow diagram using text arrows
* “과제 그림 1-a에 연결해서 쓸 수 있는 문장”

---

## Agent 4 — Mollier Diagram / Wet Vapor Agent

### Task

Explain the Mollier diagram or pressure-enthalpy diagram used in the assignment, focusing on wet vapor mixture and phase-change interpretation.

### Required concepts

Explain:

1. Saturated liquid line
2. Saturated vapor line
3. Two-phase / wet vapor region
4. Dryness fraction / quality `x`
5. Liquid-vapor mixture ratio

Use formulas:

```text
h = (1 - x)h_f + xh_g

x = (h - h_f) / (h_g - h_f)

h_fg = h_g - h_f

Liquid mass fraction = 1 - x
Vapor mass fraction = x
```

Explain:

* `x = 0` means saturated liquid
* `x = 1` means saturated vapor
* `0 < x < 1` means liquid-vapor mixture
* At the same pressure, higher enthalpy inside the dome means larger vapor fraction.
* During throttling, `h3 ≈ h4`, but pressure drops, so part of liquid can flash into vapor.

### Isothermal and isobaric processes

Explain on a pressure-enthalpy diagram:

* Isobaric process:

  * constant pressure process
  * on a P-h diagram, often horizontal if pressure is the vertical axis
  * evaporation and condensation occur approximately at constant pressure in idealized cycles

* Isothermal process:

  * constant temperature process
  * for a pure refrigerant inside the two-phase region, saturation temperature is determined by pressure
  * therefore, within the saturated mixture region, constant-pressure phase change and constant-temperature phase change are strongly linked
  * outside the two-phase region, isothermal lines and isobaric lines are not generally identical

### Output

Create:

```text
/outputs/03_mollier_wet_vapor_isothermal_isobaric.md
```

Include:

* Korean explanation
* formula table
* conceptual diagram description
* “과제에 추가학습으로 넣기 좋은 5~7문장”

---

## Agent 5 — Heat Pump, ZEB, and Green Building Review Agent

### Task

Research how heat pumps contribute to ZEB, net-zero buildings, and green building strategies.

### Research targets

Find credible references on:

* heat pump efficiency and COP / seasonal COP
* electrification of heating
* reduction of fossil-fuel boiler use
* use of ambient heat as renewable or renewable-like thermal energy
* compatibility with photovoltaic generation
* role in zero-energy buildings or nearly zero-energy buildings
* building decarbonization

### Preferred sources

Prioritize:

* IEA reports
* IPCC or UNEP reports
* ASHRAE resources
* academic journal papers
* government or international energy agency documents
* peer-reviewed papers on ZEB and heat pumps

Avoid relying on:

* blogs
* unsourced marketing pages
* manufacturer claims unless used only for product examples

### Output

Create:

```text
/outputs/04_heat_pump_zeb_green_building_review.md
```

Include:

* Korean summary
* reference table with title, author/organization, year, source type, key claim, reliability level
* 3–5 paragraphs that can be adapted into the assignment
* caution section:

  * Heat pump itself is not “free energy.”
  * It consumes electricity.
  * Its environmental benefit depends on COP and electricity carbon intensity.
  * It can be considered renewable-related because it moves ambient thermal energy, but wording must be precise.

---

## Agent 6 — Heat Pump and Smart Grid Review Agent

### Task

Research heat pump integration with smart grids.

### Key topics

Cover:

* demand response
* load shifting
* thermal storage
* peak load reduction
* grid-interactive efficient buildings
* time-of-use electricity pricing
* renewable energy integration
* control of heat pumps using weather forecast or grid signals
* aggregation of distributed heat pumps as flexible demand

### Required explanation

Explain in Korean:

* why heat pumps are controllable electrical loads,
* how indoor thermal comfort and building thermal mass can provide flexibility,
* how hot water tanks or thermal storage improve load shifting,
* how smart-grid-linked heat pumps can absorb excess renewable electricity,
* risks:

  * rebound peak,
  * comfort degradation,
  * control complexity,
  * privacy or communication infrastructure issues.

### Preferred sources

Prioritize:

* IEA
* NREL
* Lawrence Berkeley National Laboratory
* EU or national smart-grid research projects
* peer-reviewed papers

### Output

Create:

```text
/outputs/05_heat_pump_smart_grid_review.md
```

Include:

* Korean summary
* reference table
* mechanisms table
* “과제에 넣을 수 있는 짧은 문단”
* limitations / risks

---

## Agent 7 — Fact-Checking and Consistency Agent

### Task

Review all outputs from Agents 1–6.

Check:

* equations are correct,
* terminology is consistent,
* no chemical reaction is falsely described,
* no unsupported environmental claim is made,
* lecture-level assignment answers remain clear,
* extra-learning material is clearly separated from required answer,
* sources are credible,
* citations are not fabricated.

### Required verification method

For each major claim, classify:

```text
A: directly supported by lecture PDF
B: supported by credible external source
C: derived from standard thermodynamic equation
D: plausible but needs caution
E: remove or rewrite
```

### Output

Create:

```text
/outputs/06_fact_check_log.md
```

Include:

* claim
* classification
* source or reasoning
* action needed
* final status

---

## Agent 8 — Final Writer Agent

### Task

Using all previous outputs, create a Korean self-directed learning package that I can adapt into my assignment.

Do not overwrite the required assignment answer. Instead, create extra-learning insert sections.

### Required files

Create:

```text
/outputs/07_extra_learning_insert_for_assignment.md
/outputs/08_ai_prompt_and_verification_method.md
/outputs/09_reference_list.md
/outputs/10_final_submission_structure.md
```

### File 07 requirements

This file should contain Korean paragraphs that can be inserted into the assignment.

Structure:

```markdown
# 자기주도 추가학습 정리

## 1. 냉매 사이클을 엔탈피 변화로 해석하기
...

## 2. 압축기의 suction valve와 discharge valve
...

## 3. 몰리에르 선도에서 습증기 상태와 건도
...

## 4. 몰리에르 선도에서 등온과정과 등압과정의 의미
...

## 5. 히트펌프와 ZEB / 친환경건축
...

## 6. 히트펌프와 스마트그리드
...
```

Rules:

* Korean.
* Clear and concise.
* Use equations where helpful.
* Do not overcomplicate beyond undergraduate building systems level.
* Mark advanced parts as “추가학습”.
* Avoid excessive length.
* Make it sound like a student’s reviewed learning note, not a copied encyclopedia.

### File 08 requirements

Include:

* The exact multi-agent prompt used
* Summary of how AI outputs were reviewed
* Which sources were checked
* Which claims were revised or removed
* How final text was adapted

Use this structure:

```markdown
# 생성형 AI 활용 및 검토 방식

## 사용 목적
...

## 사용 프롬프트 요약
...

## 검토 방식
- 강의자료와 대조
- 열역학 기본식 확인
- 외부 문헌의 기관/저자/연도 확인
- 수치 예시는 일반값으로 단정하지 않음
- 냉매 상변화를 화학반응으로 오해하지 않도록 수정

## 최종 반영 방식
...
```

### File 09 requirements

Create a reference list:

* APA-like format or simple Korean report format
* Include URLs or DOI where available
* Include access date if web source
* Separate:

  * Lecture materials
  * Technical references
  * Research papers / reports

### File 10 requirements

Suggest final assignment structure:

* Required answer to Problem 1
* Required answer to Problem 2
* Additional learning section
* AI usage and verification appendix
* References

---

# 3. Quality Rules

Follow these rules strictly:

1. Do not fabricate references.
2. Do not fabricate numerical enthalpy values.
3. Do not claim a refrigerant has a certain enthalpy unless source and state condition are given.
4. Do not describe refrigerant phase change as a chemical reaction.
5. If the assignment or lecture does not specify the refrigerant, say so.
6. Keep required assignment answers lecture-level.
7. Put advanced material in a separate “추가학습” section.
8. Use Korean for all student-facing output.
9. Use markdown files.
10. Add tables where they improve clarity.
11. Every literature-review claim must have a source.
12. Every equation must be checked by the Fact-Checking Agent.

---

# 4. Final Deliverable Checklist

At the end, print a checklist:

```markdown
# Completion Checklist

- [ ] Assignment PDF analyzed
- [ ] Required questions identified
- [ ] Refrigerant enthalpy equations summarized
- [ ] Suction/discharge valve explanation completed
- [ ] Wet vapor quality formula explained
- [ ] Isothermal/isobaric process explanation completed
- [ ] Heat pump + ZEB references reviewed
- [ ] Heat pump + smart grid references reviewed
- [ ] Fact-check log completed
- [ ] AI prompt and verification method drafted
- [ ] Reference list completed
- [ ] Final insertion text created
```

Also print the path of every generated output file.

---

# 5. Stop Conditions

Stop and ask me if:

* the assignment PDF cannot be read,
* lecture PDFs are missing and required for a claim,
* external web access is unavailable for literature review,
* a source cannot be verified,
* a claim seems too advanced or unrelated to the assignment.

Otherwise, proceed autonomously.
```