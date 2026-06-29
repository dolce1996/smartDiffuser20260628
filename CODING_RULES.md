# CODING_RULES.md

# Smart Diffuser Firmware Coding Rules

> Last Updated: 2026-06-28
>
> Every firmware source file must follow these rules.

---

# 목적 (Purpose)

이 문서는 Smart Diffuser 프로젝트의 코딩 표준을 정의합니다.

목표

* 읽기 쉬운 코드
* 유지보수가 쉬운 코드
* 일관성 있는 코드
* 버그를 줄이는 코드

---

# General Principles

항상 우선순위

1. Readability (가독성)
2. Reliability (안정성)
3. Maintainability (유지보수)
4. Simplicity (단순성)

짧은 코드보다 이해하기 쉬운 코드를 작성합니다.

---

# File Structure

```text
firmware/

main.ino

system.cpp
system.h

audio.cpp
audio.h

led.cpp
led.h

mist.cpp
mist.h

button.cpp
button.h
```

각 모듈은 하나의 역할만 담당합니다.

---

# Function Rules

한 함수는 하나의 기능만 수행합니다.

좋은 예

```cpp
readButtons();

updateLED();

processAudio();
```

좋지 않은 예

```cpp
doEverything();
```

---

# Variable Naming

camelCase 사용

예

```cpp
soundLevel

ledBrightness

currentMode

mistEnabled
```

피해야 하는 이름

```cpp
a

tmp

value1

abc
```

---

# Constants

Magic Number 사용 금지

예

```cpp
const uint8_t MAX_MODE = 3;

const uint16_t AUDIO_THRESHOLD = 180;
```

---

# Pin Definitions

모든 핀은 define 또는 const로 정의합니다.

예

```cpp
#define PIN_LED_DATA PIN_PA1
#define PIN_MIC_ADC PIN_PA2
```

코드 안에 직접 핀 번호를 쓰지 않습니다.

---

# Comments

복잡한 코드는

왜 그렇게 작성했는지

설명합니다.

코드가 무엇을 하는지는 함수 이름으로 표현합니다.

---

# delay()

delay() 사용 최소화

가능하면

millis()

기반으로 작성합니다.

---

# State Machine

프로그램은 State Machine 기반으로 작성합니다.

예

OFF

↓

IDLE

↓

ACTIVE

↓

OFF

Switch-Case를 사용하여 상태를 관리합니다.

---

# LED Rules

LED 제어는

LedController

모듈만 담당합니다.

다른 모듈에서 직접 WS2812를 제어하지 않습니다.

---

# Audio Rules

MAX9814 처리는

AudioAnalyzer

모듈만 담당합니다.

다른 코드에서 ADC를 직접 읽지 않습니다.

---

# Mist Rules

AO3400 제어는

MistController

모듈만 담당합니다.

---

# Button Rules

모든 버튼은

Software Debounce

사용

Internal Pull-up 사용

---

# Error Handling

예외 상황은 반드시 처리합니다.

예

ADC 실패

LED 초기화 실패

센서 값 오류

---

# Future Expansion

향후

Bluetooth

OLED

EEPROM

Battery

기능을 쉽게 추가할 수 있도록 모듈화를 유지합니다.

---

# Never Do

* 전역 변수 남용
* delay() 남용
* 함수 하나에 여러 기능 구현
* 하드코딩된 핀 번호
* 의미 없는 변수명

---

# Coding Philosophy

좋은 코드는

짧은 코드가 아니라

몇 달 후 다시 봐도 바로 이해되는 코드입니다.

---

# Related Documents

* SOFTWARE.md
* PIN_ASSIGNMENT.md
* ARCHITECTURE.md
* AGENTS.md
* DECISIONS.md
