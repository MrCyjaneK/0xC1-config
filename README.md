# 0xC1 configuration

 - `runners/` - Runners are a base to run more complicated CI tasks, a runner can be something that build a `golang` program, something that package a .deb or a plain `debian:stable` with some scripts added to it. We run `docker build --platform <platform> -t 0xC1_<directory name>:<platform> .` inside of it.
    - `archlist` - list of all architectures that the build will target (`sudo apt install qemu-user-static` and `docker run --privileged --rm docker/binfmt:a7996909642ee92942dcd6cff44b9b95f08dad64`)
    List of possible platforms: `linux/arm64`, `linux/arm`, `linux/arm/v6`, `linux/386`, `linux/amd64` <!-- Probably incomplete, I can't find a full list.. but you get the idea. -->
 - `jobs/` - Under this directory you put all configurations for all your jobs, one in each file.