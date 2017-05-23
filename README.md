# Swift with Vapor Playground for Docker

This image is not intended for deployment, but for development, unlike [vapor-community/docker](https://github.com/vapor-community/docker).

The [Vapor](https://docs.vapor.codes/2.0/getting-started/install-on-ubuntu/) APT repo is applied to Ubuntu 16.04 "Xenial "

You can find the Docker Hub repo [here](https://hub.docker.com/r/bignerdranch/swift-vapor-playground/).

# Usage

## Pull the Docker Image From Docker Hub

```bash
docker pull bignerdranch/swift-vapor-playground
```

## Create a Container from the Image and Attach To It

```bash
docker run --privileged -i -t --name vapor_is_nerdy bignerdranch/swift-vapor-playground:latest bash
```

## To Start and Attach Your Image Later:

Start your image with name `vapor_is_nerdy`

```bash
docker start vapor_is_nerdy
```

and then attach to it:

```bash
docker attach vapor_is_nerdy
```

## Running an Ephemeral Image

```bash
docker run --rm -v ${PWD}:/swift -w /swift "bignerdranch/swift-vapor-playground:latest" swift test
```

* Takes the current directory and mounts it to `/swift` in a fresh container.
* Boots the container and attaches to it.
* Executes `swift test`, relaying all console output non-interactively.
* Exits and tears down the container when the commeand finishes.

## License

Licensed under [MIT](LICENSE.md).
