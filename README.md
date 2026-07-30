프로젝트 개요
0. 실행환경
OS	UBUNTU 22.04 && MACOS SEQUOIA 15.7.4

SHELL	BASH && ZSH

DOCKER	29.4.0

GIT	2.53.0	

1. 기술문서작성

2. terminal, docker, git의 사용법을 숙지하고 소계 미션목표에 해당하는 내용들을 기록.

2-1.실행환경점검(os/쉘/터미널, docker버전, git 버전)
2-2.수행항목 체크리스트(터미널/권한/docker/dockerfile/포트/볼륨/git/github)
2-3.검증방법+결과 위치 링크
2-4.트러블슈팅 2건이상(문제-원인/가설-확인-해결)
2-5 전체 내용은 현재파일의 내용으로 이해할수있게 정리.

3. 터미널 수행결과의 목록정리

3-1. 터미널의 명령어 사용과 출력결과는 아래에 정리.
정리된것은 미션에 요구한 현재위치확인, 	목록확인(숨김파일포함), 이동,생성,복사,이동/이름변경,삭제
파일 내용확인,빈 파일생성 순임.

```
pwd
```

현재 경로를 확인하는 명령어.
//개인정보 마스킹으로 유저네임대신 appuser로대체
출력결과
```
/Users/appuser
```

```
ls -al
```

목록을 확인하는 ls 명령어.
-a는 숨김파일을 포함한 전체, -l은 long list format으로 전체 내용을 긴포맷으로 출력하는 옵션.

출력결과

```
total 72
drwxr-x---+ 25 bs7703113025  bs7703113025   800  7 30 13:50 .
drwxr-xr-x   7 root          admin          224  7 30 11:57 ..
-r--------   1 bs7703113025  bs7703113025     8  7 30 11:57 .CFUserTextEncoding
drwxr-xr-x   8 bs7703113025  bs7703113025   256  7 30 12:58 .docker
-rw-r--r--@  1 bs7703113025  bs7703113025  6148  7 30 12:41 .DS_Store
drwx------  10 bs7703113025  bs7703113025   320  7 30 12:07 .orbstack
drwxr-xr-x   3 bs7703113025  bs7703113025    96  7 30 12:07 .ssh
drwx------+  2 bs7703113025  bs7703113025    64  7 30 11:58 .Trash
-rw-------   1 bs7703113025  bs7703113025  7033  7 30 13:50 .viminfo
drwxr-xr-x   3 bs7703113025  bs7703113025    96  7 30 11:58 .vscode
drwx------   3 bs7703113025  bs7703113025    96  7 30 12:04 .zsh_sessions
drwxr-xr-x   4 bs7703113025  bs7703113025   128  7 30 13:39 app
drwx------+  3 bs7703113025  bs7703113025    96  7 30 11:57 Desktop
-rw-r--r--   1 bs7703113025  bs7703113025    74  7 30 13:00 Dockerfile
drwx------+  3 bs7703113025  bs7703113025    96  7 30 11:57 Documents
drwx------+  4 bs7703113025  bs7703113025   128  7 30 12:03 Downloads
-rw-r--r--   1 bs7703113025  bs7703113025   229  7 30 13:50 file1
drwx------@ 76 bs7703113025  bs7703113025  2432  7 30 12:06 Library
drwx------   3 bs7703113025  bs7703113025    96  7 30 11:57 Movies
drwx------+  3 bs7703113025  bs7703113025    96  7 30 11:57 Music
-rw-r--r--   1 bs7703113025  bs7703113025    11  7 30 13:47 newfile
drwx------   4 bs7703113025  bs7703113025   160  7 30 12:07 OrbStack
drwx------+  4 bs7703113025  bs7703113025   128  7 30 11:58 Pictures
drwxr-xr-x+  4 bs7703113025  bs7703113025   128  7 30 11:57 Public
-rw-r--r--   1 bs7703113025  bs7703113025   498  7 30 13:28 README.md
```

```
cd ../
```

cd는 지정한 경로로 이동하는 명령어.
지정한 경로는 .현재경로 ../ 상위디렉토리로 즉 현재경로의 상위디렉토리로 이동.

출력결과

성공시 없음.

```
touch newfile
```

touch 명령어는 지정한 이름의 파일을 생성하거나 시간과 날짜를 수정하는 명령어.

출력결과

성공시 없음.

