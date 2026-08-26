# TODO

- Understand Argo CD
- Understand K3d / k3s / k3c difference
- Install k3d
    - script to install docker and other software to run k3d in virtual machine
- Instal Argo CD
- what's the role of docker hub?

---

- Continous Integration
    - Docker Hub hosts application with 2 tagged versions

    - K3D:
        - Read more about Kubernetes namespaces (namespaces for  development workflow)
        - Namespace Dedicated for "Argo CD" named "Argo CD"
        - Namespace "dev", contains application which will be automatically deployed by Argo CD using online Github Repository
        - Public repository (ArgonautApp) holds the config files Argo CD syncs from

    - Application:
        - App image: https://hub.docker.com/r/wil42/playground with tags *v1* and *v2*

- Expected:
    - Change version from public Github repo, then see changes applied correctly
    - Argo CD Dashboard
    - Argo CD shows that application is sync with github after push

```console
$ k get ns
NAME      STATUS   AGE
argocd    Active   19h
dev       Active   19h

$ k get pods -n dev
NAME                              READY   STATUS    RESTARTS   AGE
wil-playground-65f745fdf4-d2l2r   1/1     Running   0          8m9s
$
```

# Ressources

- Rancher Meetup - May 2020 - Simplifying Your Cloud-Native Development Workflow With K3s, K3c and K3d
:
    https://www.youtube.com/watch?v=hMr3prm9gDM&ab_channel=Rancher

- Argo CD
    - https://argo-cd.readthedocs.io/en/stable/
    - https://argo-cd.readthedocs.io/en/stable/understand_the_basics/
    - https://argo-cd.readthedocs.io/en/stable/core_concepts/
    - https://dev.to/danielcristho/k3d-getting-started-with-argocd-5c6l