Podman on Fedora WSL
====================


On a base install of Fedora on WSL, running `podman` fails with:

```
Error: cannot setup namespace using newuidmap: exit status 1
```

To fix this, run:

```
$ sudo dnf reinstall -y shadow-utils
```

After this you can do:
```
$ podman pull fedora:latest                                                                                                                                                        master 
Resolved short name "fedora" to a recorded short-name alias (origin: /etc/containers/registries.conf.d/shortnames.conf)
Trying to pull registry.fedoraproject.org/fedora:latest...
Getting image source signatures
Copying blob 157ab8011454 done
Copying config 9f2a560376 done
Writing manifest to image destination
Storing signatures
9f2a56037643a68ea81711a8eeb4501428eefd40b000c866ad9745a581c0464d
$ podman run -it --rm fedora:latest bash                                                                                                                                           master 
[root@b66b09abd8b7 /]#
```

to verify Podman can run
