# PROJECT_STATUS.md

# Smart Diffuser Project Status

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# 프로젝트 개요 (Project Overview)

Smart Diffuser는 **소리에 반응하여 LED와 미스트를 제어하는 독립형 스마트 디퓨저**입니다.

본 프로젝트는 단순한 프로토타입이 아니라 **실제 제품 제작(Production Ready)** 을 목표로 합니다.

---

# 현재 개발 단계 (Current Development Stage)

| Category             | Status | Notes  |
| -------------------- | :----: | ------ |
| Project Planning     |    ✅   | 완료     |
| System Architecture  |    ✅   | 완료     |
| Component Selection  |    ✅   | 대부분 완료 |
| Breadboard Prototype |   🔄   | 진행 예정  |
| Firmware Development |   🔄   | 진행 예정  |
| PCB Design           |    ⏳   | 대기     |
| PCB Manufacturing    |    ⏳   | 대기     |
| Case Design          |    ⏳   | 대기     |
| Final Assembly       |    ⏳   | 대기     |

Legend

* ✅ 완료
* 🔄 진행 중
* ⏳ 예정
* ❌ 미완료

---

# Hardware Status

## MCU

* [x] ATtiny1616 선정

---

## Audio

* [x] MAX9814 선정
* [ ] 실제 테스트

---

## LED

* [x] WS2812 선정
* [ ] 애니메이션 테스트

---

## Mist Module

* [x] USB 5V Mist Module 선정
* [ ] 실제 제어 테스트

---

## MOSFET

* [x] AO3400 선정
* [x] Low-Side Switching 확정

---

## USB-C

* [x] USB-C 입력 채택
* [x] CC 저항 적용
* [ ] 실제 전원 테스트

---

# Firmware Status

## Core

* [ ] System Initialization
* [ ] State Machine
* [ ] Configuration

---

## Audio Processing

* [ ] ADC Read
* [ ] Sound Level Detection
* [ ] AGC Verification

---

## LED Control

* [ ] Basic Control
* [ ] Sound Reactive Mode
* [ ] Animation Library

---

## Mist Control

* [ ] MOSFET Driver
* [ ] Auto Shutdown
* [ ] Safety Logic

---

## Buttons

### MODE Button

* [ ] OFF
* [ ] Level 1
* [ ] Level 2
* [ ] Level 3

### Sensitivity Button

* [ ] Level 1
* [ ] Level 2
* [ ] Level 3

---

# PCB Status

* [ ] Final Schematic
* [ ] ERC Check
* [ ] PCB Placement
* [ ] Routing
* [ ] DRC Check
* [ ] Gerber Export
* [ ] JLCPCB Order

---

# Mechanical Status

* [ ] Enclosure Design
* [ ] 3D Printing
* [ ] Assembly
* [ ] Final Appearance

---

# Testing Status

## Breadboard

* [ ] Power
* [ ] MAX9814
* [ ] WS2812
* [ ] Mist Module
* [ ] Buttons

---

## PCB

* [ ] First Prototype
* [ ] Power Test
* [ ] Functional Test
* [ ] Reliability Test

---

# Current Hardware

| Item         | Selected           |
| ------------ | ------------------ |
| MCU          | ATtiny1616         |
| Audio        | MAX9814            |
| LED          | WS2812             |
| MOSFET       | AO3400             |
| Mist         | USB 5V Mist Module |
| Power        | USB Type-C         |
| Programming  | UPDI               |
| PCB          | EasyEDA            |
| Manufacturer | JLCPCB             |
| Components   | LCSC               |

---

# Current Priority

현재 가장 중요한 작업 순서입니다.

1. Breadboard 회로 완성
2. Firmware 기본 구조 작성
3. MAX9814 테스트
4. WS2812 테스트
5. Mist 제어 테스트
6. 전체 시스템 통합
7. PCB 설계
8. PCB 제작
9. 케이스 제작
10. 최종 테스트

---

# Notes

프로젝트 진행 중 중요한 변경 사항은 반드시 아래 문서를 함께 수정합니다.

* CHANGELOG.md
* DECISIONS.md
* HARDWARE.md
* SOFTWARE.md

프로젝트의 현재 상태는 항상 이 문서를 기준으로 관리합니다.
