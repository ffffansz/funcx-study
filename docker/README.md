# Funcx-Jupyter镜像

基于python:3.8-alpine制作的funcx-jupyter镜像。

## 镜像构建

```shell
sudo docker build --pull --rm -t funcx-jupyter .
```

## 运行容器

```shell
sudo docker run -d --rm --name=funcx [-v <path_to_store_notebooks>:/root/work/] -p 8888:8888 funcx-jupyter:latest
```

其中`[-v <path_to_store_notebooks>:/root/work/]`是可选选项，挂载本地目录作为Jupyter的工作目录，容器停止后文件也会保留下来，建议添加。

`<path_to_store_notebooks>`需要替换为本地绝对路径。

## 访问

Jupyter服务运行在`0.0.0.0:8888`，初始token为`123456`，内部以root用户运行，仅限于本地测试，切不可暴露在公网环境下。
