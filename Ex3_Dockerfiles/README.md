##Exercise 3 Docker Build and Dockerfiles

In this exercise, we use dockerfile and the docker build command to build our docker image from scratch rather than building it up manually by accessing the running container,configuring it and executing the Docker commit commands on it.

First of, remove the existing image you've created called my_new_alpine_image, remove all traces of its containers and images (nb if you've been starting containers using the `--rm` switch it automatically removes the container once it stops).

Have a look at the commands in the file called **Dockerfile** in this Ex3 directory,


From this directory in your terminal window, run the following command:  
`sudo docker build -t alpine2 .`  *#Don't forget the .*

It might take a minute to complete, when it does run:  
`sudo docker run -it --rm alpine2`

You should get the input prompt for the python script similar to the previous exercise.  
So what has happened here? In essence it's that the first build command has ran a sequence of events that has pulled the original base alpine image from the Docker registry and built up the custom container into a new local image called alpine2. It is set to automatically execute the python script when the interactive docker run command is issued for that image.


Next, we will do the same process to build a simple python web server:  
`cd` into the sub-directory called **py_web**

To build the image:  
`sudo docker build -t alpine_web .`

And then to run:  
`sudo docker run -d -p 8000:8000 --rm alpine_web`

After this build process completes, confirm you have an alpine_web container running in the background (`sudo docker ps`), then open a new tab in your web browser and go to url: [http://localhost:8000](http://localhost:8000) - you should be presented with a browsable web page of the directory structure of the container that's running.

This container will run indefinitely until you either stop it or it crashes. I suggest you stop it to avoid leaving your self exposed to any security vulnerabilities (`sudo docker stop [container id]`).

Both or these examples built very small custom containers, but they demonstrate the idea of infrastructure by code. A container build could be scaled up considerably and provisioned as full clusters of containers. Couple this process with tight source/version control outlined in exercise 1 and this sets a powerful pattern for building and deploying applications using tightly controlled infrastructure states.

If you were to re-issue the run command mutiple times with different host port numbers (e.g. 8001:8000, 8002:8000, 8003:8000) this would spin up multiple containers all doing the same thing but all 100% identical in state regardless of the host machine.
