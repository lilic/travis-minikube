[![Build Status](https://travis-ci.org/LiliC/travis-minikube.svg?branch=master)](https://travis-ci.org/LiliC/travis-minikube)

# travis-minikube

Quick example of running [minikube](https://github.com/kubernetes/minikube) on [Travis CI](https://travis-ci.org/) with [Kubernetes](https://github.com/kubernetes/kubernetes) version `1.8.0`.
To read more in detail check out my [guest blog post](https://blog.travis-ci.com/2017-10-26-running-kubernetes-on-travis-ci-with-minikube) on the Travis CI blog.


To switch versions just replace the `1.8.0` version in the `.travis.yml` file. To run against RBAC enabled cluster add the `--extra-config=apiserver.Authorization.Mode=RBAC` flag to `minikube start` in the `.travis.yml`.
