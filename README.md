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

## 安裝完畢後開啟QGC

![{7578A72E-F956-4350-8DD4-A1F663069DDE}](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/3.png)

開啟後會要選擇單位(確定沒問題就點選OK)
![{9D169FFD-C8AD-47FF-955F-9557274B6EE6}](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/4.png)

選擇Vehicle information(Fireware選擇PX4 Pro 且Vehicle為Multi-Rotor)後即完成安裝
![{05D5DA2A-B41A-4D3B-800C-9144306576F7}](https://github.com/aa540799/Droneproject/raw/e97bb5fdbfdf71cf374473bbca5d9c54a0b6ffe1/img/5.png)


# 安裝韌體
1.開啟QGC

2.點選圖像

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/6.jpg)

3.點選Vehicle Configuration

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/7.jpg)

4.點選Fireware

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/8.jpg)

5.這邊會要求將USB插入無人機

![image](https://github.com/aa540799/Droneproject/raw/b518e938b58e3dd3d5e388c4d2835d23a1c572e7/img/9.jpg)

5-1如果USB已經插入請先將USB移除再重新插入

![image](https://github.com/aa540799/Droneproject/raw/66f4b81bf5ea5ded77ab8e596d8f88f340178058/img/10.jpg)

6.選擇PX4 PRO stable Relase後點選ok(也可自行建立韌體後燒入，這邊建議直接使用最新版)

![image](https://github.com/aa540799/Droneproject/blob/9e7fa08628825fd5cf42474b75416e5688d95629/img/11.jpg)
![image](https://github.com/aa540799/Droneproject/blob/9e7fa08628825fd5cf42474b75416e5688d95629/img/12.png)

等待QGC將韌體安裝完成(完成後會一直發出三長音三短音為正常現象，待後續操作完成即可停止聲響)

![image](https://github.com/aa540799/Droneproject/row/e5c04a596c1f971b7d5b78267c39645d68f2e49a/img/15.jpg)

注意:如果直接使用QGC安裝後版本有問題(安裝1.16.0但結果為1.17.0beta)請至以下網址:

https://github.com/PX4/PX4-Autopilot/releases 直接下載px4檔進行安裝(請依照飛控板型號下載對應版本 e.g. Pixhawk 6C則下載px4_fmu-v6c_default.px4)