```
cp newfile newfile1
```

cp 명령어는 지정한 인자1을 인자2로 복사하는 명령어.

출력결과

성공시 없음.

```
mv newfile app/newfile1
```

mv 명령어는 인자1을 인자2로 이동시키는 명령어.

출력결과

성공시 없음.

```
rm -rf newfile
```

rm은 파일 또는 디렉토리를 삭제하는 명령어.
-r은 하위디렉토리 전체를, -f는 묻지않고 강제로 삭제하는 옵션.

출력결과

성공시 없음.

```
cat newfile
```
cat은 지정한 파일의 내용을 출력하는 명령어

출력결과

```
hello world
```

```
touch newfile
```

touch는 앞서사용한것처럼 빈파일을 생성할때도 쓰는명령어

출력결과

성공시 없음.

3-2.권한 실습및 증거기록 항목.
권한 확인/변경하는 명령을 최소 한개의 파일과 디렉토리에 실행후 실행전후를 아래에 기록.


chmod 파일/디렉토리 실행전 ls -al의 실행결과

```
total 16
drwxr-xr-x   7 bs7703113025  bs7703113025   224  7 30 14:01 .
drwxr-x---+ 24 bs7703113025  bs7703113025   768  7 30 13:59 ..
-rw-r--r--   1 bs7703113025  bs7703113025  2995  7 30 13:57 file1
-rw-r--r--   1 bs7703113025  bs7703113025     0  7 30 14:01 file2
drwxr-xr-x   2 bs7703113025  bs7703113025    64  7 30 14:00 newdir
-rw-r--r--   1 bs7703113025  bs7703113025     0  7 30 14:00 newfile
-rw-r--r--   1 bs7703113025  bs7703113025   805  7 30 13:59 README.md
```

chmod 700을 newfile에 씌워준후 ls -al의 실행결과

```
chmod 700 newfile
```

```
total 24
drwxr-xr-x   7 bs7703113025  bs7703113025   224  7 30 14:01 .
drwxr-x---+ 24 bs7703113025  bs7703113025   768  7 30 14:01 ..
-rw-r--r--   1 bs7703113025  bs7703113025  2995  7 30 13:57 file1
-rw-r--r--   1 bs7703113025  bs7703113025   531  7 30 14:01 file2
drwxr-xr-x   2 bs7703113025  bs7703113025    64  7 30 14:00 newdir
-rwx------   1 bs7703113025  bs7703113025     0  7 30 14:00 newfile
-rw-r--r--   1 bs7703113025  bs7703113025   805  7 30 13:59 README.md
```

chmod 764을 newdir에 씌워준후 ls -al의 실행결과

```
chmod 764 newdir
```

```
total 24
drwxr-xr-x   7 bs7703113025  bs7703113025   224  7 30 14:02 .
drwxr-x---+ 24 bs7703113025  bs7703113025   768  7 30 14:02 ..
-rw-r--r--   1 bs7703113025  bs7703113025  2995  7 30 13:57 file1
-rw-r--r--   1 bs7703113025  bs7703113025  1063  7 30 14:02 file2
drwxrw-r--   2 bs7703113025  bs7703113025    64  7 30 14:00 newdir
-rwx------   1 bs7703113025  bs7703113025     0  7 30 14:00 newfile
-rw-r--r--   1 bs7703113025  bs7703113025   805  7 30 13:59 README.md
```

rwx 각각 421순의 값을 지니며 각값의 합산으로 비트값을 정함.
read,write,execute순

이때 xxx순의 숫자합계에 맨앞에는 유저,그다음에는 그륩,마지막에는 other가지닐권한의 값을 표시함.
ls에 표시되는 맨앞의d는 파일이냐 디렉토리냐를 의미.

4. docker 관련한 실행과 관련항목 점검

4-1.docker 설치및 기본점검.
-docker 버전확인결과를기록.
-docker 데몬동작확인결과를 기록.

```
docker --version
```

```
docker version 29.4.0, build 9d7ad9f
```

```
docker info
```

