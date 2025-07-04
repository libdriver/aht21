### 1. Board

#### 1.1 Board Info

Board Name: Raspberry Pi 4B.

IIC Pin: SCL/SDA GPIO3/GPIO2.

### 2. Install

#### 2.1 Dependencies

Install the necessary dependencies.

```shell
sudo apt-get install libgpiod-dev pkg-config cmake -y
```

#### 2.2 Makefile

Build the project.

```shell
make
```

Install the project and this is optional.

```shell
sudo make install
```

Uninstall the project and this is optional.

```shell
sudo make uninstall
```

#### 2.3 CMake

Build the project.

```shell
mkdir build && cd build 
cmake .. 
make
```

Install the project and this is optional.

```shell
sudo make install
```

Uninstall the project and this is optional.

```shell
sudo make uninstall
```

Test the project and this is optional.

```shell
make test
```

Find the compiled library in CMake. 

```cmake
find_package(aht21 REQUIRED)
```

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
./aht21 -i

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
./aht21 -p

aht21: SCL connected to GPIO3(BCM).
aht21: SDA connected to GPIO2(BCM).
```

```shell
./aht21 -t read --times=3

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
aht21: temperature: 27.7C.
aht21: humidity: 24%.
aht21: temperature: 27.6C.
aht21: humidity: 24%.
aht21: temperature: 27.6C.
aht21: humidity: 24%.
aht21: finish read test.
```

```shell
./aht21 -e read --times=3

aht21: 1/3.
aht21: temperature is 27.67C.
aht21: humidity is 23%.
aht21: 2/3.
aht21: temperature is 27.66C.
aht21: humidity is 23%.
aht21: 3/3.
aht21: temperature is 27.68C.
aht21: humidity is 23%.
```

```shell
./aht21 -h

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

