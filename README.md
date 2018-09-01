# Status Class

Status Class extending the Arduino Serial library capabilities with the following features:

- adding millis info,
- print error or warning message,
- print 8-bits or 16-bits register bit by bit to simplify work with communication protocols,

Library can use [I2C Sensor Interface](https://github.com/MatthewPatyk/I2C-Sensor-Interface) to unify working with I2C devices.

## Usage

To see a real-life usage example, open the [ADXL345](https://github.com/MatthewPatyk/ADXL345-Arduino-I2C-library) usage example, or my other projects that utilize that class.

### Configuration

**Important**: in order to use class with different than `115200` baudrate and different Arduino Serial objects in file `Status.cpp` change the following:

- to change baudrate:

```cpp
#define STATUS_CLASS_SERIAL_BAUDRATE 115200UL
```

- to change Serial object:

```cpp
StatusClass Status(Serial, STATUS_CLASS_SERIAL_BAUDRATE, TIME_INTERWAL_IN_MS);
```

Where in place of `Serial` you can use {Serial1, Serial2, Serial3, Serial4} in the case of Due board, 'Serial' is set as working default for most Arduino boards.

#### I2C Sensor Interface usage

In order to use this library with [I2C Sensor Interface](https://github.com/MatthewPatyk/I2C-Sensor-Interface), you have to in `Status.cpp` file change the `STATUS_IS_USING_SENSOR` define to:

```cpp
#define STATUS_IS_USING_SENSOR 0x01
```

and include [I2C_Sensor.h](https://github.com/MatthewPatyk/I2C-Sensor-Interface/blob/master/I2C_Sensor.h) file to project.
