
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
