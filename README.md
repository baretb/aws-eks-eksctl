# Deploy EKS via eksctl

## Pre-requirements
- [eksctl](https://github.com/weaveworks/eksctl)
- [awscli](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)

## Calculate max pod for instance types
To calculate max pod via [max-pods-calculator.sh](max-pods-calculator.sh), follow the steps below.

```sh
chmod +x max-pods-calculator.sh
./max-pods-calculator.sh --instance-type m5.large --cni-version 1.9.0-eksbuild.1
```
Run the script, replacing m5.large with the instance type that you plan to deploy and 1.9.0-eksbuild.1 with your Amazon VPC CNI add-on version.

##  Create the cluster
```sh
eksctl create cluster -f my-cluster.yaml
```

## Dry run
```sh
eksctl create cluster -f my-cluster.yaml --dry-run
```

## Delete the cluster
```sh
eksctl delete cluster -f my-cluster.yaml
```

## eksctl config file schema
- [Schema](https://eksctl.io/usage/schema/)
