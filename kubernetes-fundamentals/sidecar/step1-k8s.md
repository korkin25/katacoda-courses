For this scenario, Katacoda has just started a fresh Kubernetes cluster for you. Verify it's ready for your use.

`kubectl version --short && \
kubectl get componentstatus && \
kubectl get nodes && \
kubectl cluster-info`{{execute}}

The [Helm](https://helm.sh/) package manager used for installing applications on Kubernetes is also available.

`helm version --short`{{execute}}

## Kubernetes Dashboard ##

You can control the cluster with the `kubectl` CLI tool or through the Kubernetes Dashboard. Because the dashboard can be accessed publicly, it is protected and requires the secret access token to sign in. Copy the token from this secret.

`export TOKEN=$(kubectl describe secret $(kubectl get secret | awk '/^dashboard-token-/{print $1}') | awk '$1=="token:"{print $2}') &&
echo -e "\n--- Copy and paste this token for dashboard access --\n$TOKEN\n---"`{{execute}}

To access the dashboard, click on the _Kubernetes Dashboard_ tab above the command line or from this link: https://[[HOST_SUBDOMAIN]]-30000-[[KATACODA_HOST]].environments.katacoda.com/. At the sign in prompt select _Token_ and paste in the token, you copied a moment ago.

> For Kubernetes clusters exposed to the public, *always* lock administration access including [access to the dashboard](https://www.wired.com/story/cryptojacking-tesla-amazon-cloud/).