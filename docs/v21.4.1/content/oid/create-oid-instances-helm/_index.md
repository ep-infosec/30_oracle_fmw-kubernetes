+++
title = "Create Oracle Internet Directory Instances Using Helm"
date = 2019-04-18T06:46:23-05:00
weight = 4
pre = "<b>4. </b>"
description=  "This document provides steps to create Oracle Internet Directory instances using Helm Charts."
+++

1. [Introduction](#introduction)
1. [Install Helm](#install-helm)
1. [Deploy an Application using the Helm Chart](#deploy-an-application-using-the-helm-chart)
1. [Undeploy an Application using the Helm Chart](#undeploy-an-application-using-the-helm-chart)
1. [Helm Chart(s) for Oracle Internet Directory](#helm-charts-for-oracle-internet-directory)

### Introduction

This chapter demonstrates how to deploy Oracle Internet Directory 12c instance(s) using the Helm package manager for Kubernetes. Helm Chart(s) described here can be used to facilitate installation, configuration, and environment setup within a Kubernetes environment.

### Install Helm

Helm can be used to create and deploy the Oracle Internet Directory resources in a Kubernetes cluster. For Helm installation and usage information, refer to the [README](https://github.com/helm/helm).

#### Deploy an Application using the Helm Chart

The `helm install` command is used to deploy applications to a Kubernetes environment, using the Helm Chart supplied.

```
$ helm install [Deployment NAME] [CHART Reference] [flags]
```

For example:

```
$ helm install oid oid --namespace oidns
```

#### Undeploy an Application using the Helm Chart

To uninstall an application deployed using a Helm chart you need to identify the release name and then issue a delete command:

To get the release name:

```
$ helm --namespace <namespace> list
```

For example:

```
$ helm --namespace oidns list
NAME                    NAMESPACE       REVISION        UPDATED                                 STATUS          CHART                   APP VERSION
oid                     oidns           1               2020-03-31 10:37:30.616927678 -0700 PDT deployed        oid-12.2.1.4.0          12.2.1.4.0
```

To delete the chart:

```
$ helm uninstall --namespace <namespace> <release>
```

For example:

```
$ helm uninstall --namespace oidns oid
release "oid" uninstalled
```

#### Helm Chart(s) for Oracle Internet Directory

The following list provides Helm charts for deploying Oracle Internet Directory in a Kubernetes environment. Helm charts provided can be found in the project at the following location:

`https://github.com/oracle/fmw-kubernetes/tree/master/OracleInternetDirectory/kubernetes/helm`

Details about each Helm Chart can be found in the relevant README listed below:

* [oid]({{< relref "/oid/create-oid-instances-helm/oid" >}}) : A Helm chart for deployment of Oracle Internet Directory instances on Kubernetes.
