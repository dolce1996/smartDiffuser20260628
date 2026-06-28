# PCB_RULES.md

# Smart Diffuser PCB Design Rules

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# 목적 (Purpose)

이 문서는 Smart Diffuser PCB 설계 시 반드시 따라야 하는 규칙을 정의합니다.

목표

* 실수 방지
* 일관성 유지
* 생산성 향상
* JLCPCB 조립 최적화

---

# PCB Design Philosophy (설계 철학)

회로도는 항상 **최종 제품 기준**으로 작성합니다.

브레드보드용 임시 연결은 PCB 회로도에 포함하지 않습니다.

PCB는 실제 양산 가능한 구조를 목표로 합니다.

---

# Component Rules (부품 규칙)

## SMD 우선

모든 저항

0805

모든 세라믹 콘덴서

0805

가능한 모든 부품은 SMD 사용

---

## Through Hole

허용

* JST-XH
* Push Button
* 필요 시 Electrolytic Capacitor

나머지는 가능한 SMD 사용

---

# USB-C Rules

전원 입력은

USB Type-C

CC1

↓

5.1kΩ

↓

GND

CC2

↓

5.1kΩ

↓

GND

VBUS는 하나의 +5V Net으로 연결

GND는 하나의 GND Plane으로 연결

---

# Power Filtering

USB 입력 바로 옆에

470uF

↓

10uF

↓

100nF

순서로 배치

가능한 USB Connector 가까이 위치

---

# MCU Placement

ATtiny1616은

PCB 중앙 근처

배치

이유

배선 길이 최소화

---

# MAX9814

MCU ADC 가까이 배치

Audio Line 최소화

LED 배선과 가능한 멀리 배치

Noise 최소화

---

# WS2812

Data Line 최대한 짧게

5V와 GND는 충분히 굵게

필요 시 330Ω 직렬 저항 고려

---

# AO3400

반드시

Low Side

Gate

100Ω

Gate Pull-down

100kΩ

Mist Module Connector 가까이 배치

---

# Ground Plane

가능하면 전체 Bottom Layer를

Ground Plane으로 사용

Ground를 잘라놓지 않는다.

---

# Trace Width

Signal

0.25mm 이상

Power

0.5mm 이상

Mist 전원

1.0mm 이상 권장

---

# Connector Rules

## JST-XH

Pitch

2.54mm

### 3 Pin Standard

Pin1

+5V

Pin2

GND

Pin3

Signal

프로젝트 전체에서 동일 규칙 적용

---

# Silk Screen

모든 커넥터에는

기능 표시

예

USB

MIC

LED

UPDI

MIST

MODE

SENS

Pin1 위치 표시

---

# Test Points

가능하면 제공

+5V

GND

UPDI

ADC

WS2812 DATA

---

# Mounting Holes

PCB 고정용

M3 Hole

4개 권장

Copper Keepout 적용

---

# ERC / DRC

PCB 발주 전 반드시 수행

□ ERC

□ DRC

□ Footprint 확인

□ Pin Number 확인

□ GND 확인

□ 5V 확인

---

# Before Ordering Checklist

□ USB-C 확인

□ CC 저항 확인

□ Polyfuse 확인

□ TVS 확인

□ AO3400 방향 확인

□ MAX9814 확인

□ WS2812 확인

□ UPDI 확인

□ Button 확인

□ Connector 확인

□ Pin1 방향 확인

□ Silkscreen 확인

□ Gerber 확인

---

# Never Forget

절대로

브레드보드에서 동작한다고

PCB도 동작한다고 생각하지 않는다.

PCB 제작 전

항상

회로도

↓

ERC

↓

PCB

↓

DRC

↓

Gerber

↓

Review

↓

JLCPCB

순서를 지킨다.

---

# Related Documents

* HARDWARE.md
* BOM.md
* DECISIONS.md
* AGENTS.md
* PROJECT_STATUS.md
