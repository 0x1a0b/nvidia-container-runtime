# Repository configuration

In order to setup the nvidia-container-runtime repository for your distribution, follow the instructions below.

If you feel something is missing or requires additional information, please let us know by [filing a new issue](https://github.com/NVIDIA/nvidia-container-runtime/issues/new).

## Ubuntu distributions (Xenial x86_64)

```bash
curl -L https://nvidia.github.io/nvidia-container-runtime/gpgkey | \
sudo apt-key add -
sudo tee /etc/apt/sources.list.d/nvidia-container-runtime.list <<< \
"deb https://nvidia.github.io/libnvidia-container/ubuntu16.04/amd64 /
deb https://nvidia.github.io/nvidia-container-runtime/ubuntu16.04/amd64 /"
sudo apt-get update
```

## CentOS distributions (RHEL7 x86_64)

```bash
sudo tee /etc/yum.repos.d/nvidia-container-runtime.repo <<EOF
[libnvidia-container]
name=libnvidia-container
baseurl=https://nvidia.github.io/libnvidia-container/centos7/x86_64
repo_gpgcheck=1
gpgcheck=0
enabled=1
gpgkey=https://nvidia.github.io/libnvidia-container/gpgkey
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt

[nvidia-container-runtime]
name=nvidia-container-runtime
baseurl=https://nvidia.github.io/nvidia-container-runtime/centos7/x86_64
repo_gpgcheck=1
gpgcheck=0
enabled=1
gpgkey=https://nvidia.github.io/nvidia-container-runtime/gpgkey
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
EOF
```

