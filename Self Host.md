---
label: Self Hosting
date: 2022-02-15
icon: server
order: 3000
author:
    -   name: Arpan Pandey
        email: arpan@hackersrebbot.tech
        link: https://hackersreboot.tech/about
        avatar: https://avatars.dicebear.com/api/bottts/Hackers.svg
---

# Self Hosting

We love to host things myself, to control it or to tweak it if nothing else atleast monitor it myself. Isn't it one of the benefits of OSS. So naturally we want our users to have that freedom. That is why here is the guide on how to do it properly.

### Method 1: Directly running the server
- Clone the project

```bash
  git clone https://github.com/Arpan-206/DevArmyKnife.git
```

- Go to the project directory

```bash
  cd DevArmyKnife
```

- Install dependencies

```bash
  yarn install
```

- Build for production and start the server.

```bash
  yarn run build
  yarn run start 
```

- And, Voila!

### Method 2: Using Docker

!!!info Info
This should be obvious but still, you would need [Docker](https://www.docker.com/) installed on your system for this.
!!!

#### Way 1: Pulling the image from DockerHub

- Pull the image from DockerHub.

```bash
  docker pull arpanpandey/dev-army-knife 
```

- Run the image as a container.

    - As a background process
        ```bash
        docker run --publish 8000:3000 -d  arpanpandey/dev-army-knife:latest 
        ```
    
    - With outputs in the terminal
        ```bash
        docker run --publish 8000:3000  arpanpandey/dev-army-knife:latest 
        ```

- Voila! We are done.

#### Way 2: Building the Docker Image

- Cloning the repository and changing directory.

```bash
  git clone https://github.com/Arpan-206/DevArmyKnife.git
  cd DevArmyKnife
```

- Building the image.
```bash
  docker build . --tag dev-army-knife 
```

- Run the image as a container.

    - As a background process
        ```bash
        docker run --publish 8000:3000 -d  dev-army-knife:latest 
        ```
    
    - With outputs in the terminal
        ```bash
        docker run --publish 8000:3000  dev-army-knife:latest 
        ```

- Voila! We are done.