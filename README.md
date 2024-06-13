This project is a heart rate monitoring android app. It includes 2 part:
  - Hardware: ESP32, heart rate monitoring sensor (MAX30100), LCD1602. Code in folder esp32 is used to read data from sensor, display data on LCD, send data to app through BLE and implement the flow like a smart watch.
  - Software: Android App which is written in java receives data from ESP32 through BLE. This app will display the data, analyze and represent them graphically.
![z5533619381992_6f03510c71099c2b6c92a942979047ff](https://github.com/LeDangThien/HEART-RATE-MONITORING-ANDROID-APP/assets/166800814/e3d471c7-f67a-4710-a9b9-a7be772618ee)

The flow of this project:
  - 0 state: No one touch the sensor. The LCD will be cleared and BLE will be disconnected.
  - 1 state: LCD will display the data from sensor in 30 seconds.
  - 2 state: LCD will be cleared in 30 seconds.
  - 3 state: ESP32 receives signal from app and sends data to app.
  - First, it is in state 0. If someone touches the sensor, it will switch to state 1. After 30 seconds, if you still touch the sensor, it will switch to state 2. After 30 seconds, if you still touch the sensor, it
will switchs back to state 1. When it is in state 1 or 2, if no one touches the sensor in 3 seconds, it will switch to state 0. When it is in state 1 or 2 and you press start button on your app, it will switch to state3
until you press stop button. Then, it switches back to ste 1.
