# Pandockerize

<img align="left" src="./pictures/docker-logo.png" width="112">

[Pandoc](https://pandoc.org) Docker Image built with Ubuntu Trusty. Available on [Github](https://github.com/FatihBozik/pandockerize) and [Docker Hub](https://hub.docker.com/r/bozikfatih/pandoc/).

<br/></br><br/>

## Basic Usage

* Build Docker Image using Dockerfile
  ```shell
  git clone https://github.com/FatihBozik/pandockerize.git
  cd pandockerize && docker build -t bozikfatih/pandoc .
  ```
<br/>

* Run container from the built image.
  ```shell
  alias pandoc='docker run -ti \
                           --name pandoc \
                           --rm -v ${PWD}:/source \
                           --rm -v /home/fatihbozik/.local/share/fonts:/usr/local/share/fonts \
                           --rm bozikfatih/pandoc'
  ```     

  ```shell                           
  $ pandoc -v
  pandoc 2.1.3
  Compiled with pandoc-types 1.17.4.2, texmath 0.10.1.1, skylighting 0.7.0.2
  Default user data directory: /root/.pandoc
  Copyright (C) 2006-2018 John MacFarlane
  Web:  http://pandoc.org
  This is free software; see the source for copying conditions.
  There is no warranty, not even for merchantability or fitness
  for a particular purpose.
  ```
<br/>

* To bash into ubuntu container
  ```shell
  $ docker run -ti \
             --entrypoint "/bin/bash" \
             --name pandoc \
             --rm -v ${PWD}:/source \
             --rm -v /home/fatihbozik/.local/share/fonts:/usr/local/share/fonts \
             --rm bozikfatih/pandoc
  root@c30becbd8390:/source#               
  ```
