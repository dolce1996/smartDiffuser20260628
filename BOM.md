# BOM.md

# Smart Diffuser Bill Of Materials

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# 목적 (Purpose)

이 문서는 Smart Diffuser 프로젝트에서 사용하는 모든 부품을 관리합니다.

목적

* 구매 관리
* 재고 관리
* PCB 조립
* LCSC 주문
* JLCPCB SMT Assembly

---

# Main Components

| Category | Part            | Status | Notes             |
| -------- | --------------- | :----: | ----------------- |
| MCU      | ATtiny1616      |    ✅   | Main MCU          |
| Audio    | MAX9814         |    ✅   | Analog microphone |
| LED      | WS2812          |    ✅   | Addressable RGB   |
| MOSFET   | AO3400          |    ✅   | Low-side switch   |
| Mist     | USB Mist Module |    ✅   | External Module   |

---

# Power Components

| Component | Value | Package      | Status |
| --------- | ----- | ------------ | :----: |
| C1        | 470uF | Electrolytic |    ✅   |
| C2        | 10uF  | 0805         |    ✅   |
| C3        | 100nF | 0805         |    ✅   |
| R1        | 5.1k  | 0805         |    ✅   |
| R2        | 5.1k  | 0805         |    ✅   |

---

# MOSFET Circuit

| Component     | Value  |
| ------------- | ------ |
| Gate Resistor | 100Ω   |
| Pull-down     | 100kΩ  |
| MOSFET        | AO3400 |

---

# Connectors

| Name  | Type   |     Pins |
| ----- | ------ | -------: |
| USB-C | Type-C | 16/6 Pin |
| UPDI  | JST-XH |        2 |
| LED   | JST-XH |        3 |
| MIC   | JST-XH |        3 |
| MIST  | JST-XH |        2 |
| MODE  | JST-XH |        2 |
| SENS  | JST-XH |        2 |

---

# Passive Components

## Resistors

| Value | Purpose                |
| ----- | ---------------------- |
| 100Ω  | MOSFET Gate            |
| 330Ω  | WS2812 Data (Optional) |
| 4.7kΩ | General Purpose        |
| 5.1kΩ | USB-C CC               |
| 100kΩ | Pull-down              |

---

## Capacitors

| Value | Purpose          |
| ----- | ---------------- |
| 100nF | Bypass           |
| 10uF  | Power Filter     |
| 470uF | USB Input Filter |

---

# Protection Components

| Component          | Status |
| ------------------ | :----: |
| Polyfuse           |   예정   |
| TVS Diode          |   예정   |
| Reverse Protection |   검토   |

---

# Buttons

| Name | Type      |
| ---- | --------- |
| MODE | Momentary |
| SENS | Momentary |

---

# Programming

| Component   | Notes      |
| ----------- | ---------- |
| UPDI Header | JST-XH     |
| Arduino UNO | Programmer |

---

# PCB Components

## Standard Package

| Component         | Package |
| ----------------- | ------- |
| Resistor          | 0805    |
| Ceramic Capacitor | 0805    |
| MCU               | SOIC-20 |
| MOSFET            | SOT-23  |

---

# Purchase Status

## Purchased

* ATtiny1616
* MAX9814
* AO3400
* USB Mist Module
* JST-XH Connectors
* USB-C Connector
* Capacitor Kit
* Resistor Kit

---

## To Purchase

* Polyfuse
* TVS Diode
* PCB
* PCB Assembly Parts

---

# JLCPCB Assembly

SMT Assembly 대상

* MCU
* Resistors
* Capacitors
* MOSFET

수작업 조립

* JST-XH
* Push Buttons
* Electrolytic Capacitor (필요 시)

---

# Future Updates

향후 추가 예정

* LCSC Part Number
* Manufacturer
* Unit Price
* Quantity
* Stock
* Purchase Date

---

# Related Documents

* HARDWARE.md
* PCB_RULES.md
* PROJECT_STATUS.md
* CHANGELOG.md
