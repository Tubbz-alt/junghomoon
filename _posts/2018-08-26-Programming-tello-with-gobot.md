---
layout: post
title: gobot으로 DJI Tello 드론 프로그램하기  
date: 2018-08-26 18:00:00 +0900
description: Gobot으로 DJI Tello 드론 프로그램하기
img: DJI-Tello.jpg # Add image post (optional)
tags: [Software,DJI,Tello,Scratch,Programming,Gobot,Golang] # add tag
---

# Gobot으로 DJI Tello 드론 프로그램하기   

*참고 사이트 : https://github.com/hybridgroup/gobot   

## 1. go 개발환경을 설치한다.    
   1) Linux용 설치 프로그램을 다운로드한다.   
   | 사이트 : https://golang.org/dl/
   2) 압축파일을 /usr/local 폴더로 압축을 해제한다.     
      `sudo tar -C /usr/local -xzf go1.11.linux-amd64.tar.gz`   
   3) /usr/local/go 폴더 트리를 만든다.    
   3) 프로파일에 PATH를 추가한다.   
      HOME에서 `vi .profile` 를 실행한다.   
      *주의 : .profile은 숨겨져있으므로, `ls -a` 명령어로 볼 수 있음.   
      파일의 가장 아래쪽에 아래와 같이 경로를 추가한다.   
      `export PATH=$PATH:/usr/local/go/bin`   
      `export GOPATH=$HOME/go`   
      *참고 : vi명령어 a를 눌러 편집모드로 전환하고 :wq 로 저장하면 된다.
      
   4) 프로파일 적용을 위해 리눅스를 재부팅한다.   
   
## 2. go 개발환경이 정상적으로 설치되었는지 테스트해본다.
   1) Create your workspace directory, $HOME/go.   
   2) Make the directory src/hello inside your workspace, and in that directory create a file named hello.go that looks like:
   3) hello.go 파일의 내용을 아래와 같이 수정한다. 
<pre>
package main
import "fmt"
func main() {
	fmt.Printf("hello, world\n")
}
</pre>   

4) go Tool을 빌드한다.   
`$ cd $HOME/go/src/hello`   
`$ go build`   

5) 빌드되고 아래와 같이 실행하면, hello, world가 나타나면 정상적으로 설치 된 것이다.   
`$ ./hello`   
`hello, world`   

## 3. gobot 프로그램을 설치한다.   
*참고사이트 : https://gobot.io/documentation/getting-started/   
 `$ go get -d -u gobot.io/x/gobot/...`
 
## 4. 비행해보기
*참고사이트 : https://gobot.io/blog/2018/04/20/hello-tello-hacking-drones-with-go/   
지금부터 텔로 프로그램을 해보자.
1. 가장 먼저, go 스크립트를 포함할 폴더를 아래와 같은 경로가 되도록 생성한다. (제조사/제품명)   
   go 스크립트는 폴더별로 나 
`~/go/src/dji/tello`    

2. tello.go 파일을 생성해 아래 코드를 붙여넣기한 후 저장한다.   

<code>
  package main
  import (
      "time"   #"fmt"는 삭제해야 함.
      "gobot.io/x/gobot"
      "gobot.io/x/gobot/platforms/dji/tello"
  )
  func main() {
      drone := tello.NewDriver("8888")
      work := func() {
          drone.TakeOff()
          gobot.After(5*time.Second, func() {
              drone.Land()
          })
      }
      robot := gobot.NewRobot("tello",
          []gobot.Connection{},
          []gobot.Device{drone},
          work,
      )
      robot.Start()
  }
</code>

3. go 스크립트를 빌드한다.   
`$ cd $HOME/go/src/dji/tello`    
`$ go build`    

4. 프로그램을 실행한다.   
`$ ./tello`   

## 5. 영상받아보기
참고사이트 :  https://gobot.io/blog/2018/04/20/hello-tello-hacking-drones-with-go/   
   
## mplayer 설치 방법

   `sudo apt-get install mplayer`   
   
