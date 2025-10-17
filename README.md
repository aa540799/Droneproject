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
![image](https://hackmd.io/_uploads/S1IC8mJCeg.png)
或直接點選以下連結下載:https://d176tv9ibo4jno.cloudfront.net/latest/QGroundControl-installer.exe

開啟下載的exe檔進行安裝
![image](https://hackmd.io/_uploads/Hyk9v7kRge.png)

安裝完畢後開啟QGC

![{7578A72E-F956-4350-8DD4-A1F663069DDE}](https://hackmd.io/_uploads/H1Q4u7k0gg.png)

開啟後會要選擇單位(確定沒問題就點選OK)
![{9D169FFD-C8AD-47FF-955F-9557274B6EE6}](https://hackmd.io/_uploads/r1XdumJ0ge.png)

選擇Vehicle information(Fireware選擇PX4 Pro 且Vehicle為Multi-Rotor)後即完成安裝
![{05D5DA2A-B41A-4D3B-800C-9144306576F7}](https://hackmd.io/_uploads/rJUTd71Axg.png)

## **Ubuntu Linux(版本20.04)**
官方網站:https://docs.qgroundcontrol.com/master/en/qgc-user-guide/getting_started/download_and_install.html

下載 **QGroundControl-installer.exe**
![image](https://hackmd.io/_uploads/S1IC8mJCeg.png)
或直接點選以下連結下載:https://d176tv9ibo4jno.cloudfront.net/latest/QGroundControl-installer.exe

開啟下載的exe檔進行安裝
![image](https://hackmd.io/_uploads/Hyk9v7kRge.png)

安裝完畢後開啟QGC

![{7578A72E-F956-4350-8DD4-A1F663069DDE}](https://hackmd.io/_uploads/H1Q4u7k0gg.png)

開啟後會要選擇單位(確定沒問題就點選OK)
![{9D169FFD-C8AD-47FF-955F-9557274B6EE6}](https://hackmd.io/_uploads/r1XdumJ0ge.png)

選擇Vehicle information(Fireware選擇PX4 Pro 且Vehicle為Multi-Rotor)後即完成安裝
![{05D5DA2A-B41A-4D3B-800C-9144306576F7}](https://hackmd.io/_uploads/rJUTd71Axg.png)








# 無人機韌體轉換(Ardupilot->PX4)和校正

這邊將從頭教學如何將無人機韌體從Ardupilot轉換成PX4並做後續校正

# 安裝QGroundControl(QGC)

我們這邊透過QGC重新為無人機重刷韌體
