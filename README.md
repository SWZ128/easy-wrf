![logo](asset/logo.png)

# Easy-WRF

WRF（Weather Research and Forecasting Model）模式是由NCEP，NCAR等科研机构中心着手开发的一种统一的中尺度天气预报模式。
WRF模式系统具有的可移植，易维护，可扩充，高效率，方便等特点，使其成为改进从云尺度到各种不同天气尺度的重要天气特征预报精度的工具。

本项目是单节点建模运行的容器化WRF，主要用于教学和培训示例。

## Features

- WPS + WRF（version 3.7.1）
- 简易部署（docker）
- 优雅易用（Oh-my-zsh）
- 精简小巧（镜像1.6GB左右）
- 国内部署简易

## Installation & Usage

### 1.使用 docker pull 拉取（推荐）

确保已经安装docker，如果还没有，[点击我](https://www.runoob.com/docker/centos-docker-install.html)

```shell
docker pull swz128/easy-wrf
```

检查镜像是否拉取成功

```shell
docker images
```

得到类似下方的输出

```shell
REPOSITORY        TAG       IMAGE ID       CREATED             SIZE
swz128/easy-wrf   latest    2c04b5c62a0b   About an hour ago   1.6GB
```

run

```shell
docker run -v 需要挂载的本地目录:容器中的目录 -it --name test_001 swz128/esay-wrf
```

例如这样（请将路径修改为自己的）

```shell
docker run -v /Users/mac/wrf/wrf-data:/root/wrf-data -it --name test_001 swz128/esay-wrf
```

现在就可以愉快地学习和使用了

停止容器

```shell
docker stop test_001
```

当退出并停止容器后，可以使用如下命令再次进入

```shell
docker start test_001
docker exec -it test_001 /bin/zsh
```

### 2.使用 docker build

将项目克隆到本地

```shell
git clone https://github.com/swz128/easy-wrf.git
cd easy-wrf/
```

Build

```shell
docker build -t esay-wrf .
```

## Support

- [官方文档](https://www2.mmm.ucar.edu/wrf/users/docs/user_guide_V3/user_guide_V3.8/contents.html)
- [官方GitHub](https://github.com/wrf-model/WRF/)
- [气象家园论坛](http://bbs.06climate.com/)

## Acknowledgment

- [container-wrf](https://github.com/NCAR/container-wrf)
- [WRF](https://github.com/wrf-model/WRF)
- [wrf-coop](https://github.com/davegill/wrf-coop)
- [wrf-src](https://www2.mmm.ucar.edu/wrf/src/)

## License

[MIT License](License)
