# STM32_WaterLevel_Project
# Water Level Monitoring and Control System using STM32 (FreeRTOS)

This project is a real-time water level monitoring and motor control system developed on the STM32F103C8T6 (Blue Pill) board using FreeRTOS. It features digital water level sensing, scheduled tank cleaning, password-protected settings, and real-time status display via LCD.

---

## 🚀 Features

- 💧 **Water Level Detection** using digital probes connected to GPIO
- 🔁 **Motor Control** via GPIO-based relay or MOSFET
- 🔔 **Buzzer Alerts** for low/high level
- 🧠 **User Settings** (water level threshold & cleaning schedule)
- 🕒 **RTC-based Cleaning Schedule**
- 🔐 **4-Digit Password Protection** (default: `0000`)
- 💾 **EEPROM/Flash Storage** for saving user preferences
- 📟 **LCD 16x2 Display** via I2C (PCF8574)
- ⌨️ **4x4 Keypad Interface**
- ⏱️ **FreeRTOS-based Tasks, Queues, and Semaphores**

---

## 🧩 System Architecture

- **Input**
  - Keypad (for password + setting changes)
  - Water level probes
  - RTC alarm (for cleaning schedule)
- **Output**
  - Motor (via relay/MOSFET)
  - LCD (PCF8574 I2C)
  - Buzzer (GPIO)
- **RTOS Components**
  - Tasks: Button Handler, Motor Control, LCD Update, Cleaning Scheduler
  - Semaphore: From ISR (button or timer) to Motor Task
  - Queue: From Motor Task to LCD Task
  - Timer: RTC interrupt
