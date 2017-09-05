---
layout: post
title: Android Things WiFi设置
---

需要为Android Things设置WiFi帐号密码


Android Things是google新推出的物联网操作系统，可以用在树梅派开发板上。
Android things开发工具是android studio，跟开发android应用有很多相似的地方。

## 利用adb连接到树梅派上
adb connect ip  

## DuFi为WiFi的名称，66554433 为WiFi的密码
adb shell am startservice -n com.google.wifisetup/.WifiSetupService -a WifiSetupService.Connect -e ssid DuFi -e passphrase 66554433 

移除树梅派的网线，等一会会自动连接WiFi，如果将树梅派的HDMI输出连接到显示器上，会看到下面显示新的连接WIFI后的ip
## 连接到新的ip，就可以在android studio中查看到已连接的树梅派设备。
adb connect  newIP  

