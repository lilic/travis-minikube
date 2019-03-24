[![Build Status](https://travis-ci.org/LiliC/travis-minikube.svg?branch=master)](https://travis-ci.org/LiliC/travis-minikube)

# travis-minikube

Quick example of running [minikube](https://github.com/kubernetes/minikube) on [Travis CI](https://travis-ci.org/) with [Kubernetes](https://github.com/kubernetes/kubernetes) version `1.13.0`.
To read more in detail check out my [guest blog post](https://blog.travis-ci.com/2017-10-26-running-kubernetes-on-travis-ci-with-minikube) on the Travis CI blog.

To switch Kubernetes cluster versions just replace the `1.13.0` version in the `.travis.yml` file.

Note that [RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) is not enabled on this cluster by default. To enable RBAC, you need to start minikube with the `--extra-config=apiserver.authorization-mode=RBAC` flag.
Starting Minikube with RBAC enabled requires the appropriate RBAC roles to be created in the `kube-system` namespace, so all components work as expected. One of the possible solutions is to give the `default` ServiceAccount in the `kube-system` namespace the `cluster-admin` permissions. For more details see the [issue #1722](https://github.com/kubernetes/minikube/issues/1722).
