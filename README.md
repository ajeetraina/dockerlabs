# Docker Tutorial for Everyone

*A comprehensive, hands-on Docker learning platform*

**≡** [Beginner](#beginner) • [Intermediate](#intermediate) • [Advanced](#advanced) • [Community](#community)

---

![stars](https://img.shields.io/github/stars/collabnix/dockerlabs)
![Discord](https://img.shields.io/discord/1020180904129335379)
![GitHub contributors](https://img.shields.io/github/contributors/collabnix/dockerlabs)
![Twitter](https://img.shields.io/twitter/follow/collabnix?style=social)

Written and maintained by the [Collabnix Community](https://collabnix.com) • [⭐ Star us on GitHub](https://github.com/collabnix/dockerlabs)

## Introduction

**What is DockerLabs?**

DockerLabs is a comprehensive Docker learning platform designed to take you from complete beginner to Docker expert. Unlike other tutorials that focus on theory, we believe in **hands-on learning**. Every concept is paired with practical labs that you can run right in your browser or on your local machine.

**What makes this different?**

- **500+ Interactive Labs** - Learn by doing, not just reading
- **Progressive Learning Path** - Each lab builds on the previous one  
- **Real-world Examples** - Industry use cases and production scenarios
- **Community Driven** - Contributed by 1000+ developers worldwide
- **Browser-based** - No infrastructure required for most labs

Due to containerization benefits, Docker skills are in high demand. Companies like Netflix, Spotify, and Airbnb use Docker extensively. This tutorial will give you the practical skills these companies are looking for.

## What will this tutorial teach me?

This tutorial aims to be your **complete Docker journey**. By the end, you'll be able to:

- Build and deploy containerized applications
- Use Docker in development workflows  
- Implement Docker security best practices
- Deploy to cloud platforms (AWS, GCP, Azure)
- Manage containers at scale with orchestration

We'll start with the basics and progressively build to advanced topics like Docker Swarm, Kubernetes integration, and production deployment strategies.

---

## Getting Started

This tutorial contains three main learning tracks, each building on the previous one. You can jump to any section, but we recommend following the path sequentially.

**Prerequisites:**
- Basic command line familiarity
- A computer with Docker installed ([Installation Guide](./workshop/docker/dockerhub))
- Curiosity and willingness to experiment!

**Time Investment:**
- **Beginner Track**: ~8 hours (40 labs)
- **Intermediate Track**: ~12 hours (50 labs)
- **Advanced Track**: ~10 hours (31 labs)

---

## 🔰 Beginner Track
*Perfect for newcomers to containerization*

**What you'll learn:** Docker fundamentals, basic commands, working with images and containers

### Hello Docker
Let's start with the classic "Hello World" to make sure your Docker installation works:

```bash
$ docker run hello-world
```

If you see a "Hello from Docker!" message, you're ready to continue! This simple command demonstrates the core Docker workflow: Docker downloads an image, creates a container, runs it, and cleans up.

### Your First Real Container
Now let's run something more interesting - an interactive Ubuntu container:

```bash
$ docker run -it ubuntu bash
```

Congratulations! You're now inside a Ubuntu container. Try these commands:
```bash
# ls -la
# cat /etc/os-release
# exit
```

**What just happened?** Docker downloaded an Ubuntu image, created a running container from it, and gave you an interactive shell. The `-it` flags provided an interactive terminal.

### [📖 Continue Beginner Track →](./beginners/README.md)

**Topics Covered:**

**🏗️ Getting Started with Docker Images**
- [Running Hello World Example](https://collabnix.github.io/dockerlabs/beginners/helloworld/) 
- [Working with Docker Image](https://collabnix.github.io/dockerlabs/beginners/workingwithdockerimage.html)
- [Saving Images and Containers as Tar Files for Sharing](http://dockerlabs.collabnix.com/beginners/saving-images-as-tar/)
- [Building Your First Alpine Docker Image and Push it to DockerHub](https://collabnix.github.io/dockerlabs/beginners/building-your-first-alpine-container.html)

**🔧 Container Management**
- [Accessing the Container Shell](http://dockerlabs.collabnix.com/beginners/accessing-the-container.html)
- [Running a Command inside running Container](http://dockerlabs.collabnix.com/beginners/running-command-inside-running-container.html)
- [Managing Docker Containers](http://dockerlabs.collabnix.com/beginners/managing-containers.html)

**📄 Dockerfile Mastery**
- [What is Dockerfile](https://dockerlabs.collabnix.com/beginners/dockerfile/Writing-dockerfile.html#what-is-a-dockerfile)
- [Understanding Layering Concept with Dockerfile](https://dockerlabs.collabnix.com/beginners/dockerfile/Layering-Dockerfile.html)
- 17 Hands-on Labs covering all Dockerfile instructions (ADD, COPY, CMD, ENTRYPOINT, WORKDIR, RUN, ARG, ENV, VOLUME, EXPOSE, LABEL, ONBUILD, HEALTHCHECK, SHELL, USER)

**💾 Data & Networking**
- [Managing volumes through Docker CLI](https://collabnix.github.io/dockerlabs/beginners/volume/managing-volumes-via-docker-cli.html)
- [Creating Volume Mount from docker run command](https://collabnix.github.io/dockerlabs/beginners/volume/creating-volume-mount-from-dockercli.html)
- [Docker Networking Basics](http://dockerlabs.collabnix.com/beginners/using-docker-network.html)

---

## 🎯 Intermediate Track  
*Ready to level up your Docker skills*

**What you'll learn:** Multi-container applications, Docker Compose, networking, and development workflows

### Multi-Container Applications
Real applications rarely consist of just one container. Let's build a web app with a database using Docker Compose:

```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "3000:3000"
  db:
    image: postgres:13
    environment:
      POSTGRES_PASSWORD: mypassword
```

```bash
$ docker-compose up
```

**What's happening here?** Docker Compose is orchestrating two containers: your web application and a PostgreSQL database, handling networking between them automatically.

### [📖 Continue Intermediate Track →](./intermediate/README.md)

**Topics Covered:**

**🐳 Docker Compose Deep Dive**
- [Introduction to Docker Compose](http://dockerlabs.collabnix.com/intermediate/docker-compose/)
- [Dockerfile Vs Docker compose](http://dockerlabs.collabnix.com/intermediate/workshop/DockerCompose/Difference_between_dockerfile_and_docker_compose.html)
- 22 Hands-on Labs covering all Compose commands (version, help, config, build, pull, push, up, images, ps, stop, start, restart, pause, unpause, logs, port, run, scale, exec, kill, rm, down)
- [Create first docker compose file with nginx and mysql](http://dockerlabs.collabnix.com/intermediate/workshop/DockerCompose/Create_first_docker-compose_file_with_ngnix_and_mysql.html)
- [A Simple Wordpress Application using Docker Compose](https://github.com/collabnix/dockerlabs/blob/master/intermediate/workshop/DockerCompose/single-node-wordpress.md)

**🌐 Docker Swarm Orchestration**
- [What is Docker Swarm](http://dockerlabs.collabnix.com/intermediate/workshop/what-is-docker-swarm.html)
- [Docker Swarm Terminology](http://dockerlabs.collabnix.com/intermediate/workshop/Docker-Swarm-Terminology.html)
- [Creating 5-Node Docker Swarm Cluster](http://dockerlabs.collabnix.com/intermediate/workshop/getting-started-with-swarm.html)
- 7 Hands-on Labs covering overlay networks, service deployment, scaling, and node management

**🔗 Advanced Networking**
- [Docker Overlay Networking](http://dockerlabs.collabnix.com/intermediate/workshop/networking/Lab%231:Docker_Overlay_Networking.html)
- [Service Discovery & Routing Mesh](http://dockerlabs.collabnix.com/intermediate/workshop/networking/Lab%20%235_Test_Service_Discovery.html)
- [MacVLAN Implementation](http://dockerlabs.collabnix.com/intermediate/workshop/networking/lab7-macvlan.html)

---

## 🚀 Advanced Track
*Master Docker for production environments*

**What you'll learn:** Security, orchestration, performance optimization, and production deployment

### Container Security
Security should never be an afterthought. Let's scan our images for vulnerabilities using Docker Scout:

```bash
$ docker scout cves ubuntu:latest
```

**Why this matters:** In production, vulnerable containers can be entry points for attackers. Docker Scout helps identify and fix security issues before deployment.

### [📖 Continue Advanced Track →](./advanced/README.md)

**Topics Covered:**

**🔒 Docker Security**
- [Docker Content Trust](http://dockerlabs.collabnix.com/advanced/security/trust/README.html) - 8 Labs covering image signing and verification
- [Docker Secrets Management](http://dockerlabs.collabnix.com/advanced/security/secrets/) - 4 Labs on managing sensitive data
- [Docker Network Security](http://dockerlabs.collabnix.com/advanced/security/networking/) - Encrypted overlay networks
- [Security Scanning](http://dockerlabs.collabnix.com/advanced/security/scanning/) - Vulnerability assessment
- [Swarm Mode Security](http://dockerlabs.collabnix.com/advanced/security/swarm/) - Production cluster security

---

## 🛠️ Latest Docker Features & Developer Tools

### Docker Scout - Software Supply Chain Security
Scan your containers for vulnerabilities and get actionable insights:

```bash
$ docker scout quickview
$ docker scout cves
$ docker scout recommendations
```

**Scout Resources:**
- [Download Docker Scout Cheatsheet](https://www.docker.com/resources/scout-cheat-sheet/)
- [Docker Scout Community Repository](https://github.com/collabnix/docker-scout-community)
- [Integrate Scout with GitHub Actions](https://docs.docker.com/scout/integrations/ci/gha/)

### Docker Init - Bootstrap Your Projects
Docker now includes a tool to generate optimized Dockerfiles and Compose files:

```bash
$ docker init
```

**Try it with different languages:**
- [Python Projects](https://github.com/dockersamples/docker-init-demos/tree/main/python)
- [Node.js Projects](https://github.com/dockersamples/docker-init-demos)  
- [Go Projects](https://github.com/dockersamples/docker-init-demos/tree/main/go)
- [Rust Projects](https://github.com/dockersamples/docker-init-demos/tree/main/rust)
- [ASP.NET Projects](https://github.com/dockersamples/docker-init-demos/tree/main/dotnet)
- [PHP Projects](https://github.com/dockersamples/docker-init-demos/tree/main/php/app)

### Docker Desktop Features
- [Docker Dashboard, Dev Environments, Extensions](./workshop/dockerdesktop/README.md)
- [Docker Extensions Development](https://github.com/collabnix/docker-community-extensions)

### Modern Development Workflows
- [Compose Watch](https://github.com/dockersamples/docker-init-demos/tree/main/python/compose-watch) - Auto-sync and rebuild
- [Compose Include](https://github.com/ajeetraina/compose-include) - Modular compose files
- [Compose Profiles](https://github.com/ajeetraina/compose-demos/blob/main/wordpress/profile/README.md) - Environment-specific configurations

---

## 🌐 Industry Use Cases & Real-World Applications

### Sample Applications
Explore our curated collection of real-world applications built with Docker:

**Web Frameworks:**

| Python/Django | Reactjs | Golang | Java/Spring |
|:---|:---|:---|:---|
| [Docker + Django + PostgreSQL](./solution/django-postgres/readme.md) | [React + Spring + MySQL](https://github.com/docker/awesome-compose/tree/master/react-java-mysql) | [Go + NGINX + MySQL](https://github.com/docker/awesome-compose/tree/master/nginx-golang-mysql) | [Spring + PostgreSQL](https://github.com/docker/awesome-compose/tree/master/spring-postgres) |
| [Python + Flask + Redis](https://github.com/docker/awesome-compose/tree/master/flask-redis) | [React + Express + MySQL](https://github.com/docker/awesome-compose/tree/master/react-express-mysql) | [Go + NGINX + PostgreSQL](https://github.com/docker/awesome-compose/tree/master/nginx-golang-postgres) | [Java Spark + MySQL](https://github.com/docker/awesome-compose/tree/master/sparkjava-mysql) |

**Database Solutions:**

| PostgreSQL | MongoDB | MySQL |
|:---|:---|:---|
| [Docker + Django + PostgreSQL](./solution/django-postgres/readme.md) | [NGINX + Flask + MongoDB](https://github.com/docker/awesome-compose/tree/master/nginx-flask-mongo) | [NGINX + ASP.NET + MySQL](https://github.com/docker/awesome-compose/tree/master/nginx-aspnet-mysql) |
| | [NodeJS + MongoDB](https://github.com/collabnix/dockerlabs/tree/master/solution/node-mongo-docker) | |

**Monitoring & Logging:**

| Monitoring | Logging | Testing |
|:---|:---|:---|
| [Docker + Prometheus Stack + Docker Swarm](./play-with-docker/docker-prometheus-swarm/README.md) | [Docker + Elasticsearch + Logstash + Kibana + Docker Swarm](./play-with-docker/ELK/README.md) | [Docker + Apache Jmeter + Docker Swarm Mode](./play-with-docker/jmeter-docker/README.md) |
| | [Elasticsearch + Logstash + Kibana](https://github.com/docker/awesome-compose/tree/master/elasticsearch-logstash-kibana) | |

### Industry Applications
- [Docker for AI/ML Development](https://www.docker.com/products/ai-ml-development/)
- [Docker for Financial Services](https://collabnix.com/5-benefits-of-docker-for-the-finance-and-operations/)
- [Docker for Healthcare](https://collabnix.com/5-benefits-of-docker-for-the-healthcare-industry/)

---

## 📚 Featured Resources & Learning Materials

### Latest Blog Posts and Articles
- [Docker GenAI Stack on Windows using Docker Desktop](https://collabnix.com/docker-genai-stack-on-windows-using-docker-desktop/)
- [A First Look at Docker Scout – A Software Supply Chain Security for Developers](https://collabnix.com/a-first-look-at-docker-scout-a-software-supply-chain-security-for-developers/)
- [Getting Started with GenAI Stack powered with Docker, LangChain, Neo4j and Ollama](https://collabnix.com/getting-started-with-genai-stack-powered-with-docker-langchain-neo4j-and-ollama/)
- [Docker Init for Go Developers](https://collabnix.com/docker-init-for-go-developers/)
- [What is Docker Compose Include and What problem does it solve?](https://collabnix.com/what-is-docker-compose-include-and-what-problem-does-it-solve/)
- [How to Integrate Docker Scout with GitHub Actions](https://collabnix.com/how-to-integrate-docker-scout-with-github-actions/)

### Quick Reference Materials
- [Docker Cheatsheet](./docker/cheatsheet/README.md)
- [Docker Certificate Associate Exam Preparation](./docker/dca.md)
- [Docker Interview Questions](./docker/docker-interview-questions.md)
- [Concepts and Terminologies Guide](./beginners/README.md)

### Containerd Resources
- [What is Containerd and what problems does it solve](https://collabnix.com/what-is-containerd-and-what-does-it-solve/)
- [Containerd and Kubernetes](https://collabnix.com/containerd-and-kubernetes-how-are-they-related/)
- [How To Run Containerd On Docker Desktop](https://collabnix.com/how-to-run-containerd-in-docker-desktop/)
- [Getting Started With Containerd 2.0](https://collabnix.com/getting-started-with-containerd-2-0/)

---

## 🤝 Community

### Join 11,000+ Docker Learners

**[💬 Discord](https://discord.gg/QEkCXAXYSe)** - Get real-time help (2,300+ members)  
**[📱 Slack](https://launchpass.com/collabnix)** - Professional discussions (9,000+ members)  
**[🐦 Twitter](https://twitter.com/collabnix)** - Latest updates and tips  

### Contribute to DockerLabs

This is a community-driven project. Here's how you can help:

- **Fix a typo** - Even small improvements matter
- **Add a lab** - Share your Docker knowledge  
- **Translate content** - Help non-English speakers
- **Report issues** - Help us improve

**[📖 Contributing Guide →](./CONTRIBUTING.md)**

### Success Stories

*"DockerLabs helped me land my first DevOps job. The hands-on approach made all the difference."*  
— **Community Member**

*"Our entire team went through the intermediate track. It standardized our Docker knowledge."*  
— **Development Team Lead**

---

## 👥 Governance & Core Contributors

Dockerlabs is an independent community project founded by [Ajeet Singh Raina](https://github.com/ajeetraina), a [Docker Captain from India](https://www.docker.com/captains/ajeet-singh-raina) & Docker Community Leader which is now being built & shaped by a growing community of contributors across the globe.

| [<img src="https://avatars1.githubusercontent.com/u/313480?s=400&v=4" width="48px;" alt="Ajeet Singh Raina"/><br /><sub><b> Ajeet Singh Raina</b></sub>](https://github.com/ajeetraina)<br /> | [<img src="https://avatars1.githubusercontent.com/u/21982562?s=460&v=4" width="48px;" alt="Sangam Biradar"/><br /><sub><b>Sangam Biradar</b></sub>](https://github.com/sangam14)<br /> | [<img src="https://avatars0.githubusercontent.com/u/7204666?s=400&v=4" width="48px;" alt="Savio Mathew"/><br /><sub><b>Savio Mathew</b></sub>](https://github.com/saviovettoor)<br /> | [<img src="https://avatars1.githubusercontent.com/u/8190114?s=400&v=4" width="48px;" alt="Saiyam Pathak"/><br /><sub><b>Saiyam Pathak</b></sub>](https://github.com/saiyam1814)<br /> | [<img src="https://avatars2.githubusercontent.com/u/38501348?s=400&v=4" width="48px;" alt="Apurva Bhandari"/><br /><sub><b>Apurva Bhandari</b></sub>](https://github.com/apurvabhandari)<br /> | [<img src="https://avatars2.githubusercontent.com/u/25828217?s=400&v=4" width="48px;" alt="Sarkar Tathagata"/><br /><sub><b>Sarkar Tathagata</b></sub>](https://github.com/amitatha82)<br /> | [<img src="https://avatars2.githubusercontent.com/u/33524591?s=400&v=4" width="48px;" alt="Prashansa K"/><br /><sub><b>Prashansa K</b></sub>](https://github.com/Prashansa-K)<br /> |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| [<img src="https://avatars1.githubusercontent.com/u/34628205?s=400&v=4" width="48px;" alt="Wikitops"/><br /><sub><b>Wikitops</b></sub>](https://github.com/wikitops)<br /> | [<img src="https://avatars0.githubusercontent.com/u/20920080?s=400&v=4" width="48px;" alt="Akshit Grover"/><br /><sub><b>Akshit Grover</b></sub>](https://github.com/akshitgrover)<br /> | [<img src="https://avatars3.githubusercontent.com/u/18344557?s=400&v=4" width="48px;" alt="Ameya Agashe"/><br /><sub><b>Ameya Agashe</b></sub>](https://github.com/ameyaagashe)<br /> | [<img src="https://avatars1.githubusercontent.com/u/39425180?s=400&v=4" width="48px;" alt="Bala"/><br /><sub><b>Bala</b></sub>](https://github.com/balasu)<br /> | | | |

---

## What's Next?

1. **[Start with Basics](./beginners/README.md)** - If you're new to Docker
2. **[Jump to Intermediate](./intermediate/README.md)** - If you know Docker basics  
3. **[Explore Latest Features](#latest-docker-features--developer-tools)** - Check out Scout, Init, and Extensions
4. **[Join Community](#community)** - Connect with other learners

---

## License

[Apache License 2.0](./LICENSE.md)

---

<div align="center">

**Built with ❤️ by the [Collabnix Community](https://collabnix.com)**

*Help us improve this tutorial by [contributing](./CONTRIBUTING.md) or [reporting issues](https://github.com/collabnix/dockerlabs/issues)*

**[Proceed to Beginners Track >>](./beginners/README.md)**

</div>