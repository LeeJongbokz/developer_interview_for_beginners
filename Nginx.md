# Nginx
<br>


### 런타임에 Nginx 프로세스를 컨트롤 한다는 것이 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://docs.nginx.com/nginx/admin-guide/basic-functionality/runtime-control/] 
   
+ 트래픽을 핸들링하는 Nginx 프로세스와 그것을 런타임에 어떻게 컨트롤하는지 이해해봅니다. <br> 
  이 섹션은 Nginx가 런타임에 시작하는 프로세스와, 그것들을 어떻게 컨트롤할지를 묘사합니다. <br> 
</details>

-----------------------

### 마스터 프로세스와 워커 프로세스란 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://docs.nginx.com/nginx/admin-guide/basic-functionality/runtime-control/] 
   
+ Nginx는 하나의 마스터 프로세스와 하나 혹은 그 이상의 워커 프로세스들을 갖고 있습니다. <br> 
  만약 캐싱이 가능하다면, 캐시 로더와 캐시 매니저 프로세스가 또한 시작할 때 실행됩니다. <br> 
  
  마스터 프로세스의 주목적은 설정 파일을 읽고 평가하는 것과, 워커 프로세스들을 유지하는 것입니다. <br> 
  
  워커 프로세스는 요청에 대한 실제 작업을 수행합니다. <br> 
  Nginx는 OS 의존적인 메커니즘에 의존해, 요청을 워커 프로세스간에 효율적으로 분산합니다. <br> 
  워커 프로세스의 수는 nginx.conf 설정 파일의 worker_processes 지시에 정의되어 있고, <br>
  고정된 숫자로 정해져 있거나, 가능한 CPU 코어의 수에 자동으로 조정되도록 설정됩니다. <br> 
</details>

-----------------------

### Nginx를 제어한다는 것이 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://docs.nginx.com/nginx/admin-guide/basic-functionality/runtime-control/] 
   
+ 설정을 리로딩하기 위해서는, 당신은 Nginx를 중단하거나 재시작하거나, 혹은 마스터 프로세스에 <br>
  시그널을 보낼 수 있습니다. <br> 
  시그널은 -s 인자와 같이 nginx 커맨드를 실행함으로써 보내질 수 있습니다. <br> 
  
  ```
  nginx -s <SIGNAL>
  ```
  <SIGNAL>은 아래 중에 하나에 속할 수 있습니다. 
  - quit: 우아하게 셧 다운 합니다. <br> 
  - reload: 설정 파일을 리로딩 합니다. <br> 
  - reopen: 로그 파일을 다시 엽니다. <br> 
  - stop: 바로 중단시킵니다. <br> 
    
  kill 기능은 또한 마스터 프로세스에 시그널을 직접적으로 보내는데 사용될 수 있습니다. <br> 
  마스터 프로세스의 프로세스 ID는 기본으로 nginx.pid 파일에 쓰여지는데, <br>
  그것은 /usr/local/nginx/logs 혹은 /var/run 디렉토리에 위치합니다. <br> 
</details>

-----------------------
