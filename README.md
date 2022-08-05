# ocp-preview

Script to build and deploy openshift docs to a file server.

To install: 

* Copy `ocp-preview` script to `/usr/local/bin`
* `chmod a+x /usr/local/bin/ocp-preview`
* Create a config file: `vi ~/.ocp-preview` and update with your config details, for example:

```
[user]
    name = aireilly
[server]
    name = file.emea.redhat.com
[repo]
    name = /home/aireilly/openshift-docs
```

Using the ocp-preview script:

```
Usage: ocp-preview [OPTION] [DISTRO]
Usage: [DISTRO] is optional, build default is openshift-enterprise. Specify 'all' to build all distros.
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
