The RIS Compute Service is fundamentally built around Docker Containers. Docker is a container platform (see Why docker? 
and What is a Container?) designed to make it easier to build and deploy software runtime environments. 
Users of the RIS Compute Service will be called upon to learn about Docker and its related concepts and technologies.

The Computing service is about building and executing Docker container images. While the RIS computing environment does 
offer ways to build containers (see Docker and the RIS Compute Service), it should be understood that users will 
oftentimes want their own computing environment, be that a Linux, MacOS, or Windows computing environment with which to 
build and work with Docker containers and Dockerfiles.

Furthermore, containers require a container registry to store the container images one builds. RIS does plan on offering 
a container registry service, but it is assumed that users will interact with public registries like Docker Hub.

The Compute service requires an understanding of these container technologies as well as a significant understanding of 
the Linux command line and related open source technologies, as well as high performance computing job schedulers.

Users of the service:
- Agree to install Docker on their own computing workstation or laptop.
- Agree to obtain accounts on Docker Hub or other public container registries.
- Acknowledge that they will be learning Docker container technologies.
- Acknowledge that they will be learning the Linux command line.
- Acknowledge that they will be learning the IBM Spectrum LSF job scheduler.
- Acknowledge that they will using a shared computing environment and that their workloads may impact others.
- Agree to be mindful of their workloads and strive to work with RIS if and when workloads negatively impact the cluster.

The use of Docker containers affords users the ability to run any software that can be built into a container. This is not 
fundamentally different than running arbitrary code downloaded from the Internet, which has been possible in any shared 
computing environment.

Users:
- Acknowledge the risks of running code obtained from unverified sources.
