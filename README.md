# Docker Monitoring on Windows
Monitor your Docker containers using cAdvisor on Windows

Refer to this medium article for more details
https://medium.com/@mahesh.mahadevan/monitoring-docker-containers-on-windows-using-prometheus-grafana-c32bbb7ed04

## Pre-requisites

* docker on windows
* docker-compose

## Setup and Install

Clone this repo on your Windows OS machine where Docker is up and running.

Some blogs would suggest mounting “rootfs” volume for cAdvisor container. Remember, docker in Windows runs inside a Hyper-V MobyLinux VM. If you keep “rootfs” volume mapping on Windows, you will end up with a failure on running your docker-compose up command since rootfs is not available on the Windows docker env. You can safely skip this volume map setting in your docker-compose file.
When using docker-compose you will also need to set another Env variable from your Windows powershell to convert your windows paths present in your docker-compose volume mappings. On your Powershell run this command $Env:COMPOSE_CONVERT_WINDOWS_PATHS=1

Open Power shell window and run this command from current directory of this repository.

```docker-compose up```

Goto http://localhost:8080 for cAdvisor dashboard.
