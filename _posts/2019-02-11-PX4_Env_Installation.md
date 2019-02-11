---
layout: post
title: PX4 리눅스 개발환경 설치
date: 2019-02-11 20:40:00 +0900
description: PX4 리눅스 개발환경 설치
img: ros_robot.jpg # Add image post (optional)
tags: [PX4,Gazebo] # add tag
---

# 개발환경 설치하기
먼저, Tool Chain을 설치합니다.   
* 참고사이트 : https://dev.px4.io/en/setup/dev_env_linux.html   

설치하기 위해서 사용자 권한을 설정합니다.   
`sudo usermod -a -G dialout $USER`   
dialout은 권한을 모두 무시하라는 의미입니다.   
Log-out 후 다시 Log-in을 하면 권한이 반영됩니다.   

# Pixhawk/NuttX (and jMAVSim)을 설치하기
먼저, ubuntu_sim_nuttx.sh 파일을 다운로드한다.    
주소 : https://raw.githubusercontent.com/PX4/Devguide/master/build_scripts/ubuntu_sim_nuttx.sh    
다운로드가 안될 경우 내용을 복사해서 파일을 저장한다.   

스크립트를 실행한다.   
`source ubuntu_sim_nuttx.sh`   

컴퓨터를 재실행한다.   

