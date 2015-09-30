#Version: 0.0.1

FROM daocloud.io/node:0.10.40

MAINTAINER Ziming Zhang "zzmbpt@163.com"

ENV REFRESHED_AT 2015-9-30

VOLUME ["ghost"]
WORKDIR /ghost

EXPOSE 3000

ENTRYPOINT [ "npm","start","--production"]

#Run the docker container following the steps

# $mkdir /var/ghost
# $cd /var/ghost
#将dockerfile 复制到当前路径
# $docker build -t imageName .
#将ghost文件夹复制到/var/ghost下例如：ghost_0.7.0
# $docker run -d -p 8080:3000 --name containerName -v $PWD/ghost_0.7.0:/ghost imageName

#注意：上文中 EXPOSE 3000 是ghost服务监听的端口，在config.js中可以修改，在最后一步docker run之前将默认的2368端口修改成自己想要的端口号，并且将127.0.0.1全部修改为0.0.0.0 ，上文中8080是服务器主机端口号可自行根据需要修改。