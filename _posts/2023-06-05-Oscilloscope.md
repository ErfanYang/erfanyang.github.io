
## 1. Acquisition system
**sample rate**
采样时间=存储深度/采样率
采样时间=时基(T/div)$*10 div$ 即整个屏幕范围内的时间总长度
采集满一个屏幕，时基一定，采集一屏的时间就一定，从而决定存储深度和采样率
-->采样率=存储深度/采样时间=14M/(10ms/div * 10div)
为什么导出的波形数据时间从负开始，因为触发点时刻t=0，触发点之前是预触发数据。可调节波形水平位移，把触发点放到屏幕最左边那列像素
示波器如何不更改采样率的前提下，更改时基？ - 知乎用户的回答 - 知乎 https://www.zhihu.com/question/333507566/answer/739169780
[关于示波器的采样率三个问题 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/336739793)
**memory depth**
**waveform interpolation**
## 2. Input
**channels**
**coupling**
**impedance**

## 3. Vertical System
**bandwidth**
**vertical resolution**
## 4. Horizontal System
## 5. Trigger System
### coupling 

| mode | frequency response                                                    |
| ---- | --------------------------------------------------------------------- |
| DC   | pass all components of the signal                                     |
| AC   | block DC components and attenuate signal below 8Hz                    |
| LFRJ | block DC components and attenuate low-frequency components below 2MHz |
| HFRJ | attenuate high-frequency components above 1.2 MHz                     |
| Noise RJ     |                                                                       |
### Type
- edge trigger
- slope trigger
- pulse width trigger
- video 
- windows
- interval
- dropout
- runt
- pattern
- serial
- I2C
- SPI
- UART
- CAN
- LIN
## 6. Measurement
![[29b3734d3423f8d945c689f1f0265d9.jpg]]
Ref: 
1. [关于示波器的触发功能（下篇） (teledynelecroy.com.cn)](https://www.teledynelecroy.com.cn/Upload/File/20150331150959.pdf)
2. [Introduction to Oscilloscopes: Instructor's Guide (wisc.edu)](https://www.physics.wisc.edu/courses/home/fall2020/321/lab_equipment/MSO2014_scope_tutorials/Basic-Scopes/Basic-Scopes-Instructor-Guide.pdf)
![[Pasted image 20230601174109.png|inline]]
![[Pasted image 20230601174413.png|+inline]]

Vertical

| Parameters | Meaning                                                                                                                                                   |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| max        | Highest value in input waveform                                                                                                                           |
| min        | Lowest value in input waveform                                                                                                                            |
| pk-pk      | Difference between maximum and minimum data values |
| ampl       | Difference between top and base in a bimodal signal, or between max and min in an unimodal signal                                                                                                                                                         |
| top        | Value of most probable higher state in a bimodal waveform                                                                                                                                                          |
| base       | Value of most probable lower state in a bimodal waveform                                                                                                                                                          |
| mean       | Average of all data values                                                                                                                                                          |
| cmean      |  Average of all data values in the first cycle                                                                                                                                                         |
| stdev      |  Standard deviation of all data values                                                                                                                                                         |
| cstd       |   Standard deviation of all data values in the first cycle                                                                                                                                                       |
| vrms       |   Root mean square of all data values                                                                                                                                                        |
| crms       |   Root mean square of all data values in the first cycle                                                                                                                                                        |
| fov        |   Overshoot after a falling edge;(base -min)/Amplitude                                                                                                                                                        |
| rov        |   Overshoot after a rising edge;(max-top)/Amplitude                                                                                                                                                        |
| fpre       |   Overshoot after a falling edge;(max-top)/Amplitude                                                                                                                                           |
| rpre       |   Overshoot after a rising edge;(base -min)/Amplitude                                                                                                                                                        |
| level@X    |   the voltage value of the trigger point                                                                                                                                                        |
Horizontal

| Parameters | Meaning                                                                                                                                                                                                                                                                                                                                                                           |
|:---------- |:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Period     | Time between the middle threshold points of two consecutive, likepolarity edges                                                                                                                                                                                                                                                                                                  |
| Freq       | Reciprocal of period                                                                                                                                                                                                                                                                                                                                                              |
| +Wid       | Width measured at 50% level and positive slope                                                                                                                                                                                                                                                                                                                                    |
| -Wid       | Width measured at 50% level and negative slope                                                                                                                                                                                                                                                                                                                                    |
| Rise Time  | Duration of rising edge from 10-90%                                                                                                                                                                                                                                                                                                                                               |
| Fall Time  | Duration of falling edge from 90-10%                                                                                                                                                                                                                                                                                                                                              |
| Bwid       | Time from the first rising edge to the last falling edge, or the first falling edge to the last rising edge at the "50%" crossing                                                                                                                                                                                                                                                 |
| +Dut       | Time difference between the "50%" threshold of a rising edge to the "50% threshold of the next falling edge of the pulse                                                                                                                                                                                                                                                          |
| -Dut       | Time difference between the "50%" threshold of a falling edge to the "50% threshold of the next rising edge of the pulse                                                                                                                                                                                                                                                          |
| Delay      | Time from the trigger to the first transition at the 50% crossing                                                                                                                                                                                                                                                                                                                 |
| Time@Level | Time from the trigger to each rising edge at the "50%" crossing. <br> When Statistics is Off, it shows the time from the trigger to the last rising edge at the "50%" crossing. <br> When Statistics is On, it shows the Current, Mean, Min, Max, Standard Deviation of time from the trigger to each rising edge at the "50%" crossing in multiple frames (number = Count). "]:} |
| Phase      | Phase difference between two edges                                                                                                                                                                                                                                                                                                                                                |
| FRR        | Time from the first rising edge of channel "A" to the following first rising edge of channel B                                                                                                                                                                                                                                                                                    |
| FRF        | Time from the first rising edge of channel A to the following first falling                                                                                                                                                                                                                                                                                                       |
Delay

| Parameters | Meaning                                                                                        |
| ---------- | ---------------------------------------------------------------------------------------------- |
| Phase      | Phase difference between two edges                                                             |
| FRR        | Time from the first rising edge of channel A to the following first rising edge of channel B  |
| FRF        | rising --> first falling                                                                                                |
| FFR        | falling --> first rising|
| FFF        | falling --> first rising|
| LRR        | rising --> last rising|
| LRF        | rising --> last falling|
| LFR        |  falling --> last rising|
| LFF        | falling --> last falling |
| Skew       | Time of source A edge minus time of nearest source B edge |

## 7. Math