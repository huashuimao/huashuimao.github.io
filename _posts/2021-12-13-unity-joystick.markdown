---
layout: post
title:  "Unity的手柄映射关系"
date:   2021-12-13 23:42:35 +0800
categories: work joystick
---
策划想要在战斗中接入手柄，由于Unity的版本是 2018.4 ，没法直接使用新版 **[InputSystem介绍]{:target="_blank"}**，**[InputSystem手册]{:target="_blank"}** ，外加还有自定义功能需求，故而就只能自己扫一遍

吐槽：看到战双有，我们也要有，简单粗暴的战斗中使用，没有对整个游戏进行手柄操作的适配迭代，真的是无奈啊

|Xbox手柄|Android|PC|
|----|----|----|
|名字|Xbox Wireless Controller|Controller (Xbox One For Windows)|
|按键| | |
|A|JoystickButton0|JoystickButton0|
|B|JoystickButton1|JoystickButton1|
|X|JoystickButton2|JoystickButton2|
|Y|JoystickButton3|JoystickButton3|
|左肩键|LeftShift, JoystickButton4|JoystickButton4|
|右肩键|RightShift, JoystickButton5|JoystickButton5|
|左摇杆按下|JoystickButton8|JoystickButton8|
|右摇杆按下|JoystickButton9|JoystickButton9|
|三杠|JoystickButton10|JoystickButton6|
|两框|JoystickButton11|JoystickButton7|
|商标键|JoystickButton12| |
|摇杆| | |
|左摇杆左推|Axis1（0 ~ -1）|Axis1（0 ~ -1）|
|左摇杆右推|Axis1（0 ~ 1）|Axis1（0 ~ 1）|
|左摇杆上推|Axis2（0 ~ -1）|Axis2（0 ~ -1）|
|左摇杆下推|Axis2（0 ~ 1）|Axis2（0 ~ 1）|
|右摇杆左推|Axis3（0 ~ -1）|Axis4（0 ~ -1）|
|右摇杆右推|Axis3（0 ~ 1）|Axis4（0 ~ 1）|
|右摇杆上推|Axis4（0 ~ -1）|Axis5（0 ~ -1）|
|右摇杆下推|Axis4（0 ~ 1）|Axis5（0 ~ 1）|
|左方向键|Axis5（-1）|Axis6（-1）|
|右方向键|Axis5（1）|Axis6（1）|
|上方向键|Axis6（-1）|Axis7（1）|
|下方向键|Axis6（1）|Axis7（-1）|
|左扳机|Axis7（0 ~ 1）, Axis13（0 ~ 1）|Axis3（0 ~ -1）, Axis9（0 ~ 1）|
|右扳机|Axis8（0 ~ 1）、Axis12（0 ~ 1）|Axis8（0 ~ 1）、Axis10（0 ~ 1）|

|PS4手柄|Android|PC|
|----|----|----|
|名字|Wireless Controller Touchpad|Wireless Controller|
|按键| | |
|叉|JoystickButton0|JoystickButton1|
|圈|JoystickButton1|JoystickButton2|
|方块|JoystickButton2|JoystickButton0|
|三角|JoystickButton3|JoystickButton3|
|左肩键|LeftShift, JoystickButton4|JoystickButton4|
|右肩键|RightShift, JoystickButton5|JoystickButton5|
|左扳机按下|LeftAlt, JoystickButton6|JoystickButton6, 默认Axis4(-1)|
|右扳机按下|RightAlt, JoystickButton7|JoystickButton7, 默认Axis5(-1)|
|左摇杆按下|JoystickButton8|JoystickButton10|
|右摇杆按下|JoystickButton9|JoystickButton11|
|Options|JoystickButton10|JoystickButton9|
|Share|JoystickButton11|JoystickButton8|
|商标键|JoystickButton12|JoystickButton12|
|触摸板按下|Mouse0|JoystickButton13|
|摇杆| | |
|左摇杆左推|Axis1（0 ~ -1）|Axis1（0 ~ -1）|
|左摇杆右推|Axis1（0 ~ 1）|Axis1（0 ~ 1）|
|左摇杆上推|Axis2（0 ~ -1）|Axis2（0 ~ -1）|
|左摇杆下推|Axis2（0 ~ 1）|Axis2（0 ~ 1）|
|右摇杆左推|Axis3（0 ~ -1）|Axis3（0 ~ -1）|
|右摇杆右推|Axis3（0 ~ 1）|Axis3（0 ~ 1）|
|右摇杆上推|Axis4（0 ~ -1）|Axis6（0 ~ -1）|
|右摇杆下推|Axis4（0 ~ 1）|Axis6（0 ~ 1）|
|左方向键|Axis5（-1）|Axis7（-1）|
|右方向键|Axis5（1）|Axis7（1）|
|上方向键|Axis6（-1）|Axis8（1）|
|下方向键|Axis6（1）|Axis8（-1）|
|左扳机|Axis7（0 ~ 1）, Axis13（0 ~ 1）|Axis4（-1 ~ 1）, 常驻-1|
|右扳机|Axis8（0 ~ 1）、Axis12（0 ~ 1）|Axis5（-1 ~ 1）, 常驻-1|

[InputSystem介绍]:https://docs.unity3d.com/cn/current/Manual/com.unity.inputsystem.html
[InputSystem手册]:https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/QuickStartGuide.html