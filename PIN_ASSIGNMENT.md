# PIN_ASSIGNMENT.md

# Smart Diffuser Pin Assignment

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# Purpose

이 문서는 ATtiny1616의 핀 배정을 관리합니다.

회로도, PCB, 펌웨어는 반드시 이 문서를 기준으로 맞춥니다.

---

# MCU

MCU: ATtiny1616
Package: SOIC-20
Voltage: 5V
Programming: UPDI

---

# Pin Assignment Table

| ATtiny1616 Pin | Port       | Function         | Direction | Notes                   |
| -------------: | ---------- | ---------------- | --------- | ----------------------- |
|              1 | VDD        | +5V              | Power     | USB-C 5V                |
|             20 | GND        | GND              | Power     | Common Ground           |
|             19 | PA0 / UPDI | UPDI             | I/O       | Programming             |
|             18 | PA1        | WS2812 DATA      | Output    | LED data line           |
|             17 | PA2        | MAX9814 OUT      | Input ADC | Microphone analog input |
|             16 | PA3        | MODE Button      | Input     | Use internal pull-up    |
|             15 | PA4        | SENS Button      | Input     | Use internal pull-up    |
|             14 | PA5        | MIST MOSFET Gate | Output    | AO3400 gate via 100Ω    |
|             13 | PA6        | Reserved         | -         | Future use              |
|             12 | PA7        | Reserved         | -         | Future use              |
|              2 | PB0        | Reserved         | -         | Future use              |
|              3 | PB1        | Reserved         | -         | Future use              |
|              4 | PB2        | Reserved         | -         | Future use              |
|              5 | PB3        | Reserved         | -         | Future use              |
|              6 | PC0        | Reserved         | -         | Future use              |
|              7 | PC1        | Reserved         | -         | Future use              |
|              8 | PC2        | Reserved         | -         | Future use              |
|              9 | PC3        | Reserved         | -         | Future use              |
|             10 | PC4        | Reserved         | -         | Future use              |
|             11 | PC5        | Reserved         | -         | Future use              |

---

# Required Connections

## UPDI

PA0 / UPDI

주의:

UPDI는 프로그래밍용으로 사용합니다.

일반 I/O로 사용하지 않습니다.

---

## MAX9814

MAX9814 OUT

↓

ATtiny1616 PA2

ADC 입력으로 사용합니다.

---

## WS2812

ATtiny1616 PA1

↓

330Ω Optional

↓

WS2812 DIN

---

## Mist MOSFET

ATtiny1616 PA5

↓

100Ω

↓

AO3400 Gate

Gate에는 100kΩ Pull-down을 GND로 연결합니다.

AO3400은 반드시 Low-Side Switching입니다.

---

## Buttons

MODE Button

PA3

SENS Button

PA4

두 버튼 모두 internal pull-up을 사용합니다.

버튼은 눌렀을 때 GND로 연결됩니다.

---

# Connector Mapping

## LED Connector

| Pin | Signal      |
| --: | ----------- |
|   1 | +5V         |
|   2 | GND         |
|   3 | WS2812 DATA |

---

## MIC Connector

| Pin | Signal      |
| --: | ----------- |
|   1 | +5V         |
|   2 | GND         |
|   3 | MAX9814 OUT |

---

## UPDI Connector

| Pin | Signal |
| --: | ------ |
|   1 | GND    |
|   2 | UPDI   |

주의:

USB-C 전원을 사용하는 구조에서는 UPDI 커넥터에 +5V를 넣지 않는 것을 우선 고려합니다.

---

## MIST Connector

| Pin | Signal       |
| --: | ------------ |
|   1 | +5V          |
|   2 | MOSFET Drain |

---

## MODE Button Connector

| Pin | Signal |
| --: | ------ |
|   1 | PA3    |
|   2 | GND    |

---

## SENS Button Connector

| Pin | Signal |
| --: | ------ |
|   1 | PA4    |
|   2 | GND    |

---

# Design Notes

* 3핀 커넥터 표준은 Pin1 = +5V, Pin2 = GND, Pin3 = Signal 입니다.
* UPDI는 예외적으로 2핀 GND + UPDI 구성을 우선합니다.
* 버튼은 외부 모멘터리 스위치입니다.
* 가변저항은 사용하지 않습니다.
* WS2812는 데이터 핀 하나만 사용합니다.
* Mist 제어는 AO3400 Low-Side 방식만 사용합니다.

---

# Firmware Pin Names

```cpp
#define PIN_WS2812_DATA   PIN_PA1
#define PIN_MIC_ADC       PIN_PA2
#define PIN_MODE_BUTTON   PIN_PA3
#define PIN_SENS_BUTTON   PIN_PA4
#define PIN_MIST_GATE     PIN_PA5
```

---

# Related Documents

* HARDWARE.md
* SOFTWARE.md
* PCB_RULES.md
* DECISIONS.md
* BOM.md
