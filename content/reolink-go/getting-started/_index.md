---
title: "Getting Started"
date: 2020-12-18T03:54:48+02:00
draft: false
weight: 1
tags: ["getting started", "installation", "contributing"]
---

## Installation

If `go get` is not working for you, please check out this amazing post about 
`GO111MODULE=ON` [here](https://dev.to/maelvls/why-is-go111module-everywhere-and-everything-about-go-modules-24k).

### Using go get

    GO111MODULE=on go get github.com/ReolinkCameraAPI/reolinkapigo@latest

A Specific version using `@v0.x.x`

    GO111MODULE=on go get -u github.com/ReolinkCameraAPI/reolinkapigo@v0.0.1


### From source

    cd $GOPATH
    mkdir -p src/github.com/ReolinkCameraAPI
    cd src/github.com/ReolinkCameraAPI
    git clone https://github.com/ReolinkCameraAPI/reolinkapigo.git

## Using

Implement a "Camera" object by passing it an IP address, Username and Password. By instantiating the object, it will try
retrieve a login token from the Reolink Camera. This token is necessary to interact with the Camera using other
commands.

    import "github.com/ReolinkCameraAPI/reolinkapigo"

    // This can throw an error due to the API trying to authorise with the camera
    // to retrieve the necessary token for future requests.
	camera, err := pkg.NewCamera("foo", "bar", "192.168.1.100")

    // now call any of the supported api's by passing it it's resthandler
    ok, err := camera.FormatHdd(0)(camera.RestHandler)
