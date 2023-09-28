### Scheduling

Key learnings in this section:

- How are pods assigned to nodes?  How can we force assign them?
- How are labels and selectors related?
- Taints and Tolerations
- Node Selectors and Affinities
- Taints and Tolerances vs Node Affinity
  - We can use a combination of taints, tolerances, and affinities together
- Resource Requirements and Limits
- Limit Ranges and Resource Quotas
- DaemonSets
- Static Pods
  - Static pods are created by the kubelets from on-disk manifest files (e.g. /etc/kubernetes/manifests)
    on their respective nodes. This is how pods are create on the controlplane.  Just like DaemonSets, static pods are ignored by
	the Scheduler.
  - Static pods can be viewed by running $docker ps (or crictl ps), and are created with the name
	of their assigned node appended, e.g. kube-scheduler-controlplane
- Multiple Schedulers
  - If you choose to use custom schedulers, each scheduler has its own service and manifest file.
    You can run an additional/custom scheduler as a pod.  You can also create deployments.
  - https://kubernetes.io/docs/tasks/extend-kubernetes/configure-multiple-schedulers/
  - We can look for scheduling events with the ***kubectl get events -o wide*** command.
  - We can also check logs for the individual scheduler.
- Configuring Scheduler Profiles
  - https://github.com/kubernetes/community/blob/master/contributors/devel/sig-scheduling/scheduling_code_hierarchy_overview.md
  - https://kubernetes.io/blog/2017/03/advanced-scheduling-in-kubernetes/
  - https://jvns.ca/blog/2017/07/27/how-does-the-kubernetes-scheduler-work/
  - https://stackoverflow.com/questions/28857993/how-does-kubernetes-scheduler-work
  