# gobot으로 DJI Tello 드론 프로그램하기   

참고 사이트 : https://github.com/hybridgroup/gobot   

1. go 개발환경을 설치한다.    
   1) Linux 프로그램을 다운로드한다.   
   | 사이트 : https://golang.org/dl/
   2) Download the archive and extract it into /usr/local, creating a Go tree in /usr/local/go.   
      `sudo tar -C /usr/local -xzf go1.11.linux-amd64.tar.gz`
   3) PATH를 추가한다.   
   Add /usr/local/go/bin to the PATH environment variable. You can do this by adding this line to your /etc/profile (for a system-wide installation) or $HOME/.profile:
`export PATH=$PATH:/usr/local/go/bin`
   4) 프로파일 적용을 위해 리눅스를 재부팅한다.   
   
2. go 개발환경이 정상적으로 설치되었는지 테스트해본다.
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

2. gobot 프로그램을 설치한다.   
 
   