```
Client:
 Version:    29.4.0
 Context:    orbstack
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.33.0
    Path:     /Users/bs7703113025/.docker/cli-plugins/docker-buildx
  compose: Docker Compose (Docker Inc.)
    Version:  v5.1.2
    Path:     /Users/bs7703113025/.docker/cli-plugins/docker-compose

Server:
 Containers: 6
  Running: 2
  Paused: 0
  Stopped: 4
 Images: 3
 Server Version: 29.4.0
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 301b2dac98f15c27117da5c8af12118a041a31d9
 runc version: c241c0bb5e60a8e8c1b2e53d4eca8d0068d8d57e
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 7.0.11-orbstack-00360-gc9bc4d96ac70
 Operating System: OrbStack
 OSType: linux
 Architecture: x86_64
 CPUs: 6
 Total Memory: 15.69GiB
 Name: orbstack
 ID: 38764614-637d-485f-9634-2bf40ad38aaf
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http://proxy.orb.internal:8305
 HTTPS Proxy: http://proxy.orb.internal:8305
 No Proxy: localhost,127.0.0.1,127.0.0.0/8,::1,10.0.0.0/8,172.16.0.0/12,192.168.0.0/16,0.250.250.0/24,*.orb.internal,*.local,gateway.docker.internal,host.internal,host.docker.internal,host.lima.internal,docker.for.mac.localhost,docker.for.mac.host.internal
 Experimental: true
 Insecure Registries:
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false
 Product License: Community Engine
 Default Address Pools:
   Base: 192.168.97.0/24, Size: 24
   Base: 192.168.107.0/24, Size: 24
   Base: 192.168.117.0/24, Size: 24
   Base: 192.168.147.0/24, Size: 24
   Base: 192.168.148.0/24, Size: 24
   Base: 192.168.155.0/24, Size: 24
   Base: 192.168.156.0/24, Size: 24
   Base: 192.168.158.0/24, Size: 24
   Base: 192.168.163.0/24, Size: 24
   Base: 192.168.164.0/24, Size: 24
   Base: 192.168.165.0/24, Size: 24
   Base: 192.168.166.0/24, Size: 24
   Base: 192.168.167.0/24, Size: 24
   Base: 192.168.171.0/24, Size: 24
   Base: 192.168.172.0/24, Size: 24
   Base: 192.168.181.0/24, Size: 24
   Base: 192.168.183.0/24, Size: 24
   Base: 192.168.186.0/24, Size: 24
   Base: 192.168.207.0/24, Size: 24
   Base: 192.168.214.0/24, Size: 24
   Base: 192.168.215.0/24, Size: 24
   Base: 192.168.216.0/24, Size: 24
   Base: 192.168.223.0/24, Size: 24
   Base: 192.168.227.0/24, Size: 24
   Base: 192.168.228.0/24, Size: 24
   Base: 192.168.229.0/24, Size: 24
   Base: 192.168.237.0/24, Size: 24
   Base: 192.168.239.0/24, Size: 24
   Base: 192.168.242.0/24, Size: 24
   Base: 192.168.247.0/24, Size: 24
   Base: fd07:b51a:cc66:d000::/56, Size: 64
 Firewall Backend: iptables
```

4-2.docker 기본명령 수행 결과확인.
-이미지/다운로드 목록확인 docker images
-컨테이너:실행/중지/목록확인 docker ps -a
-운영:로그 확인 docker logs / docker stats


```
docker images
```

```
IMAGE           ID             DISK USAGE   CONTENT SIZE   EXTRA
my_web:latest   abc986373555       93.9MB         26.1MB   U    
nginx:latest    5a88c9c45479        240MB           66MB   U    
ubuntu:latest   3131b4cc82a7        159MB         45.3MB   U
```

```
docker ps -a
```  

```
CONTAINER ID   IMAGE     COMMAND                   CREATED             STATUS                   PORTS                                     NAMES
c82c6cff3e63   nginx     "/docker-entrypoint.…"   About an hour ago   Up About an hour         0.0.0.0:8081->80/tcp, [::]:8081->80/tcp   bind-test
cbc835bc116a   my_web    "/docker-entrypoint.…"   2 hours ago         Up 2 hours               0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   web
00a78548c703   ubuntu    "bash"                    2 hours ago         Exited (0) 2 hours ago                                             sharp_davinci
4367c19f3a55   ubuntu    "-it bash"                2 hours ago         Created                                                            my_ubuntu
f827bb8b4666   nginx     "/docker-entrypoint.…"   2 hours ago         Exited (0) 2 hours ago                                             my_nginx
ed3671729735   ubuntu    "/bin/bash"               2 hours ago         Exited (0) 2 hours ago                                             practical_heyrovsky
```

