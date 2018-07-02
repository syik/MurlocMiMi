### 命令工具
docker 基本的管理工具，用来处理基本的命令操作
docker-compose 自动化工具，可以看做CI
docker-machine 管理远程docker
docker-credential-osxkechain 把docker使用的证书保存到OS X 的 keychain

### docker 命令
由于 docker 的核心就是把一个个 docker 容器当自己拥有整个系统一样，实际上相当于每个 docker 就是一个进程，所以管理 docker 一般使用 docker ps & inspect 工具
```sh
docker run ubuntu:latest ls -l # ls -l 代表下载
docker ps
docker ps -a
docker images
docker run
docker inspect  # 会返回当前容器的 JSON 配置表
docker inspect ContainerID | jq -r ".[0].NetworkSettings.SandboxID"
docker rm
docker rm $(docker ps -a -q)  #清空所有
docker run --rm ubuntu:latest ls -l
exit
docker start  # 恢复已结束的容器
```

### 出现 unauthorized: incorrect username or password
docker login # Username (wanliming11@gmail.com): wanliming
psd: 198simple

### 查询
```
docker inspect -f {{.NetworkSettings.IPAddress}} 47866fb6b092 #查看 ip 地址
```

### 本地文件系统与容器内的文件通信
```sh
docker run -i -t ubuntu:latest bash  # -i interactive -t tty, 然后会产生一个本地的bash，相当于操作本地的bash一样 
docker run -it -p 8080:80 -v /Users/wanliming/Library/Mobile\ Documents/com~apple~CloudDocs/MurlocInformations/Docker/tmp/web:/var/www/html ubuntu:latest bash  #这样就把iCLoud里面的文件同docker 里面的文件映射起来了。
```

### 简单的起一个 Nginx 服务来处理一下
```
apt-get update && apt-get install nginx -y  # 安装Nginx

```



