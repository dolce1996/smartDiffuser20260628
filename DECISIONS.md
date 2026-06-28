# DECISIONS.md

# Smart Diffuser Design Decisions

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# Purpose

이 문서는 프로젝트에서 내려진 **중요한 설계 결정(Design Decisions)** 을 기록합니다.

목적은 다음과 같습니다.

* 왜 이러한 선택을 했는지 기록
* 같은 실수를 반복하지 않기
* 향후 설계 변경 시 근거 제공
* 새로운 AI나 개발자가 프로젝트를 빠르게 이해할 수 있도록 함

---

# Decision 001

## ESP32 → ATtiny1616

### Decision

ESP32를 사용하지 않고 ATtiny1616을 사용한다.

### Reason

* 프로젝트 규모에 적합
* 소비전력 감소
* PCB 크기 감소
* 부품 가격 절감
* Wi-Fi 기능이 필요하지 않음
* 독립형 제품으로 충분한 성능 제공

### Result

ATtiny1616을 프로젝트의 표준 MCU로 사용한다.

---

# Decision 002

## Audio Sensor

### Decision

MAX9814를 사용한다.

### Reason

* AGC 내장
* Analog 출력
* 회로가 단순
* Arduino에서 사용하기 쉬움

---

# Decision 003

## LED

### Decision

WS2812를 사용한다.

### Reason

* 데이터 핀 1개만 사용
* PWM 채널 절약
* 다양한 애니메이션 구현 가능
* 배선 단순

### Notes

Discrete RGB LED는 사용하지 않는다.

---

# Decision 004

## Power Input

### Decision

USB Type-C 5V를 표준 전원으로 사용한다.

### Reason

* 범용성
* 최신 규격
* 사용 편의성
* 부품 수급 용이

---

# Decision 005

## PCB Design

### Decision

회로도는 항상 최종 PCB 기준으로 작성한다.

### Reason

브레드보드용 임시 회로를 회로도에 남기지 않는다.

---

# Decision 006

## Breadboard Policy

### Decision

브레드보드는 검증용이다.

### Reason

실험을 위한 임시 환경이며 최종 제품 구조와는 분리한다.

---

# Decision 007

## MOSFET

### Decision

AO3400은 반드시 Low-Side Switching으로 사용한다.

### Reason

N-Channel MOSFET은 High-Side 구성에 적합하지 않다.

### History

초기 설계에서는 High-Side를 검토했으나 Low-Side로 변경하였다.

---

# Decision 008

## Programming

### Decision

UPDI를 사용한다.

### Reason

ATtiny1616 공식 프로그래밍 방식이다.

---

# Decision 009

## Connectors

### Decision

JST-XH 2.54mm를 표준 커넥터로 사용한다.

### Standard

3핀 커넥터

Pin1 = +5V

Pin2 = GND

Pin3 = Signal

이 규칙은 모든 3핀 커넥터에 적용한다.

---

# Decision 010

## Buttons

### Decision

외부 Push Button 두 개를 사용한다.

### Button 1

Mode

### Button 2

Microphone Sensitivity

Rotary Encoder와 Potentiometer는 사용하지 않는다.

---

# Decision 011

## Documentation

### Decision

중요한 설계 변경은 반드시 문서화한다.

수정 대상

* CHANGELOG.md
* HARDWARE.md
* SOFTWARE.md
* PROJECT_STATUS.md

---

# Future Decisions

앞으로 중요한 설계 변경이 발생하면 아래 형식으로 계속 추가한다.

---

# Decision XXX

## Title

### Decision

...

### Reason

...

### Result

...

### Notes

...
