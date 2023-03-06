---
title: 'Install Certwatcher'
date: 2019-02-11T19:27:37+10:00
draft: false
weight: 2
---

A step-by-step guide to installing and configuring Certwatcher.

<!--more-->

## Quickstart

Certwatcher is an SSL/TLS certificate monitoring tool, written in Go. This guide will walk you through the steps necessary to install and run.

###### Prerequisites
Before you start, you'll need to ensure that the following prerequisites are met:

- Go is installed on your system. You can download the latest version of Go from the official website: https://golang.org/dl/

- Git is installed on your system. You can download the latest version of Git from the official website: https://git-scm.com/downloads

###### Installation

To get started with Certwatcher, you'll need to clone the project repository. You can do this using Git by running the following command:

```bash

  git clone https://github.com/drfabiocastro/certwatcher
  cd certwatcher
  go build cmd/certwatcher/main.go
  sudo make install


```

###### Usage

To use Certwatcher, run the following command:

```bash
  ./certwatcher --help
```

##### Conclusion
Congratulations! You have successfully installed and run Certwatcher. You can now configure custom templates 1to monitor the SSL/TLS certificates