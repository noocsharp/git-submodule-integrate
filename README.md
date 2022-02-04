# git-submodule-integrate

This script automates the process of copying a git repository into a
subdirectory of another git repository, and preserving its history. Since git
submodules are just git repositories, the script can be used to incorporate a
submodule and its history into a parent repository.

## Usage

The script acts on two repositories: the parent repo and the child repo. Once
the script has been run, the parent repo will contain the child repo in a
subdirectory.

To start, clone the parent repository somewhere. We will assume that `$PARENT`
is the path of the parent repository. Next, either clone the child repository
locally, or find a clone URL for the child. We will assume that `$CHILD`
is this path or url.

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

Depending on the size of your repo and commits, it may take a while.
