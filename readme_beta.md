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



# One of these GNSS modules / GNSS Module Variants

| Module          | Connection             | Enclosure Needs                  | Image                                                                 | Notes                                     |
|---------------------|------------------------|----------------------------------|----------------------------------------------------------------------------|--------------------------------------------|
| **UM980**      | USB-A → USB-C OTG Adapter | Separate case (3D/custom)       | <img alt="um980" src="https://github.com/airtkey/RTKit/blob/main/pictures/um980.png">              | Compact board; needs mounting.             |
| **Mosaic-X5**  |  USB-C Cable | Built-in housing; use ETH-USB-HUB-BOX | <img alt="um980" src="https://github.com/airtkey/RTKit/blob/main/pictures/mosaicx5.png"> | Dongle-style |




# To complete your setup, you will need the following components:


| Component          | Recommendation/Example                                                                 | Image/Link                                                                 | Notes                                                                 |
|--------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------|
| **GNSS Antenna**  | Beitian BS-800S                                                                        | [![Antenna](https://github.com/user-attachments/assets/d12811f0-edee-4f7d-b358-3e0ba1650b81)](https://www.aliexpress.us/item/3256808846936564.html) | Multi-band, skyward view.                                            |
| **LM400 Cable**   | SMA to TNC-K                                                                           | [![Cable](https://github.com/user-attachments/assets/951e0954-a507-4edb-8514-e76a244d78f3)](https://www.aliexpress.us/item/3256808997745754.html) | **⚠️ TNC-K required (not standard TNC)** – Different sizes! **Buy antenna + cable bundle** from same supplier for compatibility. |
| **Mounting Bracket** | Pole mount                                                                             | [![Bracket](https://github.com/user-attachments/assets/06ec4d4b-1815-4322-8d41-9627abb804f4)](https://aliexpress.com/item/1005006425749599.html) | For stable outdoor installation.                                     |


## 🚀 Installation Guide

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


###  Assemble the Main Board
![main_board](https://github.com/user-attachments/assets/bd724068-8737-407b-b39b-44f12837400d)


(The photo shows the 2W version with pins added by the user)

- Assemble the Ethernet Hub and Raspberry Pi Zero: <br>
Carefully connect the Ethernet hub and the Raspberry Pi Zero, referring to their respective manuals for detailed instructions.
- Attach the USB-A to USB-C OTG Adapter:<br> Insert the USB-A to USB-C OTG adapter into the designated port on the right side of the Raspberry Pi Zero.
- Connect the UM980 GNSS Board:<br> Attach the UM980 GNSS board to the USB-C OTG adapter.
- Mount the Assembled Board: <br>Carefully place the fully assembled board into the case.
- Secure the Board:<br> Use the provided screws to fix the board firmly to the case.
- Install the Antenna Plug:<br> Guide the antenna plug through the designated hole in the case and secure it by screwing it into place.
- Attach the Fans:<br> Slide the two fans into their designated slots on the lid of the case.
- Connect the Fans:<br> Connect the fan cables to the appropriate GPIO pins on the Raspberry Pi Zero. ( https://github.com/airtkey/UM980-diy-/blob/main/pictures/raspberry-pi-zero-pinout.png )
<img width="349" height="100" alt="fan_lid" src="https://github.com/user-attachments/assets/a89f288a-bcf6-4063-950f-05d9efbf2443" />
<br>  
<img width="417" height="162" alt="insode" src="https://github.com/user-attachments/assets/d0f15523-a58e-4c8d-8413-0b1c4c0dbbf2" />


### 1. Flash the OS
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



## 🔗 Related Links

- [Onocoy Network](https://onocoy.com)
- [UM980 Base Setup (ELT_RTKBase)](https://github.com/GNSSOEM/ELT_RTKBase)


## 📬 Contact

Questions? Ideas?  
Feel free to:
  
- Reach out via [YouTube](http://www.youtube.com/@airtkey)  
- Message me on **Discord** – you’ll find me in the [**onocoy server**](http://discord.com/invite/CHKxSpPQ8p)   as alex_multimining.
- Or on **X (Twitter)**: [@alex_multimining](https://x.com/AlexMultiMining)

---
