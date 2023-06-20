# Docker in Windows [[references]](https://blog.51cto.com/u_15404184/4315226)

``` 
docker pull [Image]

docker images

docker run -i -t [image] /bin/bash
``` 

Commit container to image
``` 
docker ps -al

docker commit [ID] [NEW_name]
``` 

Upload image
``` 
docker login --username=USER_NAME registry.cn-hangzhou.aliyuncs.com

docker tag [image_ID] [address]:[tag]

docker push [address]:[tag]
``` 
# Install Anaconda on Ubuntu [[references]](https://utho.com/docs/tutorial/how-to-install-anaconda-on-ubuntu-20-04-lts/)
