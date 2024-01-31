# Custom SSH Exporter Helm Chart

This Helm chart provides a custom implementation of the ssh_exporter for Kubernetes environments. The original GitHub repository [treydock/ssh_exporter](https://github.com/treydock/ssh_exporter) couldn't be directly utilized in Kubernetes, so custom manifests and a Helm chart were created.

## Overview

Using a custom SSH export, you can check the SSH connection, run a specific command on the remote server, and check the connection with the obtained values.

| Kubernetes Resource   | Quantity |
|------------------------|----------|
| ConfigMap              | 2        |
| ServiceAccount         | 1        |
| Service                | 1        |
| Deployment             | 1        |


## Install
helm install ssh-exporter ./helm-chart-dir -n [namespace]

## ⚠️ Notice

* This custom SSH Exporter Helm Chart does not include an `_helpers` file as the structure is straightforward and doesn't require additional helper functions.
* The ssh exporter is an exporter that determines whether an ssh connection exists. It can be used like a script exporter, but if you want more functions, develop it.

