# TEST_PLAN.md

# Smart Diffuser Test Plan

> Last Updated: 2026-06-28
> Project Version: Prototype v0.1
> Document Version: 0.1

---

# 목적 (Purpose)

이 문서는 Smart Diffuser의 모든 테스트 절차를 정의합니다.

목표

* 회로 검증
* 기능 검증
* PCB 검증
* 안정성 검증
* 양산 전 최종 확인

---

# Test Sequence (테스트 순서)

절대로 순서를 변경하지 않습니다.

```
Power

↓

MCU

↓

Programming

↓

Buttons

↓

Microphone

↓

LED

↓

Mist

↓

System Integration

↓

Long Run Test
```

---

# STEP 1 - Power Test (전원 테스트)

목적

USB-C 전원이 정상적으로 공급되는지 확인

체크

* [ ] USB-C 연결 확인
* [ ] 5V 출력 확인
* [ ] GND 확인
* [ ] 극성 확인
* [ ] 발열 없음

측정

| Test      | Expected |
| --------- | -------- |
| USB Input | 5V       |
| MCU VCC   | 5V       |

---

# STEP 2 - MCU Test

목적

ATtiny1616 정상 동작

체크

* [ ] 전원 인가
* [ ] RESET 확인
* [ ] Clock 정상

---

# STEP 3 - UPDI Test

목적

프로그램 업로드

체크

* [ ] Arduino UNO 연결
* [ ] UPDI 연결
* [ ] Upload 성공
* [ ] Verify 성공

---

# STEP 4 - Button Test

MODE

* [ ] 버튼 입력
* [ ] Debounce 확인
* [ ] 상태 변경 확인

Sensitivity

* [ ] Level1
* [ ] Level2
* [ ] Level3

---

# STEP 5 - MAX9814 Test

목적

소리 입력 확인

체크

* [ ] ADC 값 변화
* [ ] 박수 감지
* [ ] 음악 감지
* [ ] 노이즈 확인

---

# STEP 6 - WS2812 Test

체크

* [ ] LED ON
* [ ] RED
* [ ] GREEN
* [ ] BLUE
* [ ] WHITE
* [ ] Rainbow
* [ ] Fade
* [ ] Brightness

---

# STEP 7 - Mist Test

체크

* [ ] AO3400 동작
* [ ] Mist ON
* [ ] Mist OFF
* [ ] 과열 없음

---

# STEP 8 - Integration Test

전체 시스템 테스트

* [ ] Button
* [ ] LED
* [ ] Mist
* [ ] Sound Detection

모든 기능이 동시에 동작하는지 확인

---

# STEP 9 - Long Run Test

목적

안정성 확인

시험 시간

* 1시간
* 3시간
* 8시간

체크

* [ ] 재부팅 없음
* [ ] 오동작 없음
* [ ] 발열 없음

---

# Power Consumption

측정 예정

| Mode      | Current |
| --------- | ------: |
| Idle      |         |
| LED       |         |
| Mist      |         |
| Full Load |         |

---

# Test Log

| Date | Tester | Result | Notes |
| ---- | ------ | ------ | ----- |
|      |        |        |       |

---

# Issues Found

문제 발견 시 기록

| ID | Description | Status |
| -- | ----------- | ------ |
|    |             |        |

---

# Verification Checklist

## Hardware

* [ ] USB-C
* [ ] MCU
* [ ] MAX9814
* [ ] AO3400
* [ ] WS2812
* [ ] Buttons
* [ ] Connectors

---

## Firmware

* [ ] Boot
* [ ] ADC
* [ ] Button
* [ ] LED
* [ ] Mist

---

## PCB

* [ ] ERC 완료
* [ ] DRC 완료
* [ ] Gerber 확인
* [ ] 부품 방향 확인

---

# Release Criteria

다음 조건을 모두 만족하면 Prototype v1.0으로 인정합니다.

* 모든 기능 정상 동작
* 연속 8시간 테스트 통과
* PCB 이상 없음
* 발열 문제 없음
* 버튼 정상
* LED 정상
* 미스트 정상

---

# Related Documents

* PROJECT_STATUS.md
* HARDWARE.md
* SOFTWARE.md
* PCB_RULES.md
* CHANGELOG.md
