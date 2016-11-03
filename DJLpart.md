### 3.2.1 Camunda BPM - Dockerized deployment (DJL)

Camunda BPM can be found, ready to deploy, on [Docker Hub][camunda on docker hub]. It is official image and can be used without complex settings "as is".

The main problem, during the PoC, was adding our customizations. Building our .jar and .war files required maven. We used maven in container, but configuration files for maven ware produced by Eclipse on local developer's machine and they ware appropriate for local build. In the configuration files, they ware several absolute (Windows) path names, which produced warnings and errors during the build on Linux build server. By the end of the project, we abandoned compiling on the Linux build server and our container was build from modules compiled on developer's machine. That problem showed that we need, for Java based development, much stronger support for configuring local workstations and stronger rules for making configuration files. In fact, with problems we had, it wasn't possible to compile project on other workstation, without manual interventions on configuration files. Such approach wasn't possible for automated build.

Second problem was debugging programs in container. Java error stack was misleading, pointing to configuration file as a source of problem. We made many versions of container to isolate source of the bug, but, at the end, bug was found on developer's machine.

In fact, the problem was in missing Java libraries. Those libraries existed on developer's machine, in Java library path, but not within Camunda/Tomcat libraries. That type of problem is known as "it works on my machine". Developer can add different third-party libraries on his machine, he can have libraries used in previous projects, so his machine could have parts of software not present on build, test or production server. That problem, is somehow, independent of dockerized deployment and more related with general approach in developing of Java projects and handling library dependences.

### 3.2.2 Bonita BPM - Dockerized deployment (DJL)

Dockerized deployment of Bonita was not tested. However, there is official image on [Docker hub][bonita on docker hub], so there should not be any more problems with Bonita, comparing with Camunda dockerized deployment.

### 3.3.1 Camunda DMN - Dockerized deployment (DJL)

Camunda DMN is a part of official Camunda docker image, so it was not tested dockerization of DMN standalone. However, DMN is in two .jar files, so dockerizing application with standalone DMN is trivial task.



[camunda on docker hub]: https://hub.docker.com/r/camunda/camunda-bpm-platform/
[bonita on docker hub]:https://hub.docker.com/_/bonita/
