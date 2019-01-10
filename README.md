# SpringCloudConfig

这是一个配置服务器的git仓库，在这里存放的是spring cloud的各个服务的配置文件，结构目录如下

```
config-repo
|
---{application}
	|
	---{profile}
		|
		---application.yml
```

创建一个git本地仓库

```bash
$ cd $HOME
$ mkdir config-repo
$ cd config-repo
$ git init .
$ echo info.foo: bar > application.properties
$ git add -A .
$ git commit -m "Add application.properties"
```

修改配置文件后就可以了，这时候应用想要使用新的配置项，在开启`actuator`监控的情况下访问

```bash
$ curl http://{application}:{port}/actuator/refresh
```

就可以在不重启服务的情况下刷新配置项
