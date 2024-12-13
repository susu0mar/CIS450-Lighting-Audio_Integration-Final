Project: Multitasking Control System Using FreeRTOS
Created by Souad Omar, Sukeina Ammar, Heather Buzle, & Firas Abueida. :)


**Overview of Project:**

This project demonstrates a multitasking control system built on FreeRTOS, leveraging its threading structure to allow concurrent execution of tasks and efficient resource sharing. The implementation is based on the ESP32-C3 microcontroller and includes a comprehensive architecture encompassing the following components:

- User Interface (UI) via an LCD screen.

- Lighting Control Task for managing LED brightness.

- Voice Announcement Task for real-time audio feedback.

- Internal hardware capabilities of the ESP32-C3.


**Project Architecture:**

User Interface (UI):

- The UI is displayed on the LCD screen and dynamically updates based on user actions.

- The screen reflects the current brightness level, providing immediate visual feedback as the knob is adjusted.


**Lighting Control Task:**

- Monitors the knob's position to adjust LED brightness.

- Runs in a loop, updating a shared variable with the new brightness level.

- Uses FreeRTOS's xEventGroupSetBits to signal the Voice Announcement Task whenever a brightness change occurs.


**Voice Announcement Task:**

- Operates independently of the Lighting Control Task to provide real-time audio feedback.

- Triggered by xEventGroupWaitBits, it reads the shared brightness value and constructs a voice announcement.

- Plays the corresponding audio through the connected speaker.


**ESP32-C3 Hardware:**

The microcontroller supports multitasking through its hardware features, including knob panels, LEDs, and audio output components.

This project specifically utilizes the LED, knob panel, and audio output to implement a concurrent control system.


**Key Features**

Concurrent Task Execution: FreeRTOS allows multiple tasks (UI updates, brightness control, and voice announcements) to operate concurrently without interference.


**Real-Time Feedback:**

Visual: Immediate updates on the LCD screen.

Audio: Real-time voice announcements of brightness levels.

Resource Sharing: Tasks communicate efficiently using shared variables and FreeRTOS synchronization primitives like event groups.



**Requirements**:

Hardware:

ESP32-C3 microcontroller.

LCD screen for UI display.

LED and knob panel for brightness control.

Speaker for audio feedback.

Software:

FreeRTOS for task management.

Drivers for LCD, LED, and audio components.




**How to Run the Project**

1. Clone this repository:

git clone https://github.com/your-username/your-repo-name.git

2. Set up the ESP32-C3 development environment (e.g., ESP-IDF).

3. Build and flash the firmware onto the ESP32-C3.

4. Connect the hardware components (LCD, knob panel, LED, speaker) as specified in the documentation.

5. Power up the device and interact with the knob to observe the multitasking functionality.

**6. Using the Lighting Control Panel (LCP):**

To use the lighting control panel, follow these steps:

 - Plug the ESP32-C3 into the computer using a USB-C port.

 - If you haven’t already done so, build and flash the knob-example code onto the device using the terminal.

 - Wait for the device to boot, and then twist the knob to the right to select the LCP/lighting panel.

7. Assuming the USB-C port is on the right:

Twist the knob to the left to increase brightness.

Twist the knob to the right to decrease brightness.

You will hear an audio announcement for brightness adjustments.

Press the knob to change the color/warmth of the light.



Acknowledgments:

This project highlights the power of FreeRTOS and ESP32-C3 hardware to create efficient, multitasking embedded systems. The architecture ensures seamless integration of audio and visual tasks, providing an intuitive and responsive user experience.
