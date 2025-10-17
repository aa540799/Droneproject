---
title: 無人機韌體轉換(Ardupilot->PX4)

---

# 無人機韌體轉換(Ardupilot->PX4)和校正

這邊將從頭教學如何將無人機韌體從Ardupilot轉換成PX4並做後續校正

# 安裝QGroundControl(QGC)

透過QGC重新為無人機重刷韌體

## **window**
官方網站:https://docs.qgroundcontrol.com/master/en/qgc-user-guide/getting_started/download_and_install.html

下載 **QGroundControl-installer.exe**

![image](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/1.png)

或直接點選以下連結下載:https://d176tv9ibo4jno.cloudfront.net/latest/QGroundControl-installer.exe

開啟下載的exe檔進行安裝

![image](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/2.png)

## **Ubuntu Linux**
官方網站:https://docs.qgroundcontrol.com/master/en/qgc-user-guide/getting_started/download_and_install.html

```bash
# 安裝前置套件
sudo usermod -aG dialout "$(id -un)"
sudo systemctl mask --now ModemManager.service
sudo apt install gstreamer1.0-plugins-bad gstreamer1.0-libav gstreamer1.0-gl -y
sudo apt install libfuse2 -y
sudo apt install libxcb-xinerama0 libxkbcommon-x11-0 libxcb-cursor-dev -y

# 下載並執行
wget https://d176tv9ibo4jno.cloudfront.net/latest/QGroundControl-x86_64.AppImage
chmod +x QGroundControl-x86_64.AppImage
#執行QGC
./QGroundControl-x86_64.AppImage
```

## 首次開啟QGC

![{7578A72E-F956-4350-8DD4-A1F663069DDE}](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/3.png)

開啟後會要選擇單位(確定沒問題就點選OK)
![{9D169FFD-C8AD-47FF-955F-9557274B6EE6}](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/4.png)

選擇Vehicle information(Fireware選擇PX4 Pro 且Vehicle為Multi-Rotor)後即完成安裝
![{05D5DA2A-B41A-4D3B-800C-9144306576F7}](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/5.png)


# 安裝韌體
1.點選圖像

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/6.jpg)

2.點選Vehicle Configuration

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/7.jpg)

3.點選Fireware

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/8.jpg)

4.這邊會要求將USB插入無人機

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/9.jpg)

4-1如果USB已經插入請先將USB移除再重新插入

![image](https://github.com/aa540799/Droneproject/raw/66f4b81bf5ea5ded77ab8e596d8f88f340178058/img/10.jpg)

5.選擇PX4 PRO stable Relase後點選ok(也可自行建立韌體後燒入，這邊建議直接使用最新版)

![image](https://github.com/aa540799/Droneproject/blob/9e7fa08628825fd5cf42474b75416e5688d95629/img/11.jpg)

等待QGC將韌體安裝完成(完成後會一直發出三長音三短音為正常現象，待後續操作完成即可停止聲響)

![image](https://github.com/aa540799/Droneproject/raw/e5c04a596c1f971b7d5b78267c39645d68f2e49a/img/15.jpg)

注意:如果直接使用QGC安裝後版本有問題(安裝1.16.0但結果為1.17.0alpha 畫面如下)

![image](https://github.com/aa540799/Droneproject/raw/f34d84c4a1b4c8ec40077ba0ff1e68d0c160192a/img/19.jpg)

請至以下網址:
https://github.com/PX4/PX4-Autopilot/releases 

直接下載px4檔(請依照飛控板型號下載對應版本 e.g. Pixhawk 6C則下載px4_fmu-v6c_default.px4)
下載完畢後再重新執行一次第5步

這次安裝請選用下載的px4檔
![image](https://github.com/aa540799/Droneproject/raw/e70ba6a602afeab43e21be31843249b49964d43d/img/20.jpg)

![image](https://github.com/aa540799/Droneproject/raw/e70ba6a602afeab43e21be31843249b49964d43d/img/21.jpg)

確認韌體版本沒問題即可進行下一步

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/22.jpg)

# 無人機校正


1.設定Airframe(選擇Quadrotor x 的 Generic Quadcopter)
  注意:記得點選Apply and Restart(完成後三長音三短音將會停止)

![image](https://github.com/aa540799/Droneproject/raw/52b1bb2900753ddef5239448caaccecdfa227cf2/img/13.jpg)


2.分別進行Compass、Gyroscope、Accelerometer、LevelHorizon校正
![image](https://github.com/aa540799/Droneproject/raw/52b1bb2900753ddef5239448caaccecdfa227cf2/img/14.jpg)

2-1.Compass

![image](https://github.com/aa540799/Droneproject/raw/52b1bb2900753ddef5239448caaccecdfa227cf2/img/16.jpg)

需要針對6個不同的面進行旋轉(建議擺在桌面上進行校正)

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/23.jpg)

注意!一定要出現Compass Calibration Complete才表示校正成功，出現後點選Reboot Vehicle，會自動重啟

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/24.jpg)

2-2.Gyroscope

將無人機擺放在桌面上後點選OK，等待亮綠燈即可

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/25.jpg)
![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/26.jpg)

2-3.Accelerometer

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/27.jpg)

依照圖示進行不同角度的擺放(一樣建議在桌面上操作)，等待綠燈亮起即可進行下一個角度直到6個都完成

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/28.jpg)

2-4.LevelHorizon

完成Accelerometer後，將無人機平放在桌面上，直接點選LevelHorizon

![image](https://github.com/aa540799/Droneproject/raw/f2fec56d650542b30ec5ad07fe321f3d6f2bc4a3/img/29.jpg)

![image](https://github.com/aa540799/Droneproject/raw/fdfa99e212da147cfa9d26eaed2c277ca63c01c6/img/30.jpg)

等待執行完成即可

![image](https://github.com/aa540799/Droneproject/raw/fdfa99e212da147cfa9d26eaed2c277ca63c01c6/img/31.jpg)

# 遙控器校正

1.Radio

點選Radio後將遙控器打開

![image](https://github.com/aa540799/Droneproject/raw/fdfa99e212da147cfa9d26eaed2c277ca63c01c6/img/30.jpg)

選擇Mode 1後進行Calibrate

![image](https://github.com/aa540799/Droneproject/raw/59c73bddef7e270b1f58bc79388d1c0f25ad1978/img/17.jpg)

依照文字及右邊圖案指示完成操作即可
![image](https://github.com/aa540799/Droneproject/raw/f07a74a8af5a36496f349b5505965b2e95d97b89/img/33.jpg)

2.Flight Modes

點選Flight Modes依照以下設定即可

![image](https://github.com/aa540799/Droneproject/raw/f07a74a8af5a36496f349b5505965b2e95d97b89/img/18.jpg)

# Power校正

只需設定Battery 1數值即可(Battery 2及ESC不須改動)

![image](https://github.com/aa540799/Droneproject/raw/c23dc06e47728e53c2138edd36ed402cc0c20159/img/34.jpg)

# Actuators校正

點選Actuators依照以下圖片進行設定

![image](https://github.com/aa540799/Droneproject/raw/c23dc06e47728e53c2138edd36ed402cc0c20159/img/35.jpg)








