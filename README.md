#批踢踢地震文自動發文器

###概念：
使用兩個位於不同位置的G-Senso偵測地震的發生。
當G-Senso偵測到的加速度超過設定的門檻值時，發出對伺服器發出通知，若伺服器同時收到兩個sersor的通知時，就會認為不是誤報而自動在批踢踢上發地震文。

###系統架構
- 用兩塊mbed平台的開發板(Seeed Studio Arch Pro)，接上6DOF的姿態傳感器(MPU6050)執行偵測，並透過MQTT將資訊送往伺服器。
- 用一個 Respberry Pi作為伺服器，安裝Mosquitto作為MQTT Server，並且負責判斷與發文的工作。
- 以上組件以區域網路連接

###軟體開發
- MQTT Server: Mosquitto
- MQTT Client lib: Paho

