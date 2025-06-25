A Dockerfile is a plain text file that contains a series of instructions used to build a Docker image, which serves as the blueprint for creating containers. Each instruction in a Dockerfile defines a step in assembling the image, such as specifying a base image, copying files, setting environment variables, or running commands to install software and dependencies.

**Relationship to Bash Scripts for Installing Libraries**

Dockerfiles commonly use the `RUN` instruction to execute shell commands during the image build process. This is where Bash scripts come into play. For example, you can use `RUN` to install open source or custom libraries using package managers like `apt-get`, `pip`, or by running custom shell scripts that automate more complex installation procedures. The `RUN` instruction defaults to using `/bin/sh`, but you can explicitly use Bash by either calling it directly or using the `SHELL` instruction to change the default shell to Bash for subsequent commands.

You might see something like:

```dockerfile
RUN apt-get update && apt-get install -y build-essential
RUN pip install numpy scipy
RUN /bin/bash /path/to/custom_install.sh
```

Or, if you have multiple Bash-specific commands:

```dockerfile
SHELL ["/bin/bash", "-c"]
RUN ./my_bash_script.sh
```

This approach allows you to automate the installation of both open source and custom libraries as part of the image build, ensuring that every container created from the image has the necessary dependencies pre-installed.

In summary, a Dockerfile acts as an automated build script for container images, and it often leverages Bash scripts or shell commands to install required libraries, making it a powerful tool for reproducible and portable software environments.


Let us look at one more example given below which is also in the examples folder for your reference.
```dockerfile
FROM ros:humble

RUN apt-get update && apt-get install -y nano

COPY config/ /home/.local/config/
```

This Dockerfile creates a custom container image based on ROS 2 Humble. Here’s what each line does:

- **`FROM ros:humble`** sets the base image to the official ROS 2 Humble image, providing a pre-configured environment for robotics development.
- **`RUN apt-get update && apt-get install -y nano`** updates the package list and installs the `nano` text editor inside the container, making it available for editing files during development or debugging.
- **`COPY config/ /home/.local/config/`** copies all files from the local `config` directory on your host machine into the container at `/home/.local/config/`, allowing you to include custom configuration files or scripts in the image.

This setup is typical for customizing a ROS 2 development environment, adding useful tools, and including necessary configuration files for your application.