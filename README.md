#  GNSS Basestation - RTKit



## with GNSS Module & Single-Board Computer (SBC)

RTKit is a straightforward, cost-effective project for building your own  **GNSS (Global Navigation Satellite System) base station**  using a single-board computer (SBC) and a high-precision GNSS module.<br>
Powered by **ELT_RTKBase** – supports both modules out-of-the-box. Integrates seamlessly with **onocoy**.
<br>

# 📄 Key Components



| Component                  | Recommendation/Example                                                                 | Image                                                                | Notes                                                                 |
|----------------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------|
| **Raspberry Pi Zero 2W**  | [Official Site](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/) (WH preferred) | <img alt="raspizero2w" src="https://github.com/airtkey/RTKit/blob/main/pictures/rasp.png"> | "H" = pre-soldered headers (for fans).                               |
| **Ethernet/USB Hub**      | Waveshare [ETH/USB Hub HAT](https://www.waveshare.com/product/raspberry-pi/hats/interface-power/eth-usb-hub-hat-b.htm) | <img alt="raspizero2w" src="https://github.com/airtkey/RTKit/blob/main/pictures/eth-usb-hub.png">| HAT: Compact; BOX: For Mosaic-X5 (enclosed GNSS).                    |
| **USB-A to USB-C OTG**    | [AliExpress](https://aliexpress.com/item/1005002301799896.html) (Male-Male)            |  <img alt="otg" src="https://github.com/airtkey/RTKit/blob/main/pictures/otg.png">  | Required for UM980.                                                  |
| **Aluminum Heat Sink**    | [Passive Cooling](https://aliexpress.com/item/1005003796537427.html)       |<img alt="cooling" src="https://github.com/airtkey/RTKit/blob/main/pictures/alu_cooling.png"> | Passive cooling.                                                     |
| **2x Fans (30x30x8mm)**   | [AliExpress 5V/3V](https://aliexpress.com/item/32813594463.html)                      | <img alt="cooling" src="https://github.com/airtkey/RTKit/blob/main/pictures/fan.png">   | Active cooling; connect to GPIO (pinout: [link](https://github.com/airtkey/UM980-diy-/blob/main/pictures/raspberry-pi-zero-pinout.png)). |
| **Power Supply**          | Official [Micro USB 5.1V/2.5A](https://www.raspberrypi.com/products/micro-usb-power-supply) | <img alt="power" src="https://github.com/airtkey/RTKit/blob/main/pictures/power.png"> | Essential for stable operation.                                      |
| **MicroSD Card**          | 8-32GB, Class 10 recommended                                                          | <img alt="sd_card" src="https://github.com/airtkey/RTKit/blob/main/pictures/sd_card.png">| For Raspberry Pi OS.                                                 |
| **Enclosure/Case**        | User's choice → See [Optional Section] |<img alt="case" src="https://github.com/airtkey/RTKit/blob/main/pictures/case.png">|                                     |



## One of these GNSS modules / GNSS Module Variants

| Module          | Connection             | Enclosure Needs                  | Image                                                                 | Notes                                     |
|---------------------|------------------------|----------------------------------|----------------------------------------------------------------------------|--------------------------------------------|
| **UM980**      | USB-A → USB-C OTG Adapter | Separate case (3D/custom)       | <img alt="um980" src="https://github.com/airtkey/RTKit/blob/main/pictures/um980.png">              | Compact board; needs mounting.             |
| **Mosaic-X5**  |  USB-C Cable | Built-in housing; use ETH-USB-HUB-BOX | <img alt="um980" src="https://github.com/airtkey/RTKit/blob/main/pictures/mosaicx5.png"> | Dongle-style |




## To complete your setup, you will need the following components:


| Component          | Recommendation/Example                                                                 | Image/Link                                                                 | Notes                                                                 |
|--------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------|
| **GNSS Antenna**  | Beitian BS-800S                                                                        | [![Antenna](https://github.com/user-attachments/assets/d12811f0-edee-4f7d-b358-3e0ba1650b81)](https://www.aliexpress.us/item/3256808846936564.html) | Multi-band, skyward view.                                            |
| **LM400 Cable**   | SMA to TNC-K                                                                           | [![Cable](https://github.com/user-attachments/assets/951e0954-a507-4edb-8514-e76a244d78f3)](https://www.aliexpress.us/item/3256808997745754.html) | **⚠️ TNC-K required (not standard TNC)** – Different sizes! **Buy antenna + cable bundle** from same supplier for compatibility. |
| **Mounting Bracket** | Pole mount                                                                             | [![Bracket](https://github.com/user-attachments/assets/06ec4d4b-1815-4322-8d41-9627abb804f4)](https://aliexpress.com/item/1005006425749599.html) | For stable outdoor installation.                                     |


# 🚀 Installation Guide

### Prerequisites:

- A computer for initial SD card flashing.
- Internet access for downloads and configuration.



## 🏠 Optional: Custom Enclosures & 3D Printing

Choose any waterproof case for outdoor use. <br>
3D-printable files: [/print_files](https://github.com/airtkey/RTKit/tree/main/print_files).

### Enclosure Options
| Option                | Pros                                      | Image/Link                                                                 |
|-----------------------|-------------------------------------------|----------------------------------------------------------------------------|
| **3D-Printed**       | Custom fit, low-cost                      | <img alt="case" src="https://github.com/airtkey/RTKit/blob/main/pictures/case.png">(https://github.com/airtkey/RTKit/tree/main/print_files)  |
| **Waveshare USB-HUB-BOX** |    |<img alt="hub" src="https://github.com/airtkey/RTKit/blob/main/pictures/hub_box.png"> <br>(https://www.waveshare.com/product/raspberry-pi/hats/interface-power/usb-hub-box.htm) |
| **Off-the-Shelf**    | Quick, rugged (outdoor-ready)             | [Examples](https://www.amazon.com/s?k=waterproof+electronics+case) |

### 3D Print Settings
| Parameter     | Recommendation                  |
|---------------|---------------------------------|
| **Materials** | PETG, ASA, or PLA+     |
| **Orientation** | Flat (bottom down)             |
| **Supports**  | None required                   |
| **Infill**    | 20-40%                          |
| **No Printer?** | [Craftcloud3D](https://craftcloud3d.com) |
<br>
<br>

# 🔨 Assemble the Main Board

**Choose your GNSS variant and cooling method first.** Both UM980 and Mosaic-X5 auto-detect in software (see Setup).

### Cooling Options (Pick One)
| Type                  | Components                          | Steps                                      | Image                                                                 |
|-----------------------|-------------------------------------|--------------------------------------------|------------------------------------------------------------------------|
| **Passive** (Recommended for low-power) | Aluminum Heatsink                  | Peel & stick on Pi CPU. No wiring.         | <img alt="cooling" src="https://github.com/airtkey/RTKit/blob/main/pictures/alu_cooling.png"> |
| **Active** (For hot environments) | 2x 30x30x8mm Fans (5V/3V)          | Mount on lid → Wire to GPIO (Pinout below).| <img alt="cooling" src="https://github.com/airtkey/RTKit/blob/main/pictures/fan_lid.png"> |

**GPIO Fan Pinout** (Active only):  
[![Pinout](https://github.com/airtkey/UM980-diy-/blob/main/pictures/raspberry-pi-zero-pinout.png)](https://github.com/airtkey/UM980-diy-/blob/main/pictures/raspberry-pi-zero-pinout.png)

---

### Variant 1: UM980 GNSS Board (Compact Stack)
1. **Stack ETH-Hub on Pi Zero**: Follow Waveshare manual (snap/align headers).
2. **Attach OTG Adapter**: USB-A to USB-C → Right port on Pi Zero.
3. **Connect UM980**: Plug board into OTG adapter.
4. **Mount in Case**: Place assembly inside (ETH-USB-HUB-BOX or 3D-printed).
5. **Secure**: Screws to fix board.
6. **Antenna**: Route cable through gland → Screw TNC plug.
7. **Cooling**: Apply heatsink or attach/connect fans (as chosen).

<img width="417" height="162" alt="insode" src="https://github.com/user-attachments/assets/d0f15523-a58e-4c8d-8413-0b1c4c0dbbf2" />

---

### Variant 2: Mosaic-X5 GNSS (Dongle w/ USB-C Cable)

1. **Stack ETH-Hub on Pi Zero**: Follow Waveshare manual.
2. **Connect Mosaic-X5**: USB-C cable → ETH-Hub USB port (dongle has housing).
3. **Mount in Case**: ETH-USB-HUB-BOX (Pi+Hub inside); Mosaic external.
4. **Secure**: Screws for board.
5. **Antenna**: Route through case gland → Screw to Mosaic.
6. **Cooling**: Apply heatsink or attach/connect fans.

   <br>
**⚠️ Important Notes**: Mosaic-X5 Setup & Operation
- **Pre-Installation Requirement**
  Connect the **Mosaic-X5** **before** performing a fresh OS installation.
  **Switching from UM980?** → A **full reinstallation** is required (ensure Mosaic is plugged in during setup).

- **Startup/Reboot Behavior**
  After power-up or reboot, the Mosaic-X5 requires **several minutes** to fully initialize.
  **Operational status:** All **three LEDs** must be active.

- **Troubleshooting: No Signals in Dashboard?**
  Verify GNSS reception via the **Mosaic web server**:
  1. Open **Settings** → Scroll to **GNSS Receiver Information** (bottom of the page).
  2. Check signal status.
<img alt="mosaicx5-station" src="https://github.com/airtkey/RTKit/blob/main/pictures/mosaic_stations.png">


---


# Flash the OS
Download and flash **Raspberry Pi OS Lite (64-bit)** in the **Debian Bookworm** version to your microSD card using Raspberry Pi Imager. Enable SSH and Wi-Fi before proceeding. For more detailed information on flashing and setup, please refer to: https://www.raspberrypi.com/documentation/computers/getting-started.html#installing-the-operating-system.

### 2. Connect via SSH
Insert the SD card into your Raspberry Pi and power it up.  
Then connect using an SSH client like **PuTTY**:

### 3. Install the ELT_RTKBase Software

Open a terminal (ssh with putty) on the Pi and run **two** times:
```bash
wget https://github.com/GNSSOEM/ELT_RTKBase/raw/main/install.sh
chmod +x install.sh
./install.sh
```
The script will install the required software and drivers, and start the dashboard (usually accessible at http://raspberrypi.local).

💡 After installation, you can connect it to onocoy directly from the web dashboard.

### Quick Start Guide (w/ Manual Refs)
Manual Link:
(https://github.com/GNSSOEM/ELT_RTKBase/blob/main/Doc/ELT_RTKBase_v1.8.1_EN.pdf)
| Step  | Manual Page |
|------|--------|
| **Access to the dashboard** | Site 18 |
| **Setup for onocoy stream** | Site 47 |


## 🔗 Related Links

- [onocoy Network](https://onocoy.com)
- [ELT_RTKBase](https://github.com/GNSSOEM/ELT_RTKBase)


## 📬 Contact

Questions? Ideas?  
Feel free to:
  
- Reach out via [YouTube](http://www.youtube.com/@airtkey)  
- Message me on **Discord** – you’ll find me in the [**onocoy server**](http://discord.com/invite/CHKxSpPQ8p)   as alex_multimining.
- Or on **X (Twitter)**: [@alex_multimining](https://x.com/AlexMultiMining)

---
