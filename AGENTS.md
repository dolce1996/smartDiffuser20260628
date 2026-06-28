# Project Instructions

Always treat `D:\smartDiffuser20260628` as the project root.
Run commands and file operations relative to `D:\smartDiffuser20260628`; if needed, use absolute paths.
# AGENTS.md

# Smart Diffuser AI Project Instructions

This file contains the permanent design rules for this project.

Every AI assistant working on this repository must read this document before making any modification.

---

# Project Overview

Project Name

Smart Diffuser

Goal

Design a compact, low-cost, production-ready sound reactive diffuser.

Current Version

20260628

Repository

smartDiffuser20260628

---

# General Rules

Always prioritize

1. Reliability
2. Simplicity
3. Manufacturability
4. Maintainability
5. Low Cost

Never add unnecessary complexity.

Every hardware or software change must support these principles.

---

# Hardware Platform

MCU

ATtiny1616

Development Environment

Arduino IDE

PCB

EasyEDA

PCB Manufacturer

JLCPCB

Component Supplier

LCSC

---

# Power System

Power Source

USB Type-C

Operating Voltage

5V

USB-C CC pins

CC1 -> 5.1kΩ -> GND

CC2 -> 5.1kΩ -> GND

VBUS pins connected together.

Ground pins connected together.

---

# Power Filtering

USB input should include

470uF Electrolytic Capacitor

10uF Ceramic Capacitor

100nF Ceramic Capacitor

These capacitors should be placed as close as possible to the USB power input.

---

# Programming

Programming Interface

UPDI

Programming MCU

Arduino Uno

Programming Header

GND

UPDI

The programming connector must not become the primary power source.

---

# Audio Input

Module

MAX9814

Output

Analog

The microphone output connects directly to an ADC input of the ATtiny1616.

---

# LED System

LED

WS2812

Only one data pin should control all LEDs.

Avoid using discrete RGB LEDs.

WS2812 is the standard solution for this project.

---

# Mist System

Mist Module

5V USB Mist Maker

Switching Device

AO3400

Always use

Low Side Switching

Never use High Side switching with AO3400.

Gate resistor

100Ω

Gate Pull-down

100kΩ

---

# External Connectors

Preferred Connector

JST-XH

Connector Pitch

2.54mm

3-pin connector standard

Pin1

+5V

Pin2

GND

Pin3

Signal

Every 3-pin connector must follow this rule.

---

# Buttons

Two external push buttons

Button 1

Mode

Button 2

Microphone Sensitivity

No potentiometer.

No rotary encoder.

---

# Software Philosophy

Readable code is more important than short code.

Avoid unnecessary optimization.

Prefer modular functions.

Avoid duplicated code.

Every major function should have comments.

---

# PCB Philosophy

The schematic should always represent the final PCB.

Do not design temporary breadboard circuits inside the schematic.

Breadboard adapters may be used during testing.

Final PCB should only contain production components.

---

# Design Philosophy

This project is intended to become a real product.

Every design decision should consider

Cost

Assembly

Reliability

Serviceability

Future PCB revisions

---

# Documentation

Every important decision must be recorded.

If hardware changes

Update

HARDWARE.md

If firmware changes

Update

SOFTWARE.md

If design philosophy changes

Update

DESIGN.md

If major decisions change

Update

DECISIONS.md

---

# Never Forget

This project is intended to become

A production-quality smart diffuser.

Not just a prototype.

Every modification should move the project closer to mass production.
