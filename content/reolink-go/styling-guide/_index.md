---
title: "Styling Guide"
date: 2020-12-18T03:59:35+02:00
draft: false
tags: ["styling guide", "go standards"]
---

### Styling and Standards

Golang project structure based off of https://github.com/golang-standards/project-layout

Writing functions/structs with a lot of parameters

    function HasManyParameters(
            param1 string,
            param2 int,
            param3 bool,
            ...
            param100 *Foo,
    ) {
       // Write your code here
    }

All variables are camelCase

    var someVariable1 string

Package names are all lowercase and if two or more words, camelCase

    package foo
    package fooBar

Go files are lowercase and if two or more words, snake_case

    foo.go
    foo_bar.go
