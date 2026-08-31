#  ESPGraveYard — Development Journal

##  August 10, 2026 — Background & Project Inception
**Time Spent:** 2h  
**Author:** @mihgamerrl  

### Background & Motivation
 One day I saw a guy on YouTube proving how vulnerable an WPA2 network rely is. Then I started looking more in to cybersecurity. One day one guy used an esp32 to crack an Wi-Fi password, from then on I was hooked. I started searching the best tools for cybersecurity for esp's. And on day I found this on: GhostESP. The best part is that it was compatible whit my Cheep Yellow Display ESP32 , but there was a problem. The processor kept crashing because majority of the processing power went in too the 2.8 inch display screen (and to be honest it realy didn't look cool). So I set my self a goal, I wnated to use all the GhostESP Tools in a Cool looking device.
 
### The Goal
I set a goal to build a cool-looking, dedicated hardware device that can harness all the GhostESP tools without crashing.

<img width="3024" height="4032" alt="image" src="https://github.com/user-attachments/assets/1f0af159-cbdf-4a1b-aeb6-0b1e01698785" />



---

##  August 16, 2026 — Component Research & GhostLink
**Time Spent:** 7h  
**Author:** @mihgamerrl  

### Research & Sourcing
First, before searching anything, I opened the GhostESP site and looked at what their software can handle. After I marked down everything I start looking on my local marketplace, EMag. I added to the cart NFC, Radio, Sub-GHz, Ethernet and IR modules. I also added battery , wires, prototypes boards and the ESP32-S3. But why the S3 you might ask, well the s3 not only that it has a LOT of pins, it also has 2 usb ports. The URAT port ment for board communication AND The OTG (On-The-Go) port that can act like an usb device, meaning, it can act like an mouse ,keyboard or even an storage device. Also you might think, how will I use my CYC Display to control the ESP32-S3, for that I will use the GhostLink. GhostLink is a built in way to control 2 or more ESPGhost devices wired.


### Display & Inter-Device Communication
To control the ESP32-S3 using my CYD (Cheap Yellow Display) screen without overloading the main processor, I planned to use **GhostLink**—a built-in protocol designed to link and control multiple ESPGhost devices over a wired interface.

<img width="828" height="1407" alt="image" src="https://github.com/user-attachments/assets/b0e039e8-1a21-4953-a996-6d9d0caccedc" />


---

##  August 17, 2026 (8:22 PM) — The Power Delivery Problem
**Time Spent:** 3h  
**Author:** @mihgamerrl  

### The Issue
While I was looking at what pins I need to connect for each modul and microcontroller I stumbled upon an BIG problem. For me to power the ESP32-S3 from my CYC I need the +5v and the GND, But to power the CYC I also need the 5v and GND. I have multiple GND ports but not 5v. I tried for hours to find an alternative but I came to a conclusion to just use a portable phone battery.

### Resolution
After spending hours trying to find an elegant power-sharing workaround on the board, I decided to simplify the power architecture by using a dedicated external portable battery bank to supply clean power across the setup.

<img width="403" height="873" alt="image" src="https://github.com/user-attachments/assets/0008371e-b408-4685-9179-b78cc9a6a7e9" />


---

##  August 17, 2026 (9:15 PM) — Wiring Diagrams & Pin Mapping
**Time Spent:** 5h  
**Author:** @mihgamerrl  

### Drawing the Wiring Schematic
What I thought will be a quick draw turn I to a mini 9 to 5. Last thing on the list before submitting was to make a wire diagram, I looked easy so I asked Gemini for an a site to draw, he recomanded Draw.io. I opened the site, there I was prompted whit a LOT of shapes .i mad each component and the it hit me. I have to reasearch how many pins I need for each component. And before you know it I was 2 hours deep in an convo whit Gemini, witch for the love of god, it couldn't give me any info , so I had to manually scrape resit for how many pins I have to use and what each one do. And before you say:"If it has 8 pins that means you have to connect all of them." The 2.4 Ghz modul has 8 pins but I only need 7 of them, the one I don't need is reset pin, but the is done software wise by GhostESP

 <img width="702" height="662" alt="image" src="https://github.com/user-attachments/assets/902f1eb3-a118-427f-b047-7f76559b88f7" />

