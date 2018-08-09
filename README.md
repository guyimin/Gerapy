# Gerapy

Distributed Crawler Management Framework Based on Scrapy, Scrapyd, Scrapyd-Client, Scrapyd-API, Django and Vue.js.
Gerapy 是一款分布式爬虫管理框架，支持 Python 3，基于 Scrapy、Scrapyd、Scrapyd-Client、Scrapy-Redis、Scrapyd-API、Scrapy-Splash、Jinjia2、Django、Vue.js 开发。

## Support

Gerapy is developed over Python 3.x. Python 2.x will be supported later.

## Usage
gerapy的初始化配置
Install Gerapy by pip:
安装gerapy框架。（注意要先用命令进入虚拟环境）

```bash
pip install gerapy
```

After the installation, you need to do these things below to run Gerapy server:
检查gerapy是否可用，命令：gerapy
If you have installed Gerapy successfully, you can use command `gerapy`. If not, check the installation.
现实如下证明安装成功
`usage：
   gerapy init
   gerapy migrate
   gerapy createsuperuser
   gerapy runserver
   `

First use this command to initialize the workspace:
初始化gerapy，生成gerapy框架的工作目录。(在哪初始化，工作目录就创建在哪。初始化完成，进入gerapy文件夹，会有一个projects文件夹。)

```bash
gerapy init
```

Now you will get a folder named `gerapy`.

Then cd to this folder, and run this command to initialize the Database:
先进入gerapy目录，再执行gerapy数据库的初始化，建立相关的数据库表。

```bash
cd gerapy
gerapy migrate
```

Next you can runserver by this command:
在gerapy目录下，启动gerapy服务，默认在8000端口。

```bash
gerapy runserver
```

Then you can visit [http://localhost:8000](http://localhost:8000) to enjoy it.
具体的服务器地址安装cmd窗口提示的地址。

Or you can configure host and port like this:
或者在命令后添加需要配置的主机位置和端口：

```
gerapy runserver 0.0.0.0:8888
```

Then it will run with public host and port 8888.
这样设置将运行公共主机位置和端口。

You can create a configurable project and then configure and generate code automatically.Also you can drag your Scrapy Project to `gerapy/projects` folder. Then refresh web, it will appear in the Project Index Page and comes to un-configurable, but you can edit this project in the web interface.

As for the deploy, you can move to Deploy Page. Firstly you need to build your project and add client in the Client Index Page, then you can deploy the project by clicking button.

After the deployment, you can manage the job in Monitor Page.

## 主界面
打开浏览器，输入：http://localhost:8000，或者 gerapy runserver命令中返回的地址，可以看到 Gerapy 的主界面，初始化完成。

## 安装并开启scrapyd
在Anaconda Prompt中运行 
`
pip install scrapyd
`
在cmd中运行scrapyd，开启服务。(如果scrapyd在远程服务器上已经部署成功了，那么是不需要再次进行开启的。一般远程服务器上的scrapyd会一直保持运行状态。)

## 配置gerapy的主机
在gerapy主界面点击左侧 Clients 选项卡，即主机管理页面，添加我们的 Scrapyd 远程服务，点击右上角的create创建按钮即可添加我们需要管理的 Scrapyd 服务。
创建主机，名称，如spiderserver，如果scrapyd部署在本机上，使用127.0.0.1和默认端口，如果scrapyd部署在服务器上，使用公网ip和指定端口



## Docker
容器打包

Just run this command:

```
docker run -d -v ~/gerapy:/app/gerapy -p 8000:8000 thsheep/gerapy:master
```

Then it will run at port 8000.

Command:

```
docker run -d -v <your_workspace>:/app/gerapy -p <public_port>:<container_port> thsheep/gerapy:master
```

Please specify your workspace to mount Gerapy workspace by `-v <your_workspace>:/app/gerapy` and specify server port by `-p <public_port>:<container_port>`.

If you run Gerapy by Docker, you can visit Gerapy website such as [http://localhost:8000](http://localhost:8000) and enjoy it, no need to do other initialzation things.

## Preview

Client Management:

![](https://ws4.sinaimg.cn/large/006tKfTcly1fkbdxmxtg8j31kw0smak0.jpg)

Spider Monitor:

![](https://ws4.sinaimg.cn/large/006tKfTcly1fkbe2idj4tj31kw0skqfp.jpg)

Project Management:

![](https://ws2.sinaimg.cn/large/006tKfTcly1fkbebgjxguj31kw0l4jyp.jpg)

Project Edit:

![](https://ws1.sinaimg.cn/large/006tKfTcly1fkbe00vpakj31kw0qx7ez.jpg)

Project Deploy:

![](https://ws4.sinaimg.cn/large/006tKfTcly1fkbe3w2jrij31kw0shtgr.jpg)

Project Configuration:

![](https://ws2.sinaimg.cn/large/006tKfTcly1fkbe5aqerdj31kw0xggu0.jpg)

## TodoList

- [ ] Add Visual Configuration of Spider with Previewing Website
- [x] Add Scrapyd Auth Management
- [ ] Add Automatic Python & Scrapyd Environment Deployment
- [ ] Add MongoDB & Redis & MySQL Monitor
- [ ] Add Timed Task Scheduler

## Communication

If you have any questions or ideas, you can join this QQ Group:

![](https://ws2.sinaimg.cn/large/006tNc79gy1fno6qey8a3j307609k3zs.jpg)
