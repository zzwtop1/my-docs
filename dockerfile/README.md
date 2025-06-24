语言: [English](README-EN.md) | [简体中文](README.md)
目前有2个文件  
1.docker-my-conda  
根据ubuntu:22.04创建conda镜像文件的dockerfile，使用该文件创建一个名字叫my-conda，
版本1.0的镜像，方法`docker build -t my-conda:1.0 -f docker-my-conda .`，
注意最后有个点，如果本地没有ubuntu:22.04的镜像会自动联网下载 

2.docker-my-llama_cpp 
根据之前创建的conda镜像新建一个llama.cpp项目的镜像，
如果你之前创建的conda镜像名字和版本不是my-conda:1.0，
那么需要修改docker-my-llama_cpp的FROM后面的内容，`git clone https://github.com/ggml-org/llama.cpp.git`这部分拉取的是线上最新版本,
如果时间相差过大需要修改这部分内容，最好先自行下载日期为2025.6.24的llama.cpp版本，然后使用COPY命令替代这部分  