```
docker logs bind-test
```

```
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
192.168.215.1 - - [30/Jul/2026:04:09:22 +0000] "GET / HTTP/1.1" 200 32 "-" "curl/8.7.1" "-"
192.168.215.1 - - [30/Jul/2026:04:09:34 +0000] "GET / HTTP/1.1" 200 32 "-" "curl/8.7.1" "-"
```

```
docker stats
```

```
CONTAINER ID   NAME        CPU %     MEM USAGE / LIMIT     MEM %     NET I/O           BLOCK I/O         PIDS
c82c6cff3e63   bind-test   0.00%     5.789MiB / 15.69GiB   0.04%     2.08kB / 1.42kB   16.8MB / 8.19kB   7
cbc835bc116a   web         0.00%     5.945MiB / 15.69GiB   0.04%     2.56kB / 1.5kB    12.5MB / 8.19kB   7
```

4-3.컨테이너 실행연습
-hello-world 실행 성공을 기록
-ubuntu 컨테이너를 실행후 내부에서 간단한명령어를 실행후 수행결과를 기록
-컨테이너 종료 유지(attach/exec)의 차이를 스스로 관찰하고 간단히 정리


```
docker run hello-world
```

```
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

```
root@5ff9446856d1:/# ls
```

```
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
```

```
root@5ff9446856d1:/# echo my
```

```
my
```


4-4.기존DOCKERFILE기반 커스텀 이미지제작

컨테이너 종료/유지에대해 attach는 기존 컨테이너의 메인프로세서에
내터미널을 직접연결해, 해당프로세서가 종료되면 꺼지는것이고
exec은 컨테이너안에 새로운 프로세서를 생성해 연결되, 메인프로세서가유지되어 꺼져도, 메인프로세서가남아
프로그램이 완전히 종료되지않음.

사용한 베이스 이미지는, 리눅스 우분투.
내가 적용한 베이스 커스텀 포인트 요약.
환경변수(env)는 앱홈 즉 작업폴더가될 환경변수와 타임존.
실행명령(RUN)은 apt-get사용해 기본적인 프로그램설치와 최적화를 적용.
작업폴더(WORKDIR)를 지정함으로써 작업해야할 파일을지정
복사(COPY)로 기존의 커맨드에서 필요한 파일들을 복사
유저&그륩(user&group)설정으로 필요한권한과 유저/그륩을 설정.
포트지정(EXPOSE)설정으로 사용할포트를 지정.
마지막으로 HEALTHCHECK로 해당 도커파일이 시작후n초후 m초주기로 기본 포트의 접속을n회 확인해 확인되지않으면종료되도록 설정.
CMD설정으로 프로세스 시작시 실행될 프로그램과 베이스 프로그램을 설정.

```
docker build -t my-custom-image .
```

```
[+] Building 7.9s (10/10) FINISHED                                                                                                                                                 docker:orbstack
 => [internal] load build definition from dockerfile                                                                                                                                          0.1s
 => => transferring dockerfile: 667B                                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/library/ubuntu:22.04                                                                                                                               0.8s
 => [internal] load .dockerignore                                                                                                                                                             0.1s
 => => transferring context: 2B                                                                                                                                                               0.0s
 => [1/5] FROM docker.io/library/ubuntu:22.04@sha256:0e0a0fc6d18feda9db1590da249ac93e8d5abfea8f4c3c0c849ce512b5ef8982                                                                         0.2s
 => => resolve docker.io/library/ubuntu:22.04@sha256:0e0a0fc6d18feda9db1590da249ac93e8d5abfea8f4c3c0c849ce512b5ef8982                                                                         0.2s
 => [internal] load build context                                                                                                                                                             0.1s
 => => transferring context: 5.52kB                                                                                                                                                           0.0s
 => CACHED [2/5] RUN  APT-GET update &&   apt-get install -y --no-install-recommends   curl   vim   python3 &&   rm -rf /var/lib/apt/lists/*                                                  0.0s
 => [3/5] RUN  GROUPADD -r appgroup &&   useradd -r -g appgroup appuser &&   mkdir -p /app &&   chown -R appuser:appgroup /app                                                                0.5s
 => [4/5] WORKDIR  /APP                                                                                                                                                                       0.3s
 => [5/5] COPY  --CHOWN=APPUSER:APPGROUP . .                                                                                                                                                  0.3s
 => exporting to image                                                                                                                                                                        5.2s
 => => exporting layers                                                                                                                                                                       3.8s
 => => exporting manifest sha256:4fd930c27bb7dffb6bada291b1459779568513cf5ce9ea40b1288c5bf3a2e665                                                                                             0.1s
 => => exporting config sha256:6f223c29c9ab6f654e9357668bae3f28f90f339e2bd20afdfce7d82e41852f46                                                                                               0.0s
 => => exporting attestation manifest sha256:e9c43d496aa4609ca0175b6c0e56f10033861593a03827895e286e7a23fa8730                                                                                 0.1s
 => => exporting manifest list sha256:48e9f684681b4f927c19b7652fc76a343f38879a1472136f5c290a78f2bb4d5b                                                                                        0.1s
 => => naming to docker.io/library/my-custom-image:latest                                                                                                                                     0.0s
 => => unpacking to docker.io/library/my-custom-image:latest                                                                                                                                  1.0s

 1 warning found (use docker --debug to expand):
 - JSONArgsRecommended: JSON arguments recommended for CMD to prevent unintended behavior related to OS signals (line 32)
```

```
docker run -it --name test my-custom-image bash
```

```
appuser@f4da9c4188e0:/app$ curl
```

```
curl: try 'curl --help' or 'curl --manual' for more information
```

```
appuser@f4da9c4188e0:/app$ python3
```

```
Python 3.10.12 (main, Jun 22 2026, 18:55:27) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
```

```
appuser@f4da9c4188e0:/app$ ls -al
total 28
drwxr-xr-x 1 appuser appgroup    92 Jul 30 06:30 .
drwxr-xr-x 1 root    root         6 Jul 30 06:47 ..
-rw-r--r-- 1 appuser appgroup 13856 Jul 30 06:01 README.md
drwxr-xr-x 1 appuser appgroup     0 Jul 30 05:49 app
-rw-r--r-- 1 appuser appgroup   628 Jul 30 06:28 dockerfile
drwxr-xr-x 1 appuser appgroup    50 Jul 30 06:02 docs
-rw-r--r-- 1 appuser appgroup     0 Jul 30 06:31 file6
-rw-r--r-- 1 appuser appgroup  4579 Jul 30 06:29 troubleshoot.md
```

```
appuser@f4da9c4188e0:/app$ exit
```

```
exit
```

4-5. 포트매핑 증거 첨부.

```
docker run -d --name my_nginx -p 8080:80 nginx
```

```
ffeab556bb53ed8c2b79d1f2e1bbc82a5f27ecc82ca547fbbcafde54e8fd2de2
```

```
curl http://localhost:8080 
```

```
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, nginx is successfully installed and working.
Further configuration is required for the web server, reverse proxy, 
API gateway, load balancer, content cache, or other features.</p>

<p>For online documentation and support please refer to
<a href="https://nginx.org/">nginx.org</a>.<br/>
To engage with the community please visit
<a href="https://community.nginx.org/">community.nginx.org</a>.<br/>
For enterprise grade support, professional services, additional 
security features and capabilities please refer to
<a href="https://f5.com/nginx">f5.com/nginx</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

4-6. docker 볼륨 영속성 검증

```
bs7703113025@c3r5s5 submit % docker volume create my_volume
```

```
my_volume
```

```
bs7703113025@c3r5s5 submit % docker run -it --name test -v my_volume:/data ubuntu
```

```
root@db4ca61d5960:/# cd data
```

```
root@db4ca61d5960:/data# echo "hello" >> hello.txt
```

```
root@db4ca61d5960:/data# ls -al
```

```
total 4
drwxr-xr-x 1 root root 18 Jul 30 07:37 .
drwxr-xr-x 1 root root 14 Jul 30 07:37 ..
-rw-r--r-- 1 root root  6 Jul 30 07:37 hello.txt
```

```
root@db4ca61d5960:/data# cat hello.txt
```

```
hello
```

```
root@db4ca61d5960:/data# exit
```

```
exit
```

```
bs7703113025@c3r5s5 submit % docker rm test
```

```
test
```

```
bs7703113025@c3r5s5 submit % docker run -it --name test0 -v my_volume:/data ubuntu
```

```
root@8974dccb686f:/# cd data
```

```
root@8974dccb686f:/data# ls -al
```

```
total 4
drwxr-xr-x 1 root root 18 Jul 30 07:37 .
drwxr-xr-x 1 root root 14 Jul 30 07:38 ..
-rw-r--r-- 1 root root  6 Jul 30 07:37 hello.txt
```

```
root@8974dccb686f:/data# cat hello.txt
```

```
hello
```

```
root@8974dccb686f:/data# exit
```

```
exit
```
5.git설정 및 github연동

git config파일확인

```
git config --list
```

```
credential.helper=osxkeychain
user.name=**
user.email=**@gmail.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=git@github.com:**/repo.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main
```
git 로그인및 저장소연동확인

```
git remote -v
```

```
git remote -v
```

```
origin	git@github.com:bs7703/repo.git (fetch)
origin	git@github.com:bs7703/repo.git (push)
```

```
git push            
```

```
오브젝트 나열하는 중: 5, 완료.
오브젝트 개수 세는 중: 100% (5/5), 완료.
Delta compression using up to 6 threads
오브젝트 압축하는 중: 100% (3/3), 완료.
오브젝트 쓰는 중: 100% (3/3), 803 bytes | 803.00 KiB/s, 완료.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:bs7703/repo.git
   6b7b86d..9e6c437  main -> main
