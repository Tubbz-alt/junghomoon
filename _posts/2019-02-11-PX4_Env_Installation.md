---
layout: post
title: PX4 리눅스 개발환경 설치
date: 2019-02-11 20:40:00 +0900
description: PX4 리눅스 개발환경 설치
img: ros_robot.jpg # Add image post (optional)
tags: [PX4,Gazebo] # add tag
---

# 개발환경 설치하기
## 툴-체인 설치하기   
먼저, Tool Chain을 설치합니다.   
* 참고사이트 : https://dev.px4.io/en/setup/dev_env_linux.html   

설치하기 위해서 사용자 권한을 설정합니다.   
`sudo usermod -a -G dialout $USER`   
dialout은 권한을 모두 무시하라는 의미입니다.   
Log-out 후 다시 Log-in을 하면 권한이 반영됩니다.   

## Pixhawk/NuttX (and jMAVSim)을 설치하기
먼저, ubuntu_sim_nuttx.sh 파일을 다운로드한다.    
주소 : https://raw.githubusercontent.com/PX4/Devguide/master/build_scripts/ubuntu_sim_nuttx.sh    
다운로드가 안될 경우 내용을 복사해서 파일을 저장한다.   

스크립트를 실행한다.   
`source ubuntu_sim_nuttx.sh`   

컴퓨터를 재실행한다.   

# 코드 빌드하기   
## PX4 소스코드 다운로드하기   
1. Github에서 로그인한다.   
2. Firmware repository에서 Fork 버튼을 눌러 본인 계정으로 복사한다.   
3. Repository URL을 복사한다.   
4. 복사한 URL을 git으로 clone한다.   
`git clone https://github.com/<youraccountname>/Firmware.git`   

## jMAVSim Simulator 실행하기   
Firmware 폴더 내에서 jMAVSim을 실행한다.   
`~/Firmware$ make px4_sitl jmavsim`   

프로그램이 실행되면, 이륙을 시켜본다.   
`pxh>commander takeoff`   

바로 이륙이 안될 때는 잠시 후 다시 실행해 본다.   

## QGCS를 실행하기
QGCS를 실행하면 자동으로 jMAVSim 드론이 인식된다.   
Take-off 버튼을 누르면 중앙 하단에 안전을 위한 명령 바가 나타나고 이를 오른쪽으로 움직이면 이륙을 시작한다.   
지도상에서 원하는 위치를 더블 클릭해 'goto location' 또는 'orbit at location' 메뉴를 선택하면 무인기가 해당 위치로 비행한다.     

## jMAVSim 대신 Gazebo 사용하기   
Gazebo를 실행할 때는 아래와 같이 명령을 실행한다.   
`make px4_sitl gazebo`   

## 소스코드 빌드하기     
하드웨어에 따라 빌드 명령이 다르며, Pixhawk1 기준으로 다음과 같이 명령한다.   
`cd Firmware`
`make px4_fmu-v2_default`   

## 펌웨어 업로드(Flashing) 하기   
Pixhawk을 USB로 연결한 후 아래와 같이 실행한다.   
`make px4_fmu-v2_default upload`   

Pixhakw 멜로디와 함께 업로드가 완료된다.   

다음부터는 IDE  



