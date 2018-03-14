# ecs-jdk8

This repository builds a Docker image for applications using JDK8 on ECS. The
image is based on Alpine Linux but includes some extra libraries in order to
run the KPL and other things that require glibc.

In order, it:
* installs libraries (specifically libuuid for the KPL)
* installs tini
* exposes port 8080
* sets the entrypoint to '/sbin/tini -- /docker-entrypoint.sh'

Of note, it also bakes in the NewRelic agent and (TEMPLATED!!!) configuration
file.