```

docs에 웹사이트 스크린샷 참조

6. 트러블슈팅과 문제해결

apt-get install을 배시에서실행시 해당오류가 떳는데,

```
root@d188c02ce2f4:/# apt-get install -y --no-install-recommends curl vim python3 ca-certifications
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package curl
E: Unable to locate package vim
E: Unable to locate package python3
E: Unable to locate package ca-certifications
```

확인해보니, 명령어입력전 apt-get update로 최신화를 해주지않아 생긴문제라 앞 명령어에 apt-get update &&를 붙인후 재실행함.

docker build시 나타난 오류.

```
bs7703113025@c3r5s5 submit % docker build -t my-custom-image .          
[+] Building 25.2s (7/9)                                                                                                                                                           docker:orbstack
 => [internal] load build definition from dockerfile                                                                                                                                          0.1s
 => => transferring dockerfile: 621B                                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/library/ubuntu:22.04                                                                                                                               1.1s
 => [internal] load .dockerignore                                                                                                                                                             0.1s
 => => transferring context: 2B                                                                                                                                                               0.0s
 => CACHED [1/5] FROM docker.io/library/ubuntu:22.04@sha256:0e0a0fc6d18feda9db1590da249ac93e8d5abfea8f4c3c0c849ce512b5ef8982                                                                  0.2s
 => => resolve docker.io/library/ubuntu:22.04@sha256:0e0a0fc6d18feda9db1590da249ac93e8d5abfea8f4c3c0c849ce512b5ef8982                                                                         0.2s
 => [internal] load build context                                                                                                                                                             0.2s
 => => transferring context: 27.64kB                                                                                                                                                          0.0s
 => [2/5] RUN  APT-GET update &&   apt-get install -y --no-install-recommends   curl   vim   python3 &&   rm -rf /var/lib/apt/lists/*                                                        23.1s
 => ERROR [3/5] RUN  GROUPADD -r addgroup &&   useradd -r -g appgroup appuser &&   mkdir -p /app &&   chown -R appuser:appgroup /app                                                          0.5s 
------                                                                                                                                                                                             
 > [3/5] RUN            GROUPADD -r addgroup &&                 useradd -r -g appgroup appuser &&               mkdir -p /app &&                chown -R appuser:appgroup /app:                    
0.408 useradd: group 'appgroup' does not exist                                                                                                                                                     
------                                                                                                                                                                                             
dockerfile:16                                                                                                                                                                                      
--------------------
  15 |     
  16 | >>> RUN		groupadd -r addgroup && \
  17 | >>> 		useradd -r -g appgroup appuser && \
  18 | >>> 		mkdir -p $APP_HOME && \
  19 | >>> 		chown -R appuser:appgroup $APP_HOME
  20 |     
--------------------
ERROR: failed to build: failed to solve: process "/bin/sh -c groupadd -r addgroup && \t\tuseradd -r -g appgroup appuser && \t\tmkdir -p $APP_HOME && \t\tchown -R appuser:appgroup $APP_HOME" did not complete successfully: exit code: 6
```

단순히 addgroup의 이름을 appgroup으로 하지않아서 발생한 오류
