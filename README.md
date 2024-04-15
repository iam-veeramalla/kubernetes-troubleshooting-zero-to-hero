# kubernetes-troubleshooting-zero-to-hero
Learn how to troubleshoot the most common Kubernetes Issues

## Day-01

### ImagePullBackOff

When a kubelet starts creating containers for a Pod using a container runtime, it might be possible the container is in Waiting state because of ImagePullBackOff.

The status ImagePullBackOff means that a container could not start because Kubernetes could not pull a container image for reasons such as 

- Invalid image name or 
- Pulling from a private registry without imagePullSecret. 

The BackOff part indicates that Kubernetes will keep trying to pull the image, with an increasing back-off delay.

Kubernetes raises the delay between each attempt until it reaches a compiled-in limit, which is 300 seconds (5 minutes).


## Day-02

### CrashLoopBackOff

This state occurs when the container within the pod repeatedly crashes shortly after starting up. Kubernetes continuously restarts the pod, but if the container keeps crashing, it enters a backoff state where it waits before attempting to restart the pod again. This typically indicates problems within the container itself, such as application errors, misconfigurations, or resource constraints.
