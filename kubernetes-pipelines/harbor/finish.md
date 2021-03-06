# Lessons Learned #

Generally there are three ways to interact with container registries.

1. Public registries like DockerHub, Quay.io, gcr.io 
2. Private team registries that are within you organization, often hosted by your cloud provider 
3. Private registries that you or your team may be using on a local or private Kubernetes cluster or namespace.

This tutorial gives you a leg up for leveraging personal and local registries. This is ideal when you are prototyping or rapidly developing and testing a solution locally. Knowing how to quickly setup and use a private container is another technique you can pull out of your Kubernetes toolbox.

With these steps you have learned:

- &#x2714; how to install a private container on Kubernetes,
- &#x2714; how to install web interface to list the registry contents

## References ##

- [Registry source](https://github.com/docker/distribution)
- [Registry Helm chart](https://github.com/helm/charts/tree/master/stable/docker-registry)
- [Distribution and Registry 2.0](https://github.com/docker/distribution)
- [Registry Proxy](https://github.com/helm/charts/tree/master/incubator/kube-registry-proxy)
- [IBM MAX Breast Cancer Mitosis Detector](https://github.com/IBM/MAX-Breast-Cancer-Mitosis-Detector)
- [Deploying Deep-Learning Models to Kubernetes on IBM Cloud](https://medium.com/ibm-watson-data-lab/deploying-deep-learning-models-to-kubernetes-on-the-ibm-cloud-93d4a22cb2ab)

## Homage ##

Lost friend and father, [Bill Becker](https://vimeo.com/73274666). Male Breast Cancer Awareness Week is the third week of October.

------
![No Fluff Just Stuff](/javajon/courses/kubernetes-pipelines/registries/assets/nfjs.png "No Fluff Just Stuff")

For a deeper understanding of these topics and more join me, [Jonathan Johnson](https://nofluffjuststuff.com/conference/speaker/jonathan_johnson), for a transcendent experience on the [No Fluff Just Stuff Software Symposium Tour](https://nofluffjuststuff.com).
