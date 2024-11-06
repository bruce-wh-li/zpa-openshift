# ZPA App Connector Openshift Helm Chart

This repository contains the official ZPA App Connector Helm chart for Openshift.

## Prerequisites

Helm 3 \
Openshift 4.11 \
Metrics Server

## Docker image

This process assumes you have full network access to the docker images hosted on

https://hub.docker.com/u/zscaler

<br/><br/>

## Installation

In order to install the zpa-app-connector-openshift please use the below steps

1. Login as kubeadmin and switch to default project. You will be on the default project when you login as kubeadmin unless there is a change in the settings. So you would not need any command to move to default project. \
If you are not on the default, please use the command\
    `oc project default`


2. Add the Helm repository

   `helm repo add https://dist.zscaler.private.com/helm-charts/openshift/`


3. From the default namespace, install the Helm Chart by using the following commands:

    `helm install [NAME] [CHART] [flags]`

    `helm install [NAME] --set zsglobal.provisionkey.value="<provision_key>"  repo_name/chart_name`

Below is an example of successfully installing the Helm Chart:

    helm install zpa-connector --set zsglobal.provisionkey.value="1|api.private.zscaler.com|68F0AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ/68F0AOEgpcG8McLmwdborq2m6v2 A5oNEpSztJ/68F0AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ/68F0AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ/68F0 AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ/68F0AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ/68F0AOEgpcG8McLmwdb orq2m6v2A5oNEpSztJ/68F0AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ/68F0AOEgpcG8McLmwdborq2m6v2A5oNEpS ztJ/68F0AOEgpcG8McLmwdborq2m6v2A5oNEpSztJ==" zpa-helm-repo/zpa-app-connector-openshift

    NAME: zpa-connector
    LAST DEPLOYED: Wed May 10 16:21:02 2023
    NAMESPACE: default
    STATUS: deployed
    REVISION: 1
    TEST SUITE: None
    NOTES:
    Thank you for installing zpa-app-connector-openshift.
    To learn more about the release, try:

    $ helm status zpa-connector

    $ helm get all zpa-connector

     
You can retrieve the provisioning key from the [ZPA Admin Portal](https://admin.private.zscaler.com/). To learn more, see [About App Connector Provisioning Keys](https://help.zscaler.com/zpa/about-connector-provisioning-keys).