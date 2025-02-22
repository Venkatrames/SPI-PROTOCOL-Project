# SPI Design Project

## Overview
This project demonstrates the design and implementation of an SPI (Serial Peripheral Interface) communication system using an Arduino microcontroller. The project includes both SPI Master and SPI Slave functionality, enabling efficient data transfer between devices.

## Features
- SPI Master-Slave communication setup
- Configurable SPI modes (Mode 0 - Mode 3)
- Adjustable SPI clock speed
- Data transmission and reception using SPI protocol

## Components Required
- Arduino Board (Uno, Mega, or any compatible board with SPI support)
- SPI-compatible slave device (e.g., another Arduino, sensor, or display module)
- Jumper wires
- Breadboard (optional)

## Circuit Diagram
- **SPI Master (Arduino)**:
  - MOSI (Master Out Slave In) → Pin 11
  - MISO (Master In Slave Out) → Pin 12
  - SCK (Serial Clock) → Pin 13
  - SS (Slave Select) → Pin 10

- **SPI Slave (Arduino or other device)**:
  - Connect MOSI, MISO, SCK, and SS appropriately to the slave device.

## Installation and Usage
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/spi-design-project.git
   ```
2. Open the Arduino IDE and install the SPI library if not already available.
3. Load the SPI Master and SPI Slave sketches onto the respective Arduino boards.
4. Connect the Arduino boards as per the circuit diagram.
5. Open the Serial Monitor to observe data transmission.

## Code
### SPI Master Code
```cpp
#include <SPI.h>

void setup() {
  SPI.begin();
  pinMode(SS, OUTPUT);
  digitalWrite(SS, HIGH);
}

void loop() {
  digitalWrite(SS, LOW);
  SPI.transfer(0x55);
  digitalWrite(SS, HIGH);
  delay(1000);
}
```

### SPI Slave Code
```cpp
#include <SPI.h>

volatile byte receivedData;

void setup() {
  pinMode(MISO, OUTPUT);
  SPI.begin();
  SPI.attachInterrupt();
}

ISR(SPI_STC_vect) {
  receivedData = SPDR;
}

void loop() {
  Serial.println(receivedData);
  delay(500);
}
```

## License
This project is licensed under the MIT License.

## Contributing
Feel free to fork this repository and submit pull requests. Contributions are always welcome!

## Contact
For any issues or queries, contact [your email] or visit the GitHub repository.

**GitHub Repository**: [https://github.com/yourusername/spi-design-project](https://github.com/yourusername/spi-design-project)

