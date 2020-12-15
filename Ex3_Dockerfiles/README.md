Remove the existing image you've created called my_new_alpine_image
this command won't run any more.

Have a look at the commands in the file called Dockerfile in this Ex3 directory,


Run:
sudo docker build -t alpine2 .

It might take a minute to complete, when it does run:
sudo docker run -it --rm alpine2

You will hopefully get the input prompt for the python script similar to the previous exercise. The first build command has pulled the original base alpine image from the Docker registry and built our custom container to a new local image called alpine2. 


Next, we will do the same process to build a simple python web server:
cd into the sub-directory called py_web

To build:
sudo docker build -t alpine_web .

To run:
sudo docker run -d -p 8000:8000 --rm alpine_web

Open a new tab in your web browser and open [http://localhost:8000](http://localhost:8000) and you should be presented with a browsable web page of the directory structure of the container that's running.

This will run indefinitely until you either stop the running container or it crashes. 

Both these examples were only building small custom containers, but this demonstrates the idea of infrastructure by code. This could scaled up considerably and provisioned as full clusters of containers. If you re-issue the run command with different host port numbers (e.g. 8001:8000, 8002:8000, 8003:8000) this would spin up mulitple containers all doing the same thing but all 100% identical in state.
