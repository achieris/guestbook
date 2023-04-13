
#  guestbook

This project contains: 

* the guestbook helm chart repository. 
* dev and prod overlays with different values file. 


```
.
├── chart
│   ├── guestbook-0.0.1.tgz
│   ├── guestbook-0.0.2.tgz
│   ├── guestbook-sources
│   │   ├── charts
│   │   ├── Chart.yaml
│   │   └── templates
│   │       ├── deployment.yaml
│   │       ├── route.yaml
│   │       └── service.yaml
│   └── index.yaml
├── dev
│   ├── kustomization.yaml
│   └── values-dev.yaml
└── prod
    ├── kustomization.yaml
    └── values-prod.yaml
```

## Create a new version of the chart

### Requirements:
* helm installed

### Steps:

* Modify the template in the chart/guestbook-sources/templates. 

* Modify the chart/guestbook-sources/Chart.yaml file to change the version. 

* Create the new tgz and update the helm repo index:

```
cd chart

helm package guestbook-sources

helm repo index --url https://achieris.github.io/guestbook/chart/ .

```


