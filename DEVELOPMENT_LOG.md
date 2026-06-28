# DEVELOPMENT_LOG.md

# Smart Diffuser Development Log

> Last Updated: 2026-06-28

---

# Purpose (목적)

이 문서는 Smart Diffuser 프로젝트의 **개발 일지**입니다.

단순한 변경 이력이 아니라,

* 무엇을 했는지
* 왜 그렇게 했는지
* 어떤 문제가 있었는지
* 어떻게 해결했는지
* 다음에 무엇을 해야 하는지

를 기록합니다.

---

# 2026-06-28

## Project Restart

### Summary

프로젝트 문서를 새롭게 정리하기 시작하였다.

GitHub를 프로젝트의 공식 저장소로 사용하기로 결정하였다.

---

## Completed

* README.md 작성
* AGENTS.md 작성
* PROJECT_STATUS.md 작성
* DECISIONS.md 작성
* HARDWARE.md 작성
* SOFTWARE.md 작성
* PCB_RULES.md 작성
* BOM.md 작성
* TEST_PLAN.md 작성

---

## Current Hardware

MCU

ATtiny1616

Microphone

MAX9814

LED

WS2812

Mist

USB Mist Module

MOSFET

AO3400

Power

USB Type-C

---

## Current Goal

브레드보드에서

모든 기능을 먼저 검증한다.

PCB 설계는 브레드보드 검증이 끝난 후 진행한다.

---

## Important Decisions

ESP32 사용 중단

↓

ATtiny1616 채택

WS2812 채택

USB-C 사용

AO3400 Low-Side Switching

JST-XH 표준화

---

## Problems

현재 없음

---

## Next Tasks

* 브레드보드 제작
* UPDI 테스트
* MAX9814 테스트
* WS2812 테스트
* Mist 테스트

---

## Notes

향후 모든 작업은

이 문서에 날짜별로 계속 추가한다.

---

# Daily Log Template

## YYYY-MM-DD

### Today's Work

*

*

*

### Problems

*

*

### Solution

*

*

### Decisions

*

*

### Next Step

*

*

### Notes

*

*

---

# Prototype History

| Version | Description |
| ------- | ----------- |
| v0.1    | 프로젝트 문서 구축  |
| v0.2    | 브레드보드 테스트   |
| v0.3    | 펌웨어 개발      |
| v0.4    | PCB 설계      |
| v0.5    | PCB 제작      |
| v1.0    | 첫 번째 완성품    |

---

# Lessons Learned

프로젝트를 진행하면서 얻은 경험과 교훈을 기록한다.

예)

* AO3400은 반드시 Low-Side로 사용
* PCB는 브레드보드와 분리하여 설계
* 중요한 결정은 즉시 문서화
* 회로 변경 시 DECISIONS.md와 함께 수정

---

# References

관련 문서

* README.md
* PROJECT_STATUS.md
* DECISIONS.md
* CHANGELOG.md
* TEST_PLAN.md
