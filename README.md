# Portails4

Portals4 is a Network Programming Interface which allows high-performance network communication.
This implementation uses UDP as a transport layer, other transports can be implemented easily.


This repository has been created following the Sandia specification for Portals 4.3.
All the documentation about Portals functions can be found [on Sandia's website](https://www.sandia.gov/app/uploads/sites/144/2023/03/portals43.pdf).

## How to build
Run the following commands to build the library :
```
$ meson setup build
$ cd build
$ ninja
```

## Configuring the Interface IP

You can set the interface IP address by exporting the `NET_IP` environment variable. 
If `NET_IP` is not set, the default IP `127.0.0.x` will be used.

To specify the interface IP, use the following command in your terminal:

```bash
export NET_IP=192.168.50.1
```

## How to test
A [examples](./examples) folder is present on the root of the project.

Export NET_IP (e.g export NET_IP=192.168.50.1) enviroment variable to choose Interface IP default 127.0.0.x.  

Some examples using Portals functions can be found. To execute them:
```
$ cd build
$ ./examples/<name of the example>
```

To execute all tests :
```
$ cd build
$ ninja
$ meson test
```

## Architecture

The project is divided in 4 layers :
- The **Portals** layer which is the front-end exposing the Portals API,
- The **swptl** layer which makes the link between the back-end and the front-end layer. It implements the logic of Portals (as the events generation, triggered operation management, reception matching, ...),
- The **bximsg** layer which is used for retransmission and packetization,
- The **bxipkt layer** which is the transport layer.

The current version of Portails4 implements UDP transport communication.

## About

This repository is named Portails4 which means Portals4 in French.
