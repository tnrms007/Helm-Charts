# Custom SSH Exporter Helm Chart

This Helm chart provides a custom implementation of the ssh_exporter for Kubernetes environments. The original GitHub repository [treydock/ssh_exporter](https://github.com/treydock/ssh_exporter) couldn't be directly utilized in Kubernetes, so custom manifests and a Helm chart were created.

## Overview

The custom SSH exporter allows you to verify SSH connectivity and execute specific commands on remote servers. It's designed to be flexible, allowing you to define custom exporters if you require additional functionality beyond the standard SSH connectivity check.

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
* SSH Exporter is a tool designed to verify SSH connectivity and execute specific commands on remote servers. It functions as an exporter, allowing you to monitor and validate access to servers via SSH. If you require additional functionality or custom logic beyond the standard SSH connectivity check, SSH Exporter provides the flexibility to create custom exporters tailored to your specific needs.
