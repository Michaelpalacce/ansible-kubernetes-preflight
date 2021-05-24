A simple ansible role that installs a specific version of kubernetes

This package closely follows the guide at: https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/

If you want to use Helm to manage your K8S cluster, you can include the role `michaelpalacce.helm`.

# Important
This roles does NOT install a CRI. You must install one beforehand. Consider adding `michaelpalacce.docker` role to install docker as a cri.

# Supported variables

~~~
check_version_exists
~~~
Checks if the version given actually exists. Generally should be safe to leave to yes, but you can disable this if the check is not valid.
Defaults to: `yes`.

~~~
k8s_version
~~~
The Kubernetes binaries version to install
For a list of available versions run: `curl -s https://packages.cloud.google.com/apt/dists/kubernetes-xenial/main/binary-amd64/Packages | grep 'Package: kubelet' -A 2 | grep 'Version' | awk '{print $2}'`
Defaults to: `1.21.1-00`
