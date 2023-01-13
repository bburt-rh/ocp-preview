# ocp-preview

This is a script to build and deploy OpenShift docs using `asciibinder`. 

Using one of the flags, you can either build locally or build locally and then copy the full build to a Red Hat file share server for remote access.

The script must be run from within your local `openshift-docs` directory, but the script itself should be located outside of this directory.

## Prerequisites

* You have a installed `asciibinder`.
* You have set up your local `openshift-docs` repo.
* For copying a build to a Red Hat file share server, you must request access from Red Hat IT. You will then be provided access to the server -- for example `file.emea.redhat.com`. Once you have access, configure passwordless SSH access to the server.

## Installation 

* Copy `ocp-preview` script to `/usr/local/bin`
* `chmod a+x /usr/local/bin/ocp-preview`
* Create a config file: `~/.ocp-preview` and update with your file server config details, for example:

```
[user]
    name = aireilly
[server]
    name = file.emea.redhat.com
[repo]
    name = /home/aireilly/openshift-docs
```

Using the `ocp-preview` script:

```
Usage: ocp-preview [OPTION] [DISTRO]
Usage: [DISTRO] is optional, build default is `openshift-enterprise`. Specify `all` to build all distros.
-b, --build
               does a full clean build and rsync. Use this option if your PR does not update an assembly.
-r, --refresh
               builds and rsyncs updated assemblies only.
-s, --silent-refresh
               builds and rsyncs updated assemblies, no preview pop up.
-l, --local-build
               does a full clean build locally, does not rsync. Use this option if your PR does not update an assembly.
-f, --local-refresh
               builds and updated assemblies locally, does not rsync.
-c, --local-refresh-silent
               builds and updated assemblies locally, does not rsync, no preview pop up.
-d, --delete
               deletes the current pull request build from the file server.
```
