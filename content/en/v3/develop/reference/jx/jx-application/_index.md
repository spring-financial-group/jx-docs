---
title: jx application
linktitle: application
type: docs
description: 
aliases:
  - jx-application
---

## jx-application

command for viewing deployed Applications across Environments

***Aliases**: application,version,versions*

### Usage

```
jx-application
```

### Synopsis

Display applications across environments.

### Examples

  # List applications, their URL and pod counts for all environments
  jx get applications
  
  # List applications only in the Staging environment
  jx get applications -e staging
  
  # List applications only in the Production environment
  jx get applications -e production
  
  # List applications only in a specific namespace
  jx get applications -n jx-staging
  
  # List applications hiding the URLs
  jx get applications -u
  
  # List applications just showing the versions (hiding urls and pod counts)
  jx get applications -u -p

### Options

```
  -b, --batch-mode         Runs in batch mode without prompting for user input
  -e, --env string         Filter applications in the given environment
  -h, --help               help for jx-application
  -n, --namespace string   Filter applications in the given namespace
  -p, --pod                Hide the pod counts
  -w, --preview            Show preview environments only
  -u, --url                Hide the URLs
      --verbose            Enables verbose output. The environment variable JX_LOG_LEVEL has precedence over this flag and allows setting the logging level to any value of: panic, fatal, error, warn, info, debug, trace
```

### SEE ALSO

* [jx-application version](jx-application_version)	 - Displays the version of this command

###### Auto generated by spf13/cobra on 3-Jul-2020