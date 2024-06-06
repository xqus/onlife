---
title: "Cleaning up after Docker"
date: 2024-06-06T20:38:00+02:00
draft: false
tags:
- docker
- server
---

## From the [Docker documentation](https://docs.docker.com/config/pruning/)

> Docker takes a conservative approach to cleaning up unused objects (often referred to as "garbage collection"),
> such as images, containers, volumes, and networks. These objects are generally not removed unless you explicitly
> ask Docker to do so. This can cause Docker to use extra disk space. For each type of object, Docker provides a
> prune command. In addition, you can use docker system prune to clean up multiple types of objects at once.

## Pruning data
 ```
$ docker system prune

WARNING! This will remove:
        - all stopped containers
        - all networks not used by at least one container
        - all dangling images
        - unused build cache
        
Are you sure you want to continue? [y/N] 
 ```

To also prune volumes, add the `--volumes` flag

 ## Pruning old data

The following command removes items older than 24 hours:

`$ docker system prune --filter "until=24h"`