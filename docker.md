## Docker 简介
1. Docker 是一种操作系统级别的虚拟化技术，关注于应用层面。
2. Docker 致力于轻易封装三个过程: 
  * 为任何应用，创建便于分发的构建镜像；
  * 把构建镜像大规模部署到任何环境中；
  * 简化敏捷软件开发团队的工作流程，提升软件的交付效率。
3. Docker 式工作流的好处
  * 加快应用开发测试和部署，保持开发环境和生产环境一致，如果流程中加入CI/CD，可以达到更高的效率；
  * 使用标准的镜像格式打包软件应用和所需的操作系统环境；
  * 在运行任何系统的任何环境中测试和部署同一个打包好的镜像；
  * 把软件应用与硬件剥离，不滥用资源
  * 微服务化

## Docker 安装
   [Docker for Mac](https://docs.docker.com/docker-for-mac/install/#install-and-run-docker-for-mac)
   [Docker for Linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

## 镜像(image) vs 容器(container)
  1. 容器基于镜像创建，镜像提供了部署和运行容器所需的一切基础。若想启动容器，必须下载公共镜像或创建自己的镜像。
  2. 每个镜像都包含一个或多个文件系统层，一般来说创建镜像时每个构建步骤都会创建一个文件系统层。
  3. Docker很大程度上依赖存储后端管理镜像。存储后端负责与底层Linux文件系统通信，用于构建和管理镜像的多个层。
  4. 可以把镜像理解成容器的生成模板，同一个镜像可以创建N个容器。容器是镜像的运行实例，是一个真实的系统进程。

## Dockerfile
  1. Dockerfile 是 Docker 用来构建镜像的文本文件，包含自定义的指令和格式，每条指令对应 Linux 下面的一条命令，可以通过 docker build 命令构建镜像。
  2. Dockerfile 的指令忽略大小写，建议使用大写，使用 # 作为注释，每一行只支持一条指令，每条指令可以携带多个参数。
  3. Dockerfile 的指令根据作用可以分为两种，构建指令和设置指令:
    * 构建指令:用于构建image,其指定的操作不会在运行image的容器上执行。
    * 设置指令:用于设置image的属性，其指定的操作将在运行image的容器中执行。

## Docker 常用指令
  1. 查看本地镜像 $ docker iamges
  2. 删除本地镜像 $ docker rmi 1e4d457cc824(IMAGE ID)
  3. 从[远程仓库](https://hub.docker.com/explore/)拉取镜像 $ docker pull node:latest
  4. 查看本地全部容器 $ docker ps -a
  5. 删除本地容器 $ docker rm 21daae74b641(CONTAINER ID)

## 容器化封装
  1. 在工程目录创建编辑 [Dockerfile](https://docs.docker.com/engine/reference/builder/)
  2. 用编辑好的 Dockerfile 来构建镜像
     $ docker build -f Dockerfile -t pier-mbl:1.0 --no-cache
  3. 运行镜像，并查看容器运行状态
     $ docker run --name=pier-mbl -p 8886:8886 -d pier-mbl:1.0
     $ docker ps -a (查看容器状态)
     $ docker logs -f pier-mbl (查看logs)
     $ docker exec -ti [容器ID] sh (交互式的与容器进行交互)

## 版本控制和自动构建
  1. 把Dockerfile 和对应的应用代码一起放到版本控制中，然后能够自动构建镜像
     
