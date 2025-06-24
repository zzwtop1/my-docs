Language: [English](README.md) | [简体中文](README.zh-CN.md)
There are currently two Dockerfiles available:
1. docker-my-conda  
This Dockerfile builds a Conda-based image based on ubuntu:22.04.
To create the image named my-conda with version 1.0, use the following command:
`docker build -t my-conda:1.0 -f docker-my-conda .`
Note: The final dot (.) is important — it indicates the build context.
If the ubuntu:22.04 image is not available locally, it will be downloaded automatically from the Docker registry.

2. docker-my-llama_cpp  
This Dockerfile builds an image for the llama.cpp project using the previously created Conda image.
If the Conda image you created is not named my-conda:1.0, you will need to modify the FROM line in docker-my-llama_cpp accordingly.
The command `git clone https://github.com/ggml-org/llama.cpp.git` in the Dockerfile fetches the latest version from the official repository.
If the latest version has significantly changed, you may want to download the specific version of llama.cpp dated 2025-06-24 in advance and replace the git clone command with a COPY instruction pointing to your local copy.
