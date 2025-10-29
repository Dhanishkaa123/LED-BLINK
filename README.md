# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
   <img width="1600" height="956" alt="image" src="https://github.com/user-attachments/assets/6ff0ac35-1bc6-48e6-89ae-5c3c53df80b7" />


2. Click **File → New STM32 Project**.
   <img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/eaa1c2c3-bddc-4c9e-948c-1cffd33c46c1" />
<img width="1600" height="940" alt="image" src="https://github.com/user-attachments/assets/85db288b-6ff0-428b-a973-d120f04053bb" />


3. Select the **target microcontroller** or board and click **Next**.
   <img width="1600" height="848" alt="image" src="https://github.com/user-attachments/assets/f42a0750-fdc9-4298-92d9-c803aecc2b7d" />





4. Name the project.
   <img width="1600" height="938" alt="image" src="https://github.com/user-attachments/assets/27585dc1-e3d6-42b5-ab1f-28bb83c04731" />


5. The corresponding `.ioc` file will be generated automatically.
   <img width="1600" height="936" alt="image" src="https://github.com/user-attachments/assets/c086139d-d913-47f4-81f7-dfd49962213e" />


6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
<img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/849dc0e0-bd88-4c50-b200-9c612e54c854" />

<img width="1110" height="624" alt="image" src="https://github.com/user-attachments/assets/b7abcd80-797d-451f-a7c3-23f303822423" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   <img width="1600" height="948" alt="image" src="https://github.com/user-attachments/assets/1fe17556-21d3-432c-ab70-aad662bb10af" />

 
8. Edit the generated main program as required.
  <img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/6b5f6138-1e51-4dbf-82fd-7c74531e5cfd" />

9. Click **Project → Build All**.
    <img width="967" height="242" alt="image" src="https://github.com/user-attachments/assets/731372a2-bb99-41f2-a642-5c8f24af71d5" />


10. Link the **HEX file** using the post-build process.
    <img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/a0f96bb2-99fe-4af6-99f6-a777e590a7f6" />


11. Click **Debug** and connect the **STM Nucleo Board**.
<img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/4f0353d4-8f7c-44d0-bf28-3870bd39425f" />



12. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/33203e45-5af6-43d6-8849-b30a745dfc48" />


CASE 2: LED OFF

![Uploading image.png…]()


---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
