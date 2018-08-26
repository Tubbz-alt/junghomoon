# gobot으로 DJI Tello 드론 프로그램하기   

참고 사이트 : https://github.com/hybridgroup/gobot   

## 1. go 개발환경을 설치한다.    
   1) Linux용 설치 프로그램을 다운로드한다.   
   | 사이트 : https://golang.org/dl/
   2) 압축파일을 /usr/local 폴더로 압축을 해제한다.     
      `sudo tar -C /usr/local -xzf go1.11.linux-amd64.tar.gz`   
   3) /usr/local/go 폴더 트리를 만든다.    
   3) 프로파일에 PATH를 추가한다.   
      HOME에서 `vi /.profile` 를 실행한다.   
      가장 아래쪽에 경로를 추가한다.   
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
 
## 4. 비행해보기

## 5. 영상받아보기
참고사이트 :  https://gobot.io/blog/2018/04/20/hello-tello-hacking-drones-with-go/   
   
## mplayer 설치 방법

   `sudo apt-get install mplayer`   
   
