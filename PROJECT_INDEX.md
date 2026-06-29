# PROJECT_INDEX.md

# Smart Diffuser Project Index

> This is the entry point for the Smart Diffuser project.
>
> 모든 AI와 개발자는 이 문서를 먼저 읽고 프로젝트를 시작합니다.

---

# 프로젝트 소개 (Project Overview)

Smart Diffuser는 **소리에 반응하여 LED와 미스트를 제어하는 독립형 스마트 디퓨저**입니다.

이 프로젝트의 목표는 단순한 DIY가 아니라 **실제 생산 가능한 제품(Production Ready Product)** 을 만드는 것입니다.

현재 MCU는 **ATtiny1616**을 사용하며, USB-C 전원, MAX9814 마이크, WS2812 LED, AO3400 MOSFET 기반으로 설계하고 있습니다.

---

# 현재 개발 단계 (Current Phase)

현재 단계

✅ 프로젝트 문서 구축 완료

🔄 브레드보드 제작 준비

다음 목표

* 브레드보드 제작
* 펌웨어 작성
* 회로 검증
* PCB 설계

---

# 프로젝트 진행 순서

```
Documentation

↓

Breadboard

↓

Firmware

↓

Hardware Verification

↓

PCB Design

↓

PCB Manufacturing

↓

Prototype

↓

Product Version 1.0
```

---

# 가장 먼저 읽을 문서

프로젝트를 시작하기 전에 아래 문서를 순서대로 읽습니다.

1.

AGENTS.md

↓

프로젝트 규칙

2.

PROJECT_STATUS.md

↓

현재 어디까지 진행되었는지

3.

DEVELOPMENT_LOG.md

↓

최근 작업 내용

4.

DECISIONS.md

↓

왜 이런 설계를 했는지

---

# 기술 문서

시스템 구조

ARCHITECTURE.md

하드웨어

HARDWARE.md

소프트웨어

SOFTWARE.md

PCB

PCB_RULES.md

부품

BOM.md

테스트

TEST_PLAN.md

---

# 현재 하드웨어

MCU

ATtiny1616

Audio

MAX9814

LED

WS2812

Mist

USB 5V Mist Module

MOSFET

AO3400

Power

USB Type-C

Programming

UPDI

---

# 현재 해야 할 일

Priority 1

브레드보드 제작

Priority 2

ATtiny1616 테스트

Priority 3

MAX9814 테스트

Priority 4

WS2812 테스트

Priority 5

Mist 테스트

Priority 6

PCB 설계

---

# 설계 원칙

항상

* 단순하게
* 안정적으로
* 생산 가능하게
* 유지보수가 쉽게

설계합니다.

---

# 중요한 설계 결정

* ESP32 사용 중단
* ATtiny1616 채택
* MAX9814 사용
* WS2812 사용
* USB-C 사용
* AO3400 Low-Side Switching
* JST-XH 표준화

자세한 내용은

DECISIONS.md

참고

---

# 프로젝트 규칙

회로 변경

↓

HARDWARE.md 수정

코드 변경

↓

SOFTWARE.md 수정

설계 변경

↓

DECISIONS.md 수정

작업 완료

↓

DEVELOPMENT_LOG.md 작성

프로젝트 상태 변경

↓

PROJECT_STATUS.md 수정

---

# 문서 구조

```
README.md

AGENTS.md

PROJECT_INDEX.md

↓

docs/

↓

firmware/

↓

easyeda/

↓

datasheets/

↓

3d/
```

---

# AI Startup Checklist

프로젝트를 시작할 때 반드시 아래 순서를 따릅니다.

□ README 확인

□ AGENTS 확인

□ PROJECT_STATUS 확인

□ DEVELOPMENT_LOG 최근 내용 확인

□ DECISIONS 확인

□ 현재 작업 목표 확인

이후 작업을 시작합니다.

---

# Current Goal

현재 목표는

브레드보드에서

모든 기능을 검증하는 것입니다.

PCB 설계는

브레드보드 검증 완료 후 시작합니다.

---

# Long-term Vision

Smart Diffuser는 앞으로

* Version 1
* Version 2
* Version 3

까지 계속 발전시키는 것을 목표로 합니다.

GitHub 저장소는 프로젝트의 공식 기록으로 사용합니다.
