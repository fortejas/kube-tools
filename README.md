# Docker Image - kube-tools

Docker Image packaged with Kubernetes troubleshooting tools:

This image contains the following tools to help troubleshoot Kubernetes problems:

 - kubectl - for API troubleshooting
 - dig & nslookup - for DNS troubleshooting
 - nc - for routing troubleshooting


## Available Tags

Alpine Liunux - `latest`


## Basic Usage

```
# Deploy the pod to the your Kubernetes cluster
$ cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: Pod
metadata:
  name: kubectl-tools
  namespace: default
spec:
  containers:
    - name: tools
      image: fortejas/kube-tools
      command:
        - sleep
        - 24h
EOF

# Exec into the pod to start performing troubleshooting
$ kubectl exec -it kubectl-tools -- ash
```