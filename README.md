# git-submodule-integrate

This script automates the process of copying a git repository into a
subdirectory of another git repository, and preserving its history. Since git
submodules are just git repositories, the script can be used to incorporate a
submodule and its history into a parent repository.

## Usage

The script acts on two repositories: the parent repo and the child repo. Once
the script has been run, the parent repo will contain the child repo in a
subdirectory.

First, you'll need copies of the parent and child repositories in separate
directories. So if the child repository is a submodule, you'll need to clone it
into its own repo, outside of the parent. We will assume that `$PARENT` is the
path to the parent repository and `$CHILD` is the path to the child repository.

Next, download the script somewhere. We will assume the path of the script is
`$GSI`.

Now set your working directory to the parent repository

```
$ cd $PARENT
```

If you're trying to integrate a submodule, you need to remove the submodule from
the parent repository. This can be accomplished with

```
$ git rm path/to/submodule && git commit
```

Now pick a name for the subdirectory `$DEST` where you want the child repository
to be placed and run

```
$ $GSI $CHILD $DEST
```

Of course
Depending on the size of your repo and commits, it may take a while.
