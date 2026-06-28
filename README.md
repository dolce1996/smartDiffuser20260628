# Smart Diffuser 20260628

> Interactive Sound Reactive Smart Diffuser using ATtiny1616

---

# Overview

Smart Diffuser는 소리에 반응하여 조명과 미스트를 제어하는 소형 디퓨저입니다.

ESP32 기반 프로젝트로 시작했지만,
보다 저렴하고 안정적인 독립형 제품을 목표로
ATtiny1616 기반으로 새롭게 설계하고 있습니다.

최종 목표는

- Sound Reactive
- USB-C Powered
- Compact PCB
- Easy Manufacturing
- Low Cost
- Stable Operation

입니다.

---

# Main Features

- MAX9814 Sound Sensor
- WS2812 RGB LED
- Mist Maker Control
- Multiple Animation Modes
- Multiple Sensitivity Levels
- USB-C Power
- Single PCB Design

---

# Hardware

MCU

ATtiny1616

Input

MAX9814

Output

WS2812 RGB LED

Mist Maker

5V USB Mist Module

Power

USB Type-C

Programming

UPDI

---

# Current Status

✅ Hardware design

- MCU 선정 완료
- MAX9814 선정 완료
- WS2812 선정 완료
- USB-C 선정 완료
- MOSFET 선정 완료

⬜ Breadboard Test

⬜ Firmware

⬜ PCB Layout

⬜ Prototype

⬜ Final Product

---

# Folder Structure

```
docs/
    DESIGN.md
    HARDWARE.md
    SOFTWARE.md
    BOM.md

firmware/

easyeda/

3d/

datasheets/
```

---

# Development Philosophy

이 프로젝트는

단순한 DIY가 아니라

"누구나 생산 가능한 완성도 높은 제품"

을 목표로 합니다.

설계는 항상

- 단순성
- 안정성
- 유지보수성
- 저비용
- 생산성

을 우선합니다.

---

# Design Principles

## Hardware

- ATtiny1616 사용
- USB-C 전원
- EasyEDA 설계
- JLCPCB 제작
- LCSC 부품 우선

## Software

- Arduino IDE
- 가독성 우선
- 유지보수 우선
- 모듈화

---

# Planned Functions

Sound Detection

↓

Sound Analysis

↓

Mode Decision

↓

LED Animation

↓

Mist Control

↓

Sleep

---

# Project Goals

- 저전력
- 저비용
- 생산 가능
- 안정성 확보
- 깔끔한 PCB
- 간단한 조립

---

# Future Plans

- Breadboard Verification
- PCB Design
- PCB Manufacturing
- Firmware Optimization
- 3D Printed Case
- Product Assembly
- Long-term Reliability Test

---

# License

Private Project

Copyright © Bek Choi
