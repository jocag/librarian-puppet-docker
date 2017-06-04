[![Build Status](https://travis-ci.org/jocag/librarian-puppet-docker.svg?branch=master)](https://travis-ci.org/jocag/librarian-puppet-docker)  [![Docker Automated build](https://img.shields.io/badge/docker%20build-automated-blue.svg)](https://hub.docker.com/r/jocag/librarian-puppet-docker/)

# Librarian Puppet Base Image
## Summary
This repository contains a dockerised [librarian puppet](https://github.com/voxpupuli/librarian-puppet) installation published to the public [Docker Hub](https://hub.docker.com/r/jocag/librarian-puppet-docker/) registry using automated builds.

The Dockerfile for this image can be found in the Github repository [librarian-puppet-docker](https://github.com/jocag/librarian-puppet-docker)

## How to Obtain This Image
You can simply pull this image from [Docker Hub](https://hub.docker.com/r/jocag/librarian-puppet-docker) using one of the available tags.

`$docker pull jocag/librarian-puppet-docker:latest`

## Building Your Own Container Based on an Image (Optional)
To build this image, simply pull this repository and cd into the directory that contains your preferred Dockerfile and run:  

`$docker build -t librarian-puppet-docker:<tag> .`

## Configuration
There are base images available currently for CentOs 7.x and Ubuntu 16.04 systems, using both the latest stable version of Librarian Puppet.

## Usage
It is **required** to have a Puppetfile in your current directory.
Then, you need to mount the volume for librarian puppet as `/puppet`

```
$cd puppet  

$docker run --rm -v "$PWD":/etc/puppet -w /etc/puppet docker.io/jocag/librarian-puppet-docker install --verbose
```

You can use this image to download and compile your modules from [Puppet Forge](https://forge.puppet.com/) or any other repository as it is specified in your Puppetfile.

## License
This software is shipped under the MIT License. Feel free to copy, modify or add extra software for your own purposes.  
Forks and Pull requests are welcome!
