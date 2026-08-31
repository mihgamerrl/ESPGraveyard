#  ESPGraveYard — Development Journal

##  August 10, 2026 — Background & Project Inception
**Time Spent:** 2h  
**Author:** @mihgamerrl  

### Background & Motivation
One day I saw a video on YouTube proving how vulnerable a WPA2 network really is. That rabbit hole got me interested in cybersecurity. Eventually, I saw someone using an ESP32 to audit Wi-Fi security, and I was completely hooked. 

I started searching for the best cybersecurity tools for ESP modules and found **GhostESP**. The best part was that it was compatible with my Cheap Yellow Display (CYD) ESP32! However, I ran into a major hardware limitation: the processor kept crashing because the majority of its processing power went toward driving the 2.8-inch display (and to be honest, it didn't look as cool as I wanted).

### The Goal
I set a goal to build a cool-looking, dedicated hardware device that can harness all the GhostESP tools without crashing.

<img width="3024" height="4032" alt="image" src="https://github.com/user-attachments/assets/1f0af159-cbdf-4a1b-aeb6-0b1e01698785" />



---

##  August 16, 2026 — Component Research & GhostLink
**Time Spent:** 7h  
**Author:** @mihgamerrl  

### Research & Sourcing
Before ordering anything, I checked the GhostESP documentation to see what hardware modules its firmware supports natively. Once I had a complete list, I started searching my local marketplace (EMag) for parts.

I added the following to my cart:
* **Modules:** NFC, Radio (NRF24L01), Sub-GHz (CC1000), Ethernet (W5500), and IR modules.
* **Power & Prototyping:** Battery, wiring, breadboards/prototype boards.
* **Main Controller:** ESP32-S3.

### Why the ESP32-S3?
1. **High Pin Count:** It has enough GPIOs to route multiple communication buses (SPI, I2C, UART).
2. **Dual USB Ports:** It features a native UART port for debugging and a **USB OTG (On-The-Go)** port that can emulate HID devices (mouse, keyboard, storage).

### Display & Inter-Device Communication
To control the ESP32-S3 using my CYD (Cheap Yellow Display) screen without overloading the main processor, I planned to use **GhostLink**—a built-in protocol designed to link and control multiple ESPGhost devices over a wired interface.

<img width="828" height="1407" alt="image" src="https://github.com/user-attachments/assets/b0e039e8-1a21-4953-a996-6d9d0caccedc" />


---

##  August 17, 2026 (8:22 PM) — The Power Delivery Problem
**Time Spent:** 3h  
**Author:** @mihgamerrl  

### The Issue
While mapping out power connections for each module and microcontroller, I hit a major hardware bottleneck:
* To power the **ESP32-S3** from the Cheap Yellow Display (CYD), I need `+5V` and `GND`.
* To power the **CYD** from the main power source, it also requires a `+5V` rail and `GND`.

While I have plenty of shared ground (`GND`) pins, I lacked an easy way to distribute regulated `+5V` power across both devices without causing power dips or brownouts.

### Resolution
After spending hours trying to find an elegant power-sharing workaround on the board, I decided to simplify the power architecture by using a dedicated external portable battery bank to supply clean power across the setup.

<img width="403" height="873" alt="image" src="https://github.com/user-attachments/assets/0008371e-b408-4685-9179-b78cc9a6a7e9" />


---

##  August 17, 2026 (9:15 PM) — Wiring Diagrams & Pin Mapping
**Time Spent:** 5h  
**Author:** @mihgamerrl  

### Drawing the Wiring Schematic
The last step before submitting was making a clear wiring diagram. I thought it would be a quick drawing task, so I opened Draw.io. Once inside, I was flooded with shapes and components and realized I needed to know the exact pinout for every module.

### Researching Pinouts
I asked Gemini for help mapping out the connections, but it kept giving me incomplete/confusing pin information. I had to manually scrape datasheets and Reddit threads to figure out how many pins each module actually needed and what every pin did.

 **Lesson Learned:** Just because a module has 8 physical pins doesn't mean you need to wire all 8! For example, the NRF24L01 2.4GHz module has 8 pins, but only 7 need to be wired up—the `RESET` pin isn't connected because resetting is handled via software in GhostESP.

 <img width="702" height="662" alt="image" src="https://github.com/user-attachments/assets/902f1eb3-a118-427f-b047-7f76559b88f7" />

