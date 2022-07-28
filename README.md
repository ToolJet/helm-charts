# ToolJet Helm Charreporepots
This repository contains helm charts for [ToolJet](https://github.com/ToolJet/ToolJet).\
Charts can be used to install ToolJet in a Kubernetes Cluster via [Helm v3](https://helm.sh).\
This setup comes with an included PostgreSQL server out of the box which is enabled by default. You can disable it and update `values.yml` with a different PostgreSQL server to be used with.

## Installation

### From helm repo
```bash
helm repo add tooljet https://tooljet.github.io/helm-charts
helm install tooljet tooljet/tooljet
```

### From the source
1) Clone the repo and `cd` into this directory
2) Run `helm dependency update`
3) Recommended but optional:\
Patch the values in `values.yaml` file (usernames & passwords, persistence, ...).
4) Run `helm install -n $NAMESPACE --create-namespace $RELEASE .`\
You need to replace these variables with your configuration values.
5) The database won't be seeded yet. For that, shell into the `tooljet` pod and run `npm run db:seed` in the `/app` folder. You can now login with user `dev@tooljet.io` and password `password`.


## Questions? Feedback?
[Join our Slack](https://join.slack.com/t/tooljet/shared_invite/zt-r2neyfcw-KD1COL6t2kgVTlTtAV5rtg)
