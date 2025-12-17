# ESP32 1Wire DS18B20 Scanner

An ESP32 project that scans and manages multiple DS18B20 temperature sensors connected via 1Wire protocol using the ESP-IDF framework.

## About the Project

This project provides a complete solution for detecting and reading temperature data from multiple DS18B20 temperature sensors connected to an ESP32 microcontroller using the 1Wire communication protocol. The implementation uses the ESP-IDF (Espressif IoT Development Framework) for optimal performance and reliability.

## Technologies Used

- ESP32 microcontroller
- 1Wire protocol
- DS18B20 temperature sensors
- ESP-IDF framework
- C++ programming language
- CMake build system

## Project Structure

```
ESP32-1Wire-DS18B20-Scanner/
├── main/               # Main application code
├── CMakeLists.txt      # Build configuration
├── sdkconfig           # SDK configuration settings
└── README.md           # Project documentation
```

## Prerequisites

- ESP32 development board
- DS18B20 temperature sensor(s)
- ESP-IDF v4.4 or higher
- CMake 3.5 or higher
- Python 3.7 or higher
- ESP32 toolchain

## Hardware Setup

1. Connect DS18B20 sensor(s) to ESP32:
   - VCC pin to 3.3V
   - GND pin to GND
   - DQ (data) pin to GPIO pin (configured in code, typically GPIO4)

2. Add a 4.7k ohm pull-up resistor between VCC and DQ pin for reliable communication

## Installation and Configuration

1. Clone the repository
```bash
git clone https://github.com/cyberdebb/ESP32-1Wire-DS18B20-Scanner.git
cd ESP32-1Wire-DS18B20-Scanner
```

2. Set up ESP-IDF environment (if not already installed)
```bash
# Follow the official ESP-IDF installation guide
https://docs.espressif.com/projects/esp-idf/en/latest/
```

3. Configure the project
```bash
idf.py set-target esp32
idf.py menuconfig
```

4. Build the project
```bash
idf.py build
```

5. Flash to ESP32
```bash
idf.py -p /dev/ttyUSB0 flash
```

Replace `/dev/ttyUSB0` with your ESP32 serial port.

6. Monitor serial output
```bash
idf.py -p /dev/ttyUSB0 monitor
```

## Features

- Automatic detection of connected DS18B20 sensors
- Reading temperature data from multiple sensors
- 1Wire protocol implementation
- Low power consumption
- Real-time temperature monitoring
- Error handling for sensor communication failures

## Configuration

The main configuration can be adjusted in the `main/` directory:

- GPIO pin for 1Wire communication
- Temperature reading resolution
- Scan interval
- Debug output settings

Modify these settings in the source code according to your hardware setup and requirements.

## Building with CMake

The project uses CMake as the build system. Key build commands:

```bash
# Configure and build
idf.py build

# Clean build
idf.py fullclean

# Build and flash in one command
idf.py -p /dev/ttyUSB0 build flash

# Set different target
idf.py set-target esp32s3
```

## Serial Communication

The project outputs temperature readings and debug information via UART serial communication. Use a serial monitor with 115200 baud rate to view the output.

## Troubleshooting

- If sensors are not detected, verify the pull-up resistor is properly connected
- Check that the GPIO pin matches your code configuration
- Ensure all hardware connections are secure
- Monitor the serial output for error messages
- Verify the ESP-IDF installation and toolchain

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for more details.
