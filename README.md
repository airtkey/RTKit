#  GNSS Basestation - RTKit
<img width="510" height="183" alt="miner_ohneBG" src="https://github.com/user-attachments/assets/7aa2d497-d174-43aa-8f2b-47c93be2a783" />


## with UM980 GNSS Module & Raspberry Pi Zero 2WH

RTKit is a simple, affordable project for building your own GNSS (Global Navigation Satellite System) basestation using a Raspberry Pi Zero and UM980 board. It's ideal for RTK (Real-Time Kinematic) applications like precision surveying or navigation. This guide focuses on hardware assembly; software setup (e.g., using RTKLIB) is left to the user.

<br>

# 📄 Key Components


- Raspberry Pi Zero 2 WH – where the "H" officially stands for "pre-soldered headers"  
https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/
<img width="250" height="174" alt="RASP_PI_ZERO2_WH" src="https://github.com/user-attachments/assets/80a5c816-0b8b-43cc-b90f-1bcd15385148" />

- Ethernet / USB HUB HAT <br>
https://www.waveshare.com/product/raspberry-pi/hats/interface-power/eth-usb-hub-hat-b.htm?___SID=U  
<img width="250" height="172" alt="eth_hat" src="https://github.com/user-attachments/assets/4e4fce9b-29e2-4b4d-b333-94443c3f791a" />

- UM980 GNSS Module<br>
Example: https://witmotion-sensor.com ; https://www.gns-electronics.de/ ; https://aliexpress.com/ 
<img width="184" height="250" alt="um980" src="https://github.com/user-attachments/assets/c81fc6bb-e565-4fdf-b510-cbfd57153f90" />

- USB-A (Male) to USB-C (Male) OTG<br>
Example: https://aliexpress.com/item/1005002301799896.html
<img width="229" height="250" alt="usb otg" src="https://github.com/user-attachments/assets/11d13eb0-989e-42bb-b893-fa8c28c4eb26" />


- 2x Fan 30x30x08 5V/3V<br>
Example: https://aliexpress.com/item/32813594463.html
<img width="250" height="251" alt="fan" src="https://github.com/user-attachments/assets/6ebe6f5f-afcc-4d9b-934c-0be6bb307f4d" />

- Raspberry Pi Micro USB Power Supply <br>
https://www.raspberrypi.com/products/micro-usb-power-supply
<img width="250" height="250" alt="microusb-51v-25a-netzteil-fur-raspberry-pi-3b-3a-3b-2b-zero-zero-2-original-weiss" src="https://github.com/user-attachments/assets/1b6409c5-2805-414e-88f5-0d3cbac5ee8e" />

- MicroSD card (at least 8GB,max 32GB, Class 10 recommended)
<img width="250" height="187" alt="sd_card" src="https://github.com/user-attachments/assets/3d729816-15c2-4d2f-ae81-a434106245fd" />
<br>

- Enclosure/Case (user's choice—see optional section below)

# To complete your setup, you will need the following components:

- GNSS Antenna  Recommend: Beitian BS-800S<br>
Example: https://www.aliexpress.us/item/3256808846936564.html
<img width="450" height="200" alt="antenna" src="https://github.com/user-attachments/assets/d12811f0-edee-4f7d-b358-3e0ba1650b81" />

- LM400 cable SMA - TNC<br>
Example: https://www.aliexpress.us/item/3256808997745754.html <br>
Connector Compatibility Note: <br>
The antenna requires a TNC-K connector — not a standard TNC.
Why this matters:
Standard TNC and TNC-K have different sizes.
Recommended Practice:
To guarantee compatibility, buy the antenna and cable as a bundle from the same supplier.
<img width="250" height="203" alt="cable" src="https://github.com/user-attachments/assets/951e0954-a507-4edb-8514-e76a244d78f3" />

- A mounting bracket <br>
Example: https://aliexpress.com/item/1005006425749599.html
<img width="110" height="110" alt="bracket" src="https://github.com/user-attachments/assets/06ec4d4b-1815-4322-8d41-9627abb804f4" />




## 🚀 Installation Guide

### Prerequisites:

- A computer for initial SD card flashing.
- Internet access for downloads and configuration.



## Optional: Enclosures and 3D Printing
You can choose any suitable enclosure for your basestation—off-the-shelf waterproof cases work great for outdoor use. For a custom fit, 3D-printable files are available in the [print_files](print_files) folder as an optional starting point. Feel free to modify or design your own!

Here's an example of various enclosure options to inspire you:  
<img width="1000" height="275" alt="coll" src="https://github.com/user-attachments/assets/96d59010-52d4-4a1a-acc0-da424a6dbc85" />


*(Image shows a range of colorful, rugged cases suitable for electronics projects.)*

If you decide to 3D print a case using the provided files:  
- **Recommended Materials**: PETG, ASA, or PLA+ for durability.  
- **Orientation**: Print flat (bottom side down) for best results.  
- **Supports**: Not required.  
- **Infill**: 20-40% is typically sufficient.  

No 3D printer? Services like [Craftcloud3D](https://craftcloud3d.com/) can print and ship custom parts for you.

### 1. Assemble the Main Board
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

