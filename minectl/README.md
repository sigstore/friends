# `minectl 🗺`️️

`minectl 🗺`️️ is a cli, written in golang, to creating Minecraft server on different cloud provider.

Currently, it supports 13 differen cloud providers and with Ubuntu [Mutipass](https://multipass.run/) even a local
deploy option.

As `minectl 🗺` interacts with cloud providers, we want to ensure that everything is as public as possible. From the
code, to the dependencies and the generation of the final binary.

**That's why we use `cosign` to keyless sign our binaries and container images.**

https://github.com/dirien/minectl
