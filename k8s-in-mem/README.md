# Instructions

Get openshift 3.11 running (for knative), and install the following addons:

```
git clone https://github.com/openshift-cloud-functions/minishift-addons.git
minishift addons install minishift-addons/istio
minishift addons install minishift-addons/knative
minishift addons install minishift-addons/knative-eventing
minishift addons apply istio  # this will take a while, so be patient
minishift addons apply knative
minishift addons apply knative-eventing
```

## k8s events

Install the k8s-source sample addon:

```

git clone -b k8s-in-mem --single-branch git@github.com:matzew/ocf-addons.git
minishift addons install minishift-addons/k8s-in-mem 
minishift addons apply k8s-in-mem
```

Query for the pods: (`oc get pods -n myproject`)

and read the logs:

```
oc logs -f message-dumper-00001.......... -c user-container
```

