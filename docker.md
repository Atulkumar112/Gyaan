## Docker

Docker is a software platform that allows you to build, test, and deploy applications quickly using containers.

#### OR

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.	

#### OR                     			

Docker is an open-source platform that allows developers to automate the deployment, scaling, and management of applications inside lightweight, portable containers. 

### "OR IN A SIMPLE WORDS, MUST READ IT"

In simple words, Docker is a tool that helps developers package their software and all its dependencies together, making it easy to run and use on any computer. It's like putting your app in a special box that contains everything it needs to work, so you don't have to worry about setting it up again and again on different computers. This makes it faster to develop and test software and ensures that it works the same way everywhere.

### Containers

In simple words, a container in Docker is like a small, self-contained isolated environment that holds your application and all its necessary components, like libraries and settings. It's a lightweight and portable package that allows you to run your application consistently and reliably on any computer that supports Docker. Containers make it easy to isolate and manage your applications, so they work the same way everywhere without conflicts or compatibility issues.

### Container Image

In simple words, a container image in Docker is like a blueprint or template for creating containers. It contains all the necessary instructions and files to build and run your application in a standardized and isolated way. It's like a snapshot of your application and all its dependencies, so you can easily share and distribute it to run on any computer that supports Docker. Container images make it simple to package and deploy your applications consistently, ensuring they work the same way wherever they are run.

- Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. 

### Virtual Machine in Docker

In simple words, a virtual machine in Docker is like a complete computer within your computer. It's a software emulation of a computer system, including its operating system and applications. With a virtual machine, you can run multiple operating systems and applications on the same physical computer.

Now, Docker is different from traditional virtual machines. Instead of emulating a complete computer, Docker uses containers, which are lightweight and share the host computer's operating system. Containers isolate applications and their dependencies, so they can run independently without interfering with each other.

In summary, virtual machines provide full system emulation, running separate operating systems, while Docker containers offer lightweight and isolated environments for running individual applications on a shared operating system. This makes Docker more efficient and faster to start compared to traditional virtual machines.

### Diff b/w docker container and docker images

#### Docker image

- Definition: A Docker image is a read-only template that contains the application's code, runtime environment, libraries, dependencies, and everything required to run the application.

- Purpose: It's essentially the blueprint or snapshot of your application and environment, which can be used to create containers.
 
- Immutable: Images cannot be changed once they are created. If changes are needed, a new image must be built.
 
- Stored: Images are stored in Docker's local registry or a remote registry like Docker Hub.
 
- Example: ubuntu:latest or nginx:alpine are examples of pre-built images.


#### Docker Container:

- Definition: A Docker container is a running instance of a Docker image. When you run an image, it creates a container that is an executable package containing everything needed to run the software, including the image.
 
- Purpose: Containers are the live environments in which your application runs. They are isolated, lightweight, and portable.
 
- Mutable: Containers can be modified while running (e.g., changing files, configurations), but those changes do not persist in the image itself. When a container is stopped and removed, changes are usually lost unless they are committed to a new image.
 
- Example: When you run docker run nginx, you're creating a container from the nginx image.





