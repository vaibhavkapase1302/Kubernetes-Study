### kubectx
kubectx is a tool to switch between contexts (clusters) on kubectl faster.

```sh
$ kubectx -h
USAGE:
  kubectx                       : list the contexts
  kubectx <NAME>                : switch to context <NAME>
  kubectx -                     : switch to the previous context
  kubectx -c, --current         : show the current context name
  kubectx <NEW_NAME>=<NAME>     : rename context <NAME> to <NEW_NAME>
  kubectx <NEW_NAME>=.          : rename current-context to <NEW_NAME>
  kubectx -u, --unset           : unset the current context
  kubectx -d <NAME> [<NAME...>] : delete context <NAME> ('.' for current-context)
                                  (this command won't delete the user/cluster entry
                                   referenced by the context entry)
  kubectx -h,--help             : show this message
  kubectx -V,--version          : show version
```

```sh
$ kubectx
arn:aws:eks:ap-south-1:223530587197:cluster/facctum-dev-eks-cluster
arn:aws:eks:ap-south-1:494855333795:cluster/eks-demo-cluster
arn:aws:eks:ap-south-1:494855333795:cluster/my-eks-cluster
arn:aws:eks:ap-south-1:891377000934:cluster/facctum-stage-eks-cluster
arn:aws:eks:ap-south-1:891377087030:cluster/facctum-qa-eks-cluster
arn:aws:eks:eu-west-2:533267276219:cluster/barclays-dev-eks-cluster
arn:aws:eks:eu-west-2:905418413399:cluster/facctum-dev-eks-cluster
docker-desktop
```

```sh
$ kubectx arn:aws:eks:ap-south-1:891377000934:cluster/facctum-stage-eks-cluster
✔ Switched to context "arn:aws:eks:ap-south-1:891377000934:cluster/facctum-stage-eks-cluster".
```

### kubens
kubens is a tool to switch between Kubernetes namespaces (and configure them for kubectl) easily.

```sh
$ kubens -h
USAGE:
  kubens                    : list the namespaces in the current context
  kubens <NAME>             : change the active namespace of current context
  kubens -                  : switch to the previous namespace in this context
  kubens -c, --current      : show the current namespace
  kubens -h,--help          : show this message
  kubens -V,--version       : show version
```
