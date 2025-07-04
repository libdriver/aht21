### 1. Chip

#### 1.1 Chip Info

Chip Name: STM32F407ZGT6.

Extern Oscillator: 8MHz.

UART Pin: TX/RX PA9/PA10.

IIC Pin: SCL/SDA PB8/PB9.

### 2. Development and Debugging

#### 2.1 Integrated Development Environment

LibDriver provides both Keil and IAR integrated development environment projects.

MDK is the Keil ARM project and your Keil version must be 5 or higher.Keil ARM project needs STMicroelectronics STM32F4 Series Device Family Pack and you can download from https://www.keil.com/dd2/stmicroelectronics/stm32f407zgtx.

EW is the IAR ARM project and your IAR version must be 9 or higher.

#### 2.2 Serial Port Parameter

Baud Rate: 115200.

Data Bits : 8.

Stop Bits: 1.

Parity: None.

Flow Control: None.

#### 2.3 Serial Port Assistant

We use '\n' to wrap lines.If your serial port assistant displays exceptions (e.g. the displayed content does not divide lines), please modify the configuration of your serial port assistant or replace one that supports '\n' parsing.

### 3. AHT21

#### 3.1 Command Instruction

1. Show aht21 chip and driver information.

   ```shell
   aht21 (-i | --information)
   ```

2. Show aht21 help.

   ```shell
   aht21 (-h | --help)
   ```

3. Show aht21 pin connections of the current board.

   ```shell
   aht21 (-p | --port)
   ```

4. Run aht21 read test, num means test times.

   ```shell
   aht21 (-t read | --test=read) [--times=<num>]
   ```

5. Run aht21 read function, num means test times.

   ```shell
   aht21 (-e read | --example=read) [--times=<num>]
   ```

#### 3.2 Command Example

```shell
aht21 -i

aht21: chip is ASAIR AHT21.
aht21: manufacturer is ASAIR.
aht21: interface is IIC.
aht21: driver version is 1.0.
aht21: min supply voltage is 2.2V.
aht21: max supply voltage is 5.5V.
aht21: max current is 0.98mA.
aht21: max temperature is 85.0C.
aht21: min temperature is -40.0C.
```

```shell
aht21 -p

aht21: SCL connected to GPIOB PIN8.
aht21: SDA connected to GPIOB PIN9.
```

```shell
aht21 -t read --times=3

aht21: chip is ASAIR AHT21.
aht21: manufacturer is ASAIR.
aht21: interface is IIC.
aht21: driver version is 1.0.
aht21: min supply voltage is 2.2V.
aht21: max supply voltage is 5.5V.
aht21: max current is 0.98mA.
aht21: max temperature is 85.0C.
aht21: min temperature is -40.0C.
aht21: start read test.
aht21: temperature: 31.5C.
aht21: humidity: 21%.
aht21: temperature: 31.3C.
aht21: humidity: 21%.
aht21: temperature: 31.2C.
aht21: humidity: 20%.
aht21: finish read test.
```

```shell
aht21 -e read --times=3

aht21: 1/3.
aht21: temperature is 30.16C.
aht21: humidity is 21%.
aht21: 2/3.
aht21: temperature is 30.10C.
aht21: humidity is 21%.
aht21: 3/3.
aht21: temperature is 30.05C.
aht21: humidity is 21%.
```

```shell
aht21 -h

Usage:
  aht21 (-i | --information)
  aht21 (-h | --help)
  aht21 (-p | --port)
  aht21 (-t read | --test=read) [--times=<num>]
  aht21 (-e read | --example=read) [--times=<num>]

Options:
  -e <read>, --example=<read>    Run the driver example.
  -h, --help                     Show the help.
  -i, --information              Show the chip information.
  -p, --port                     Display the pin connections of the current board.
  -t <read>, --test=<read>       Run the driver test.
      --times=<num>              Set the running times.([default: 3])
```

