# Docker Image - kube-tools

Docker Image packaged with Kubernetes troubleshooting tools:

This image contains the following tools to help troubleshoot Kubernetes problems:

 - kubectl - for API troubleshooting
 - dig & nslookup - for DNS troubleshooting
 - nc - for routing troubleshooting
 - curl - for http request troubleshooting


## Available Tags

Alpine Linux - `latest`


## Basic Usage

Create the Pod Spec `kube-tools.yml`:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: kube-tools
  namespace: default
spec:
  containers:
    - name: kube-tools
      image: fortejas/kube-tools
      command:
        - sleep
        - 24h
```

Launch the pod into your cluster:

```bash
# Deploy the pod to the your Kubernetes cluster
$ kubectl apply -f kube-tools.yml

# Exec into the pod to start performing troubleshooting
$ kubectl exec -it kube-tools -- ash
```

## Clean Up

Once you've finished working with this pod you can delete the pods:

```
$ kubectl delete pod --wait=false kube-tools
```
