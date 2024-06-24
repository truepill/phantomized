# Fork of PhantomJS

This fork is to unbreak the Docker.base-image build in TPOS monorepo. Would be nice to move away from `html-pdf` package so we no longer depend on PhantomJS but, until then, we have this.

# Stop using PhantomJS

https://dustinblackman.com/posts/stop-using-phantomjs/

# Phantomized

An automated build to tar up dynamic ELFs required by PhantomJS using Dockerized. This makes dockerizing PhantomJS with base images like Alpine Linux easy.

This build does not include the phantomjs binary itself so make it easier for application that install PhantomJS through other sources like [npm](https://github.com/Medium/phantomjs). This is based off the work of [docker-phantomjs2](https://github.com/fgrehm/docker-phantomjs2).

## How To

Adding this line to your Dockerfile applies all files to your docker image. You can find a production example [here](https://github.com/Gravebot/Gravebot/blob/master/Dockerfile).

```bash
curl -Ls "https://github.com/dustinblackman/phantomized/releases/download/2.1.1a/dockerized-phantomjs.tar.gz" | tar xz -C /
```

## Build from source

Make sure your have your docker environment set up correctly, and run the build script. Running the build script will build the docker container and copy the newly created `dockerized-phantomjs.tar.gz` to your current working directory.

```bash
./build.sh
```
