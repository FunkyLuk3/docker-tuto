# 🐳 DOCKER

Docker is a tool that can package an application and its dependencies in an isolated container, which can be run on any server.

## 📦 Download / Installation

To easily use docker you have to download [docker desktop](https://www.docker.com/products/docker-desktop).

After having followed the installation of docker you can in a terminal type the following command :

```cmd
docker run -d -p 85:80 hello-world
```
In the docker desktop application a container should have appeared. If so, the installation worked.

## 💡 How to create a Docker Image

To start, you will need to create a Dockerfile in a folder.

![image](./image/dockerfile.png)

Once the Dockerfile is created, you can open it with your favorite editor (VSCode has some extensions for Dockers).
There are several docker commands. We will look at the most important :

### FROM 
FROM allows you to specify the version and the image of the platform used by the docker (ex: ubuntu, centos, ...).
```docker
FROM {docker platform image}:{image version}
```
You can find all platform images here : [platform image](https://hub.docker.com/search?type=image).

### RUN 
RUN instruction will execute any commands in a new layer on top of the current image and commit the results.
```docker
RUN {command}
```
or
```docker
RUN ["executable","param1", "param2"]
```

### CMD 
CMD allows to execute commands in the CMD of the container.
```docker
CMD ["executable","param1","param2"] (exec form, this is the preferred form)
```
or
```docker
CMD {command} {param1} {param2} (shell form)
```

### EXPOSE 
EXPOSE instruction informs Docker that the container listens on the specified network ports at runtime.
```docker
EXPOSE {port}
```

For all other docker commands or for more details you can go to the [docker doc](https://docs.docker.com/engine/reference/builder/#environment-replacement).

Once your Dockerfile is finished, you just need to build the image.
Run the command below in a command prompt open in the folder where your Dockerfile is located.
```cmd
docker build --progress=plain -t {image name} .
```

## 📄 Launch a docker with your image

Execute the command below in a command prompt to create a container running the desired image.
```cmd
docker run -d -p {port}:{port} {image name}
```

## 📚 Official Docker Doc

- [Docker Doc](https://docs.docker.com/)
- [Image HUB for docker](https://hub.docker.com/search?q=&type=image)


## ✍ Contributor
- Luc ENEE
- Jess Leonatti