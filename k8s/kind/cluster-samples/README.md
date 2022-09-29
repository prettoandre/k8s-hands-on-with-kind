# My first clusters with kind single node: 

kind create cluster --name [cluster-name]

Kind get clusters # look all clusters 


# Get kubernetes context: 

kubectl cluster-info --context [cluster-name]

# Kind create cluster wiht config file: 

kind create cluster --name [cluster-name] --config [configuration-file.yaml]  


# Kubernetes versions to use with kind: 

https://github.com/kubernetes-sigs/kind/releases

# Images built for this release:

1.25: kindest/node:v1.25.2@sha256:9be91e9e9cdf116809841fc77ebdb8845443c4c72fe5218f3ae9eb57fdb4bace
1.24: kindest/node:v1.24.6@sha256:97e8d00bc37a7598a0b32d1fabd155a96355c49fa0d4d4790aab0f161bf31be1
1.23: kindest/node:v1.23.12@sha256:9402cf1330bbd3a0d097d2033fa489b2abe40d479cc5ef47d0b6a6960613148a
1.22: kindest/node:v1.22.15@sha256:bfd5eaae36849bfb3c1e3b9442f3da17d730718248939d9d547e86bbac5da586
1.21: kindest/node:v1.21.14@sha256:ad5b7446dd8332439f22a1efdac73670f0da158c00f0a70b45716e7ef3fae20b
1.20: kindest/node:v1.20.15@sha256:45d0194a8069c46483a0e509088ab9249302af561ebee76a1281a1f08ecb4ed3
1.19: kindest/node:v1.19.16@sha256:a146f9819fece706b337d34125bbd5cb8ae4d25558427bf2fa3ee8ad231236f2