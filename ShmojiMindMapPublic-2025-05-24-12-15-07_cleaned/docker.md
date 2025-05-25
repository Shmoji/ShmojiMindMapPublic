  * tracking thoughts when using docker
    * tracking thoughts when setting up docker
      * tracking thoughts when setting up docker in general
        * [[2023-12-23]]
          * installing docker requires you to reset Windows computer - thaz annoying. Possibly bc you have to change kernel or smthn - maybe important to learn more about one day
      * tracking thoughts when setting up docker as containerized linux env on windows machine
        * [[2024-01-27]]
          * i ran this command: "docker run --name ubuntu-devevelopment -e HOST_IP=192.168.1.9 --expose 3000 -p 3000:3000 -v //c/Users/jackj/Desktop:/src -t -i tecnickcom/alldev /bin/bash"
          * this installs docker image from https://hub.docker.com/r/tecnickcom/alldev - it contains all kinds of dependences for linux env - you can see everything installed in dockerfile on github
          * the expose and p args map ports between docker env and your machine's ports - gotta do it otherwise wont be mapped
          * the v command - says that when we access src directory in docker container, it is symlink to .../Desktop we defined on host machine. And you can navigate to other places of course
          * after running this, youll notice in docker dashboard, youll see docker container running on port 3000. From there you can get in cli or youll also be in container cli after running command
          * you only have to run command above once to get image - from then on you just start container from docker dashboard, in powershell run docker ps, docker attach <container_id>
          * if having trouble with localhost, try using your IP instead when doing dev stuff
          * i was confused where to do dev and then asked GPT some questions and now i get it: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/docker#^xhNBKXvtf|when you create docker container, where should you do development? like if i want to clone some repo and work in that repo locally, where do i do it in the container?]]
          * so -v command above was v related to where to dev
  * how TOs
    * how to create new container env
      * docker run --name noosphere-container -e HOST_IP=192.168.1.9 --expose 3000 -p 3000:3000 -v //c/Users/jackj/Projects/noosphere-stuff/noosphere:/src -t -i tecnickcom/alldev /bin/bash
        * give name you want, your device IP, port you want and map directory you want to /src
        * this is specifically a docker image for base linux env in container thanks to  tecnickcom/alldev image from dockerhub
    * how to get in and use container that is already started
      * docker exec -it <docker_container_id_thing> /bin/bash
    * how to allow docker container to use MORE RAM ^tqRhBucZV
      * if using [[wsl]]2 (will tell you in docker settings): at your user home (cd ~), create .wslconfig and paste this in:
        * [wsl2]
memory=15GB 
        * then run wsl --shutdown
        * then kill prior container with too little RAM and docker run new one (maybe need to use -m 16GB arg to define mem limit, but idk)
        * run htop command to see available mem yay

  * questions
    * when you create docker container, where should you do development? like if i want to clone some repo and work in that repo locally, where do i do it in the container? ^xhNBKXvtf
      * GPT4:
        * summary: use your local environment for development (coding, editing, version control) and Docker containers for running your application in a consistent, isolated environment. Docker volumes are key to linking your local development environment with the Docker container.
        * long version:
          * When working with Docker, it's important to understand the distinction between development environments and the role of containers. Here's a guideline on how you might approach development with Docker:
            * Local Development Environment:
              * Clone the Repository Locally: Typically, you would clone the repository to your local development environment, not inside the Docker container. This is because your local environment is where you'll be doing most of your editing, using your preferred tools and IDEs.
              * Write and Test Code Locally: You do your coding on your local machine where you have your development tools set up.
            * Using Docker for Development:
              * Dockerfile: Create a Dockerfile in your project. This file defines how your Docker container should be built, including the base image, any dependencies, and how your application should be run.
              * Docker Volumes: To work directly with the local files, use Docker volumes. A volume can be used to sync the files between your local environment and the Docker container. This means any changes you make locally will be reflected inside the container.
              * Running the Application: Once your Docker container is set up, you can start the container with your application. The containerized environment will be configured exactly how you need it for the application to run (e.g., specific versions of languages, tools, databases).
            * Workflow Example:
              * Step 1: You edit your files locally using your favorite IDE.
              * Step 2: You use Docker to build a container that mounts your code from your local directory into the container.
              * Step 3: You run your application inside the container, where it has access to all the necessary dependencies and environment settings.
        * me: so -v command is creating a volume?
          * GPT4: yes, When you use the -v flag, it mounts a directory from your host system into the container. This allows for data to be stored and accessed from the host system, even when the container is not running. Any changes to any side of symlink is reflected in both.
          * me: is this typically what "src" is meant for inside a container?
            * GPT4: yes, typically the source code directory
