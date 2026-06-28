# HARDWARE.md

# Smart Diffuser Hardware Specification

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# Hardware Overview (하드웨어 개요)

Smart Diffuser는 **ATtiny1616 기반의 독립형 사운드 반응 디퓨저**입니다.

주요 기능은 다음과 같습니다.

* Sound Detection (소리 감지)
* LED Animation (조명 효과)
* Mist Control (미스트 제어)
* Push Button Interface (사용자 입력)
* USB-C Power (전원)

---

# System Block Diagram (시스템 구성)

```text
                USB-C 5V
                    │
     ┌──────────────┴──────────────┐
     │                             │
 Power Filter                 Mist Module
     │                             ▲
     ▼                             │
  ATtiny1616 ───── AO3400 MOSFET ──┘
     │
     ├──────── MAX9814
     │
     ├──────── WS2812
     │
     ├──────── MODE Button
     │
     └──────── SENS Button
```

---

# Main Components (주요 부품)

| Module      | Component          |
| ----------- | ------------------ |
| MCU         | ATtiny1616         |
| Audio       | MAX9814            |
| LED         | WS2812             |
| MOSFET      | AO3400             |
| Mist        | USB 5V Mist Module |
| Power       | USB Type-C         |
| Programming | UPDI               |

---

# MCU

## ATtiny1616

선정 이유

* 저렴한 가격
* 충분한 성능
* 소형 PCB
* 저전력
* 생산에 적합

---

# Power System (전원)

## USB Type-C

Input

5V

USB PD는 사용하지 않습니다.

단순 USB Device로 동작합니다.

### CC 연결

CC1 → 5.1kΩ → GND

CC2 → 5.1kΩ → GND

VBUS는 모두 연결합니다.

GND도 모두 연결합니다.

---

# Power Filtering (전원 필터)

USB 입력 직후 다음 부품을 배치합니다.

| Component | Value              |
| --------- | ------------------ |
| C1        | 470uF Electrolytic |
| C2        | 10uF Ceramic       |
| C3        | 100nF Ceramic      |

배치 순서

USB

↓

470uF

↓

10uF

↓

100nF

↓

System

---

# Audio System (오디오 입력)

Module

MAX9814

Output

Analog

Signal

ADC 입력으로 연결

### 특징

* AGC 내장
* 높은 감도
* 회로 단순
* Analog 출력

---

# LED System (조명)

LED

WS2812

### 이유

PWM 채널 절약

배선 단순

애니메이션 구현 쉬움

RGB LED를 개별 제어하는 방식은 사용하지 않습니다.

---

# Mist System (미스트)

Module

USB 5V Mist Module

Control

AO3400

### 반드시 지킬 규칙

AO3400은

**Low-Side Switching**

으로만 사용합니다.

### Gate

100Ω 직렬 저항

### Pull-down

100kΩ

---

# Buttons (버튼)

버튼은 모두 Momentary Push Button입니다.

## Button 1

MODE

기능

OFF

↓

Level1

↓

Level2

↓

Level3

↓

OFF

---

## Button 2

Sensitivity

Level1

↓

Level2

↓

Level3

↓

Level1

---

# Programming (프로그래밍)

Interface

UPDI

개발용

Arduino Uno

최종 PCB에는 UPDI 헤더를 제공합니다.

---

# Connector Standard (커넥터 규칙)

표준 커넥터

JST-XH

Pitch

2.54mm

## 2 Pin

Pin1

+5V 또는 Signal

Pin2

GND

(용도에 따라 정의)

## 3 Pin (프로젝트 표준)

Pin1

+5V

Pin2

GND

Pin3

Signal

모든 3핀 커넥터는 이 규칙을 반드시 따릅니다.

---

# PCB Philosophy (PCB 설계 원칙)

회로도는 항상

최종 제품 기준

으로 작성합니다.

브레드보드용 임시 연결은 회로도에 포함하지 않습니다.

---

# Future Expansion (향후 확장)

향후 추가 가능 기능

* BLE
* Battery
* OLED Display
* Ambient Light Sensor
* Temperature Sensor

현재 버전에서는 포함하지 않습니다.

---

# Related Documents

* DESIGN.md
* SOFTWARE.md
* BOM.md
* PCB_RULES.md
* DECISIONS.md
