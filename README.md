# MPU6050-LoPy4
Simple library for MPU6050 on LoPy4 with micropython

Slightly adapted from [adamjezek98](https://github.com/sparkfun/MPU-6050_Breakout)

To be able to import the library place it in a dir named `lib/` on the LoPy4

SCL connected to pin P9, SDA to pin P10<br/>
example usage:

```python
from machine import I2C, Pin
import mpu6050

i2c = I2C()
accelerometer = mpu6050.accel(i2c)
while True:
    vals = accelerometer.get_values()
    print(vals)
```
```
Out: {'GyZ': -41, 'GyY': -113, 'GyX': 644, 'Tmp': 25.33, 'AcZ': -2588, 'AcY': 8, 'AcX': 17612}
```
Accelerometer/Gyroscope values are in int16 range (-32768 to 32767)<br/>
If the mpu6050 loses power, you have to call __init__() again
