# k8sspider

K8S Spider is a quick power-up of Kubernetes inside a VM, on a flat L2, with Flannel overlay, KubeDNS and Metrics-server installed.

# Requirements

- Flat network L2
- Debian/Ubuntu variant
- Hostname in DNS for all node(s).

# Setting up on all nodes
    1. k8s-install.sh

## on the primary 
    1. k8s-new-master.sh and
    2. k8s-new-join-command.sh will print the token to be entered on the worker-node(s).

## on the secondary/secondaries

    1. kubeadm join $APISERVERIP --token $TOKEN --discovery-token-ca-cert-hash sha256:$DIGEST where

        TOKEN
        APISERVERIP
        DIGEST

        comes from the output of step #2 on the primary.