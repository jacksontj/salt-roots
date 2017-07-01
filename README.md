# Basic Salt Root Repo
A simple repo for cloining to start your salt installation.
This repo (with the below config) encapsulates the various roots required to
have a functioning salt infrastructure all backed by git.


# Master config
The below configuration will configure the master to pull both the file_roots and
pillar_roots from this git repo.

```
fileserver_backend:
  - git
gitfs_remotes:
  - https://github.com/jacksontj/salt-roots.git
gitfs_root: file_roots
ext_pillar:
  - git:
    - __env__ https://github.com/jacksontj/salt-roots.git:
      - root: pillar_roots
      - env: base
```
