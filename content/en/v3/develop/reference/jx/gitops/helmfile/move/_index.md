---
title: jx gitops helmfile move
linktitle: move
type: docs
description: "Moves the generated template files from 'helmfile template' into the right gitops directory ***Aliases**: mv*"
aliases:
  - jx-gitops_helmfile_move
---

### Usage

```
jx gitops helmfile move
```

### Synopsis

Moves the generated template files from 'helmfile template' into the right gitops directory
  
The output of 'helmfile template' ignores the namespace specified in the 'helmfile.yaml' and there is a dummy top level directory. 

So this command applies the namespace to all the generated resources and then moves the namespaced resources into the config-root/namespaces/$ns/$releaseName directory and then moves any CRDs or cluster level resources into 'config-root/cluster/$releaseName' 

If supplied with --dir-includes-release-name then by default we will annotate the resources with the annotation 'meta.helm.sh/release-name' to preserve the helm release name

### Examples

  ```bash
  # moves the generated files in 'tmp' to the config root dir
  jx-gitops helmfile move --dir config-root --from tmp

  ```
### Options

```
      --annotate-release-name       if using --dir-includes-release-name layout then lets add the 'meta.helm.sh/release-name' annotation to record the helm release name (default true)
      --dir string                  the directory containing the generated resources
      --dir-includes-release-name   the directory containing the generated resources has a path segment that is the release name
  -h, --help                        help for move
      --invert-selector             inverts the effect of selector to exclude resources matched by selector
  -k, --kind stringArray            adds Kubernetes resource kinds to filter on. For kind expressions see: https://github.com/jenkins-x/jx-helpers/v3/tree/master/docs/kind_filters.md
      --kind-ignore stringArray     adds Kubernetes resource kinds to exclude. For kind expressions see: https://github.com/jenkins-x/jx-helpers/v3/tree/master/docs/kind_filters.md
  -o, --output-dir string           the output directory (default "config-root")
      --selector stringToString     adds Kubernetes label selector to filter on, e.g. -s app=pusher-wave,heritage=Helm (default [])
      --selector-target string      sets which path in the Kubernetes resources to select on instead of metadata.labels.
```



### Source

[jenkins-x-plugins/jx-gitops](https://github.com/jenkins-x-plugins/jx-gitops)
