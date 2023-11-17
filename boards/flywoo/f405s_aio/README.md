https://flywoo.net/products/goku-gn-405s-20a-aio-bmi270-25-5-x-25-5


Sensors:
1. MCU: [STM32F405 BGA](https://www.st.com/resource/en/datasheet/stm32f405rg.pdf)
2. IMU: ICM42688P
3. Barometer: [BMP280](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmp280-ds001.pdf)
4. Onboard LED: ws2812*4
5. USB Does not take up a UART

- For serial porting, refer to file `boards/flywoo/f405s_aio/nuttx-config/include/board.h`
    - [PINOUT] <-> <Firmware Port> <-> (PX4 Mapping) <-> |USB Port| <-> {Hardware Connected}
    - [TX/RX1] <-> <UART 1> <-> (N/A) <->      |/dev/ttyS0|  <-> {Not used}
    - [TX/RX2] <-> <UART 2> <-> (TEL1/101) <-> |/dev/ttyS1|  <-> {Not used}
    - [TX/RX3] <-> <UART 3> <-> (N/A) <->      |N/A|         <-> {Not used, I2C }
    - [TX/RX4] <-> <UART 4> <-> (TEL2/102) <-> |/dev/ttyS2| <->  {Companion computer}
    - [TX/RX6] <-> <UART 6> <-> (UART6) <->    |/dev/ttyS3| <->  {Lidar}
    - [VTX] <->    <UART 5> <-> (N/A) <->      |N/A|        <->  {Not used, dedicated for VTX SBUS}
