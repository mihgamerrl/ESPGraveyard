# ESPGraveYard 

**ESPGraveYard** is a portable, dual-node cybersecurity and wireless research device running **GhostESP v2.1**. It offloads screen and touch UI processing to a primary display controller while delegating heavy radio, USB injection, and hardware tasks to an **ESP32-S3** expansion node via **GhostLink**.

---

##  Key Features

-  **BadUSB & BadBT (Wireless HID):** Hardware-level DuckyScript keyboard injection via native USB OTG on the ESP32-S3 and Bluetooth Low Energy Swift Pair.
-  **Sub-GHz RF (433 MHz):** Frequency scanning, packet capture, and signal transmission using the **CC1101** module.
-  **2.4 GHz Transceiver:** Wireless scanning, sniffing, and signal auditing using the **NRF24L01+ PA/LNA** module.
-  **NFC / RFID Auditing:** 13.56 MHz card reading, cloning, and tag emulation with the **PN532** module.
-  **GPS Wardriving:** Dual-mode GPS/BDS location logging saved directly to MicroSD in WiGLE-compatible formats.
-  **Hardwired Ethernet:** Network diagnostic capabilities via SPI-attached **W5500** module.
-  **Portable LiPo Power System:** Integrated **TP4056** USB-C charging module with a 3.7V 2000mAh battery and step-up boost converter.

---

>  *All firmware rights and core software credits belong to the original **GhostESP** project.*
