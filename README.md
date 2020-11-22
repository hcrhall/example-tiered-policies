# example-tiered-policies

This repo contains an example of how you to use different local source paths within a `sentinel.hcl` file to enforce different policies by environment

## Demonstration Steps

1. Run Policy evaluation in parent directory
```
$ sentinel apply -trace

No module changes to install

No policy changes to install

Execution trace. The information below will show the values of all
the rules evaluated and their intermediate boolean expressions. Note that
some boolean expressions may be missing if short-circuit logic was taken.

Pass - one.sentinel

Print messages:

This is policy 1


Pass - two.sentinel

Print messages:

This is policy 2


Pass - three.sentinel

Print messages:

This is policy 3
```

2. Run Policy evaluation in child directory
```
$ cd ./staging/baz
$ sentinel apply -trace

No module changes to install

Installing policies...
  - Policy one marked for installation
Policy installation complete

Execution trace. The information below will show the values of all
the rules evaluated and their intermediate boolean expressions. Note that
some boolean expressions may be missing if short-circuit logic was taken.

Pass - one.sentinel

Print messages:

This is policy 1
```
