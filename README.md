# DIGITAL CLOCK USING COUNTERS AND 7-SEGMENT DISPLAY

## Abstract
This project presents the design and implementation of a hardware-based digital clock using fundamental digital logic ICs. The system utilizes IC 7490 decade counters, IC 7446 BCD-to-7-segment decoder drivers, IC 7408 logic gates, and IC 555 timer to generate accurate timing pulses and display time on common cathode seven-segment displays. The clock successfully operates in MM:SS format with stable timing, clear illumination, and reliable count transitions without the use of any microcontroller.

---

## 1. Introduction
Digital clocks are widely used real-time display systems. Instead of implementing this project using Arduino or microcontrollers, this clock was built completely using basic digital ICs. Through this approach, we gained deeper understanding of counters, BCD decoding, timing generation, frequency division, display driving, and hardware implementation challenges. Working on PCB, soldering, debugging and real wiring helped us understand how digital circuits behave in practical conditions.

---

## 2. Objective
To design and construct a digital clock capable of displaying accurate time using digital logic ICs and seven-segment displays.

---

## 3. Components Used
| Component | Description |
|----------|-------------|
| IC 7490 | Binary Decade Counter |
| IC 7446 | BCD to Seven Segment Decoder Driver |
| IC 7408 | Quad 2-Input AND Gate |
| IC 555 | Clock Pulse Generator (1 Hz) |
| Seven Segment Display | Visual Time Display |
| PCB, Resistors, Capacitors, Wires | Circuit Implementation |
| 9V Battery | Power Source |

---

## 4. Working Principle

### 4.1 IC 555 – Clock Pulse Generator
The IC 555 timer is configured in astable mode to generate a stable 1 Hz clock signal, which acts as the timing base of the system. This pulse is fed into the first 7490 counter so that the time increments once every second.

---

### 4.2 IC 7490 – Decade Counter
IC 7490 is the heart of time counting. It generates BCD outputs and is configured to:
- Count 0–9 for units digit
- Count 0–5 for tens digit
By cascading multiple IC 7490 counters, we achieve:
- Seconds: 00 to 59  
- Minutes: 00 to 59
- Hours: 00 to 23  

Thus, the clock displays HH:MM:SS accurately.

---

### 4.3 IC 7446 – BCD to Seven-Segment Decoder
Outputs of IC 7490 are in BCD form, which cannot be displayed directly. IC 7446 converts BCD values into seven-segment drive signals, enabling clear numeric display on common cathode 7-segment displays. Each digit is connected to a dedicated 7446 decoder.

---

### 4.4 IC 7408 – Logic Control
IC 7408 AND gate is used to generate logic control signals for counter resets and carry propagation. It ensures correct transitions when:
- Seconds move from 59 → 00
- Minutes increment correctly

---

## 5. System Operation
1. IC 555 generates a 1 Hz pulse.
2. Pulse is given to IC 7490 to count seconds.
3. After 59 seconds, reset occurs and minutes increment.
4. Minutes counters repeat the same sequence.
5. IC 7446 converts BCD values to readable digits.
6. Seven-segment display shows HH:MM:SS format continuously.

---

## 6. Display Module
Common cathode seven-segment displays were used. The digits were bright, clear, and stable, making the time easy to read.

---

## 7. Results
- Successfully displayed time in HH:MM:SS format.
- Maintained accurate timing with stable pulse generation.
- Display illumination was consistent.
- Overall hardware operation was reliable.

---

## 8. Challenges Faced
- Solder bridges and cold joints
- Pads lifting from PCB due to overheating
- Managing dense wiring
- Maintaining accurate frequency

### Solutions
- Controlled soldering temperature
- Careful placement and wiring
- Tested connections using multimeter
- Ensured stable component mounting

---

## 9. Conclusion
The project successfully demonstrated the design of a fully hardware-based digital clock using IC 7490, IC 7446, IC 7408, and IC 555. This strengthened our knowledge of digital counters, timing circuits, display interfacing, and hardware debugging. The clock performed reliably, accurately displaying time without any programming or microcontroller.

---


Department of Electronics and Communication Engineering  
Amrita School of Engineering, Bengaluru
