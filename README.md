[![Build Status](https://travis-ci.org/LiliC/travis-minikube.svg?branch=master)](https://travis-ci.org/LiliC/travis-minikube)

# travis-minikube

Quick example of running [minikube](https://github.com/kubernetes/minikube) on [Travis CI](https://travis-ci.org/) with [Kubernetes](https://github.com/kubernetes/kubernetes) version `1.9.0`.
To read more in detail check out my [guest blog post](https://blog.travis-ci.com/2017-10-26-running-kubernetes-on-travis-ci-with-minikube) on the Travis CI blog.

Other examples of different Kubernetes versions can be found in the following branches:
- For `1.10.0` Kubernetes example see the [minikube-26-kube-1.10](https://github.com/LiliC/travis-minikube/tree/minikube-26-kube-1.10) branch.
- For the `1.12.0` Kubernetes example see the [minikube-30-kube-1.12](https://github.com/LiliC/travis-minikube/tree/lili/minikube30-k8s12) branch which is derived from the [xenial](https://github.com/LiliC/travis-minikube/tree/kubeadm/xenial) branch.

Note that [RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) is not enabled on this cluster by default. To enable RBAC, you need to start Minikube with the `--extra-config=apiserver.Authorization.Mode=RBAC` flag.
Starting Minikube with RBAC enabled requires the appropriate RBAC roles to be created in the `kube-system` namespace, so all components work as expected. One of the possible solutions is to give the `default` ServiceAccount in the `kube-system` namespace the `cluster-admin` permissions. For more details see the [issue #1722](https://github.com/kubernetes/minikube/issues/1722).
