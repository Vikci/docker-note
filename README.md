## Docker
```
Docker 是一种操作系统级别的虚拟化技术，由于关注于应用层面，所以它可以解决传统工作流方面众多棘手的问题。
Docker 能帮助企业把不同的团队的业务隔离开，降低开发与运维人员的沟通成本。除了能解决沟通成本问题，Docker 还鼓励使用独特的微服务方式处理软件的架构，使用微服务方式能构建更强健的软件。使微服务架构的核心应用服务的容器化，将解决依赖之前版本的构建问题。Docker 也非常契合应用微服务架构和 DevOps 构建方法论。
```
## 镜像vs容器 
```
容器基于镜像创建，镜像提供了部署和运行容器所需的一切基础。若想启动容器，必须下载公共镜像或创建自己的镜像。每个Docker镜像都包含一个或多个文件系统层，一般来说创建镜像时每个构建步骤都会创建一个文件系统层。Docker很大程度上依赖存储后端管理镜像。存储后端负责与底层Linux文件系统通信，用于构建和管理镜像的多个层。
我们可以把镜像理解成容器的生成模板，同一个镜像可以创建N个容器。容器是镜像的运行实例，是一个真实的系统进程。
```
# Dockerfile
```
Dockerfile 是 Docker 用来构建镜像的文本文件，包含自定义的指令和格式，可以通过 docker build 命令构建镜像。
Dockerfile 的指令根据作用可以分为两种，构建指令和设置指令:
*构建指令:用于构建image,其指定的操作不会在运行image的容器上执行。
*设置指令:用于设置image的属性，其指定的操作将在运行image的容器中执行。
Dockerfile 的指令忽略大小写，建议使用大写，使用 # 作为注释，每一行只支持一条指令，每条指令可以携带多个参数。
```

**Install docker on Mac OS**
*学习环境：MacOS version:10.12.6*

* [安装docker](https://docs.docker.com/docker-for-mac/install/)
* [配置阿里云Docker镜像加速器](https://yq.aliyun.com/articles/29941?spm=a2c4e.11153959.blogcont40494.11.41cf62b350edxf)

**Edit Dockerfile**
**Build Dockerfile**

*参考文档*
* [Docker学习路线图](https://yq.aliyun.com/articles/40494?spm=a2c4e.11153959.teamhomeleft.23.360918b13WGTgY)
* [Dockerising a Node.js and MongoDB App](https://medium.com/statuscode/dockerising-a-node-js-and-mongodb-app-d22047e2806f)
* [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
