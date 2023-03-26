# RabbitMQ_Note





## 一、安装（docker版）

1. 查找镜像

```
sudo docker search rabbitmq
```

2. 拉取镜像

```
sudo docker pull rabbitmq
```

3. 运行MQ镜像：

```
sudo docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq
```

4. 开启Web控制台插件

```
#查看容器id
sudo docker ps -a

#进入到容器内部
docker exec -it [CONTAINERID] /bin/bash

#开启Web控制台插件
rabbitmq-plugins enable rabbitmq_management

#然后使用http://youadmin:15672/即可访问，默认用户名密码都是guest
```

5. 修改用户密码

```
#参考第4步进入容器

#搜索全部用户
rabbitmqctl  list_users

#根据用户名修改密码
rabbitmqctl  change_password  [Username]  'Newpassword'
```

