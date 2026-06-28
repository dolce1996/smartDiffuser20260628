# ROADMAP.md

# Smart Diffuser Development Roadmap

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# Project Vision (프로젝트 비전)

Smart Diffuser는 단순한 DIY 프로젝트가 아니라 **실제 판매 가능한 완성도 높은 제품**을 목표로 합니다.

최종 목표는 다음과 같습니다.

* 안정적인 동작
* 생산 가능한 PCB
* 깔끔한 외형
* 유지보수가 쉬운 구조
* 저렴한 생산 단가

---

# Development Phases

## Phase 1 - Documentation

**Status:** ✅ Completed

### Goals

* 프로젝트 구조 정의
* 문서 작성
* 개발 규칙 확립

### Deliverables

* README
* AGENTS
* HARDWARE
* SOFTWARE
* BOM
* TEST_PLAN
* DECISIONS

---

## Phase 2 - Breadboard Prototype

**Status:** 🔄 In Progress

### Goals

브레드보드에서 모든 기능 검증

### Tasks

* [ ] USB-C 전원 확인
* [ ] UPDI 업로드
* [ ] ATtiny1616 테스트
* [ ] MAX9814 테스트
* [ ] WS2812 테스트
* [ ] AO3400 테스트
* [ ] Mist Module 테스트
* [ ] 버튼 테스트

### Exit Criteria

모든 기능이 정상 동작

---

## Phase 3 - Firmware Development

**Status:** ⏳ Planned

### Goals

기본 펌웨어 완성

### Features

* Audio Detection
* LED Animation
* Mist Control
* Button Control
* State Machine

---

## Phase 4 - PCB Design

**Status:** ⏳ Planned

### Goals

EasyEDA에서 PCB 설계

### Tasks

* Final Schematic
* ERC
* PCB Placement
* Routing
* DRC
* Gerber

---

## Phase 5 - PCB Manufacturing

**Status:** ⏳ Planned

### Goals

JLCPCB 제작

### Tasks

* PCB 주문
* SMT 조립
* 부품 납땜
* 전원 테스트

---

## Phase 6 - Prototype Verification

**Status:** ⏳ Planned

### Goals

첫 번째 시제품 검증

### Tests

* 기능 테스트
* 발열 테스트
* 장시간 테스트
* 소비전력 측정

---

## Phase 7 - Enclosure

**Status:** ⏳ Planned

### Goals

제품 케이스 제작

### Tasks

* Blender 모델링
* 3D Printing
* 조립성 확인

---

## Phase 8 - Version 1.0

**Status:** ⏳ Planned

### 목표

첫 번째 완성품

### 완료 조건

* PCB 안정화
* Firmware 안정화
* 케이스 완성
* 최종 테스트 완료

---

# Future Roadmap

## Version 2.0

후보 기능

* BLE 지원
* OLED Display
* EEPROM 설정 저장
* 자동 밝기
* 절전 모드

---

## Version 3.0

후보 기능

* Smartphone App
* OTA Update
* Battery Version
* USB PD 지원

---

# Milestones

| Milestone     | Target |
| ------------- | ------ |
| Documentation | ✅      |
| Breadboard    | 🔄     |
| Firmware      | ⏳      |
| PCB           | ⏳      |
| Prototype     | ⏳      |
| Product v1.0  | ⏳      |

---

# Success Criteria

프로젝트 성공 기준

* 모든 기능 정상 동작
* 8시간 이상 연속 운전
* PCB 문제 없음
* USB-C 안정성 확보
* LED 및 미스트 정상 제어
* 생산 가능한 BOM 확보

---

# Long-term Vision

Smart Diffuser는 앞으로 다음과 같은 방향으로 발전합니다.

* 안정적인 하드웨어 플랫폼 구축
* 유지보수가 쉬운 펌웨어 구조
* 문서 중심 개발
* GitHub 기반 프로젝트 관리
* 향후 후속 모델(v2, v3) 개발 기반 마련

---

# Related Documents

* PROJECT_STATUS.md
* DEVELOPMENT_LOG.md
* TEST_PLAN.md
* DECISIONS.md
* CHANGELOG.md
