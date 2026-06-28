# ARCHITECTURE.md

# Smart Diffuser System Architecture

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# 목적 (Purpose)

이 문서는 Smart Diffuser의 전체 시스템 구조를 설명합니다.

목표

* 시스템 전체 이해
* 모듈 간 관계 설명
* 데이터 흐름 정의
* 향후 기능 확장 기준 제공

---

# System Overview (전체 시스템)

```text
                    USB Type-C
                         │
                    +5V Power
                         │
               ┌─────────┴─────────┐
               │                   │
         Power Filter        Mist Module
               │                   ▲
               ▼                   │
           ATtiny1616 ─── AO3400 ──┘
               │
     ┌─────────┼───────────────┐
     │         │               │
     ▼         ▼               ▼
 MAX9814    WS2812         Buttons
(Audio)      (LED)      Mode / Sens
```

---

# Module Description (모듈 설명)

## MCU

ATtiny1616

역할

* 시스템 제어
* ADC 입력
* LED 제어
* 버튼 처리
* 미스트 제어

---

## Audio Module

MAX9814

입력

소리

출력

Analog Signal

MCU에서 ADC로 읽습니다.

---

## LED Module

WS2812

입력

Data

출력

RGB Animation

LED 애니메이션은 모두 MCU가 제어합니다.

---

## Mist Module

5V USB Mist Module

제어 방식

AO3400 MOSFET

Low-Side Switching

---

## Buttons

MODE

Sensitivity

Momentary Push Button

Software Debounce 적용

---

# Data Flow (데이터 흐름)

## Audio

```text
Sound

↓

MAX9814

↓

ADC

↓

Sound Analysis

↓

State Decision
```

---

## LED

```text
Current Mode

↓

Animation Engine

↓

WS2812 Driver

↓

LED
```

---

## Mist

```text
Current Mode

↓

MOSFET Driver

↓

AO3400

↓

Mist Module
```

---

## Buttons

```text
Button

↓

Debounce

↓

Event

↓

Mode Change
```

---

# Firmware Layers

```text
Application

↓

Control Logic

↓

Drivers

↓

Hardware
```

---

# Software Modules

```text
main

↓

system

↓

audio

↓

button

↓

led

↓

mist
```

각 모듈은 독립적으로 관리합니다.

---

# System States

```text
OFF

↓

IDLE

↓

LISTENING

↓

ACTIVE

↓

IDLE
```

---

# Mode Structure

## MODE

0

OFF

↓

1

Low

↓

2

Medium

↓

3

High

↓

OFF

---

## Sensitivity

Level1

↓

Level2

↓

Level3

↓

Level1

---

# Timing

모든 주기적인 작업은

millis()

기반으로 처리합니다.

delay() 사용은 최소화합니다.

---

# Future Expansion

향후 추가 가능

* Bluetooth
* OLED
* EEPROM 저장
* Ambient Sensor
* Battery Version
* Smartphone App

현재 버전에서는 구현하지 않습니다.

---

# Design Goals

* Low Cost
* Stable
* Easy Assembly
* Easy Maintenance
* Production Ready

---

# Related Documents

* README.md
* HARDWARE.md
* SOFTWARE.md
* PCB_RULES.md
* PROJECT_STATUS.md
* DECISIONS.md
