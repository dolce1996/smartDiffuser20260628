# SOFTWARE.md

# Smart Diffuser Firmware Specification

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# Overview (개요)

Smart Diffuser는 **ATtiny1616 기반의 독립형 임베디드 시스템**입니다.

목표는 다음과 같습니다.

* 안정적인 동작
* 유지보수가 쉬운 구조
* 모듈화된 코드
* 저전력
* 확장 가능한 설계

---

# Firmware Architecture (전체 구조)

```text
                Setup()

                   │

                   ▼

              Initialization

                   │

                   ▼

                loop()

                   │

 ┌────────────────────────────────────┐
 │                                    │
 │  Read Buttons                      │
 │  Read Microphone                   │
 │  Process Audio                     │
 │  Update Mode                       │
 │  Update LEDs                        │
 │  Update Mist                       │
 │  Background Tasks                  │
 │                                    │
 └────────────────────────────────────┘
```

---

# Main Modules (주요 모듈)

## System

시스템 초기화

* GPIO
* ADC
* Timer
* LED
* Variables

---

## Audio Module

입력

MAX9814

처리

ADC

기능

* Sound Level
* Peak Detection
* Noise Filter

---

## LED Module

출력

WS2812

기능

* Color
* Brightness
* Animation
* Fade
* Rainbow
* Pulse

LED 관련 코드는 모두 이 모듈에서 관리합니다.

---

## Mist Module

AO3400 MOSFET 제어

기능

* ON
* OFF
* Auto Shutoff

---

## Button Module

Button 1

MODE

Button 2

Sensitivity

모든 버튼은

Software Debounce를 사용합니다.

---

# State Machine (상태 머신)

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

### 설명

OFF

시스템 대기

↓

IDLE

소리 감시

↓

LISTENING

음성 분석

↓

ACTIVE

LED와 미스트 제어

---

# Audio Processing (소리 처리)

순서

ADC Read

↓

Noise Filter

↓

Peak Detection

↓

Sensitivity

↓

Trigger

---

# Sensitivity Levels

Level 1

낮은 감도

Level 2

기본

Level 3

높은 감도

버튼으로 순환합니다.

---

# LED Modes

현재 계획

* Static
* Pulse
* Fade
* Rainbow
* Music Reactive

향후 추가 가능

* Fire
* Water
* Breathing
* Aurora

---

# Mist Modes

Mode 1

Always OFF

Mode 2

Always ON

Mode 3

Sound Reactive

향후

Timer 기능 추가 가능

---

# Timing

delay() 사용을 최소화합니다.

가능한 모든 처리는

millis()

기반으로 작성합니다.

---

# Code Structure

```text
firmware/

main.ino

audio.cpp

audio.h

led.cpp

led.h

mist.cpp

mist.h

button.cpp

button.h

system.cpp

system.h
```

---

# Coding Rules (코딩 규칙)

## 함수

하나의 함수는

하나의 기능만 수행합니다.

---

## 변수

읽기 쉬운 이름 사용

예

good

soundLevel

ledBrightness

modeIndex

bad

a

b

tmp

---

## Magic Numbers

직접 숫자를 쓰지 않습니다.

예

```
const uint8_t MAX_LEVEL = 3;
```

---

## Comments

복잡한 로직은 반드시 설명을 작성합니다.

코드보다

왜 이렇게 작성했는지

설명하는 것을 우선합니다.

---

# Error Handling

예외 상황

* ADC 오류
* LED 초기화 실패
* 버튼 오동작

가능한 안전하게 처리합니다.

---

# Future Features

향후 추가 가능

* EEPROM 저장
* 자동 밝기
* 절전 모드
* BLE 버전
* OLED 지원

현재 버전에서는 구현하지 않습니다.

---

# Related Documents

* HARDWARE.md
* DESIGN.md
* BOM.md
* DECISIONS.md
* CHANGELOG.md

---

# Firmware Philosophy

코드는

"짧은 코드"

보다

"이해하기 쉬운 코드"

를 목표로 합니다.

프로젝트가 커질수록

가독성이 가장 중요합니다.
