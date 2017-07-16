# MongoDB BOSH release

This MongoDB deployment is intended for use with BOSH 2 deployment  

## Prerequisites

1. A deployment of [BOSH](https://github.com/cloudfoundry/bosh)
2. Tested environment

Name | Version
------------ | -------------
MongoDB | 3
BOSH | 261.1

## Features

1. Bosh 2 deployed

2. Single node

3. service instances represent logical databases on the shared server  

4. Authentication supported

5. No service broker

## How to use

1. You can follow the [bosh document](http://bosh.io/docs) to install BOSH firstly

2. Create and upload release

    `bosh create-release --name=mongodb --version=1.0.0 --final --force`

    `bosh upload-release`

3. Create manifest file. You can find an example using BOSH cloud-config in mongodb-deployment.manifest under deployment folder as reference

4. Deploy

    `bosh -n deploy -d mongodb <deployment_manifest>`

    `bosh run-errand -d mongodb create-admin-user`

5. When it completes ,you can check mongodb node using

    `bosh vms`

6. Connect from a mongo client

    `mongo <mongodb ip>:<port default is 27017>/admin -u admin -p admin`

## Contribution

Welcome to contribute through pull request  
