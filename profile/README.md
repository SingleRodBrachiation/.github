# Single-Rod Brachiation

An organization for managing source code for the joint research project on single-rod brachiation between the Czech Technical University, Faculty of Mechanical Engineering, Dept. of Instrumentation and Control Engineering and Tokyo University of Agriculture and Technology, Dept. of Mechanical Systems Engineering.

Currently the organization contains the Arduino control loop program (C++) who's first versions were written by Hijiri Akahane but was later heavily modified and extended by Juraj Lieskovský.
The program is accompanied by a smaller utility program for setting the appropriate parameters for ensuring that the prescribed torque is aimed for by the controller.
As a side note there also exists a short [script for parsing Arduino serial output](https://gist.github.com/lieskjur/6f5b448fc157e70ad28dbcabc78c7a46) managed as a gist.
An additional repository then contains code for simulating the single-rod robot in julia and creating plots for the journal paper (maybe these two could be separated).

I would suggest we manage all relevant code that would/does benefit from source control here, adding additional organization owners as we see fit.

# Electrical design

Motor driver - [EPOS2](https://www.maxongroup.com/maxon/view/product/control/Positionierung/367676)
Control board - [NUCLOE-F103RB](https://www.st.com/en/evaluation-tools/nucleo-f103rb.html)
Encoder counter - [MikroE Counter Click](https://www.mikroe.com/counter-click?srsltid=AfmBOooAc547Hi3YX7WqDLprGw8HHImTrGliJFiZXVDFnyCqJhTguAVZ)
IMU - [Adafruit BNO055](https://www.adafruit.com/product/2472)

| Counter | STM32 |
| --- | --- |
| 3V3 | 3V3 |
| GND | GND |
| SDI | D11/MOSI |
| SDO | D12/MISO |
| SCK | D13/SCK |
| CS | D10/CS |

| IMU | STM32 |
| --- | --- |
| 3V3 | 3V3 |
| GND | GND |
| SDA | D14/SDA |
| SCL | D15/SCL |
