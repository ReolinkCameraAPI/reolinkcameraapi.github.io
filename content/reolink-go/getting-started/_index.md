---
title: "Getting Started"
date: 2020-12-18T03:54:48+02:00
draft: false
weight: 1
tags: ["getting started", "installation", "contributing"]
---

## Installation

### From source

    git clone https://github.com/ReolinkCameraAPI/reolinkapigo.git

### Using go get

    go get -u github.com/ReolinkCameraAPI/reolinkapigo

## Using

Implement a "Camera" object by passing it an IP address, Username and Password. By instantiating the object, it will try
retrieve a login token from the Reolink Camera. This token is necessary to interact with the Camera using other
commands.

    import "github.com/ReolinkCameraApi/reolinkapigo"

    // This can throw an error due to the API trying to authorise with the camera
    // to retrieve the necessary token for future requests.
	camera, err := pkg.NewCamera("foo", "bar", "192.168.1.100")

    // now call any of the supported api's by passing it it's resthandler
    ok, err := camera.API.FormatHdd(0)(camera.RestHandler)
