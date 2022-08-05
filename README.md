# ocp-preview

Script to build and deploy openshift docs to a file server.

To install: 

* Copy `ocp-preview` script to `/usr/local/bin`
* `chmod a+x /usr/local/bin/ocp-preview`
* `touch ~/.ocp-preview`
* `vi ~/.ocp-preview` and add the following:

```
[user]
    name = <REPLACE_WITH_USERNAME>
[server]
    name = <REPLACE_WITH_FILESERVER>
```


Using the ocp-preview script:

```
Usage: ocp-preview [OPTION] [DISTRO]
Usage: [DISTRO] is optional, build default is openshift-enterprise. Specify 'all' to build all distros.
-b, --build
               does a full clean build and rsync. Use this option if your PR does not update an assembly.
-r, --refresh
               builds and rsyncs updated assemblies only. Uses default distro.
-s, --silent-refresh
               builds and rsyncs updated assemblies, no preview pop up. Uses default distro.
-l, --local-build
               does a full clean build locally, does not rsync. Use this option if your PR does not update an assembly.
-f, --local-refresh
               builds and updated assemblies locally, does not rsync. Uses default distro.
-c, --local-refresh-silent
               builds and updated assemblies locally, does not rsync, no preview pop up. Uses default distro.
-d, --delete
               deletes the current pull request build from the file server.
```
