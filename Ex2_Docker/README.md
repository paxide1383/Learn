### Exercise 2 - Docker

Docker is used for running containers. Once Docker is installed containers can be quickly created using Bash commands or using build files (named Dockerfiles).

[Install Docker by following the official guidance.](https://docs.docker.com/get-started/)  

*E.g. if you're on Ubuntu run:*
`apt install docker` (or is is `apt install docker.io` maybe?)

**nb Docker always requires elevation so needs to be run with sudo**

#### Docker Section 1 - Some  Docker Basics
To spin up your first Docker container run the following command: </br>
`sudo docker run -ti alpine /bin/ash`<br>
*The options for this command will be discussed in section B*

It may or may not take a moment on first run as it has to pull the image from the Docker Hub on the Internet. After this, the image is available locally until you remove it so it would be quicker to run this command next time.

You should see a change to your prompt when the container is running, this denotes that you're at the command prompt within the running container. Open a new terminal window on your computer and run:
`sudo docker ps -a`


This should output a list of all running containers. Note your container is an alpine image, this is an extremely lightweight distro of linux. From your other terminal host window check out the output from the following commands:<br>
`sudo docker container ls`<br>
`sudo docker image ls`<br>

The container command lists active containers and is useful for finding the container ID and container name. <br>
The image command is useful for viewing info about the base images. This alpine image is only 5.57Mb, if you spun up the official Ubuntu or Centos images (i.e .`sudo docker run -ti ubuntu /bin/bash`) and checked you would find they are over 200Mb in size - feel free to experiment trying this if you have the disk space. <br>
[Explore other available container base images on Docker Hub and try a few out](https://hub.docker.com/search?q=&type=image)

To clear up and remove containers first `exit` the active container you're running (or run `sudo docker kill cont_name` from your host terminal), then run `sudo docker container rm cont_name` and/or `sudo docker image rm image_name`

####  Docker Section 2 - Some More Basics
So what was actually going on when running the command:</br>
`sudo docker run -ti alpine /bin/ash`<br>

The answer is that it ran a container interactively and connected you to that running container...
* The docker **run** command tells a container what binary command to run - in this case it was a shell command: **/bin/ash**. /bin/ash is a lightweight flavour of bash installed on Alpine. If you spun up a Ubuntu image, the  you would include would have been `/bin/bash` as that's the typical default shell on Ubuntu. As it's a shell, it will persist until you `exit` it. Alternatively try running any other linux executable command - e.g. try runnning `/bin/ls` as part of your docker run and checking the output; you should see it generating the ls output and then the container finishes. This is because ls exits when it is complete unlike a shell that the user chooses to exit.
* **-ti** are two switch options, the **t** tells the container have an assigned TTY (needed to interactive with a shell), and the **i** tells the container it should be interactive. Bear in mind containers aren't typically expected to be interacted with, they should normally exist just to run a single process or service, in theory a container instance is disposable so the idea is to destroy a container and start a new one if it has issues.

Run `sudo docker run --help` for a full list of command line options.

It's worth noting, when you spin up a container and access it interactively, any changes you make to it are lost when you exit **unless you commit them** and so create a new image. Try this out by running your alpine container, create a new directory when it's running and exit the container, then spin up the container again. The directory previously made will be gone.

Follow these steps to create a new local image from the base container:
1. Run `sudo docker run -ti alpine /bin/ash`
2. From inside the container run `mkdir /my_new_dir`
3. Run `ls /` to check your directory was created
4. Without exiting that running container, from a separate terminal window use `sudo docker ps` to find the container name or ID of the running container, then run<br> `sudo docker commit [container name/ID] my_new_alpine_image`
5. This will create a new local version of the alpine image called **my_new_alpine_image**.  If you exit your running container, you can now use this image as the base for starting up new containers as follows: `sudo docker run -ti my_new_alpine_image /bin/ash`
6. When you're in the new container, run the `ls` command and you should see your directory is now there as it's baked into the image from now on.

Experiment with creating other changes to images, for example spin up your image and then install bash and python3 using the following commands:
* `apk update `  -  *This updates existing apk package manager repos*
* `apk add bash` - *This installs the bash shell*
* `apk add python3` -  *This installs python3*

Next run the docker commit command from a host terminal to overwrite your *my_new_alpine_image* - **important - your container will now have a different container name / ID from the previous commit command so be sure to get the new name / ID for your commit command**.<br>
If all went well, you now have a new base image called **my_new_alpine_image** that has both bash and python3 on it; you shoud now be able to issue your docker run command and run the **/bin/bash** shell instead of **/bin/ash**:<br>
1. `sudo docker run -ti my_new_alpine_image /bin/bash`  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *- your prompt should now be 'bash'*
2. In your container run `python3` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *Opens the python3 CLI*
3. Type in `import this`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *Outputs the zen of Python to demonstrate you have an active Python on your container*
4. Type `exit()` to come out of python3 and then `exit` to come out of your container.
5. From your host terminal `cd` into the folder in this Repo called **Ex2_Docker** (there should be a file called hello_python.py in there).
5. From within this directory run `sudo docker run -ti --rm -v "$PWD":/myscript -w /myscript my_new_alpine_image './hello_python.py'`
6. Make a copy of the *hello_python.py* script and make a few changes to it if you want to experiment a little.


Step 5 has two extra option included. The `-v "$PWD":/myscript` maps your present working directory (i.e. the Ex2_Docker directory) and makes it available as a directory mounted inside the running container named as */myscript*. This is useful for making data avaialble to your docker container. <br>
The `-w /myscript` then just tells the container that's spinning up to use */myscript* as its present working directory. There are a lot of configurable options when running docker containers including options to specify and join networks, CPU, expose ports to the host etc.
