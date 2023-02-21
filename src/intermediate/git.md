# Git

git is a version control system which enables tracking
changes in code over time and enables multiple developers
to collaborate on the same project.

Although the tool is extremely complex, knowing a few
basic commands is enough to go unlock much of the potential.

[The full reference is here.](https://git-scm.com/docs)

There are many great introductory guides on git but the basic
terminology includes:
- `repository` or `repo` the history associated with some source code
- `commits` a checkpoint in a repository that can be restored
at any point in the future
- `branch` a divergence in the code that allows different changes
to exist side by side
- `merge` integrating some changes into the main code
- `conflicts` when multiple changes exist on the same lines of the source

## [A helpful git cheat-sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)


## Basic workflow steps

To copy a repository we use 
```bash
git clone <repo>
```

You could clone the source code for this guide with
```bash
git clone https://github.com/aujxn/rtg_hpc_cookbook
```

Github is a website owned by Mircosoft where git repos are
hosted.

If you wanted to make some changes you could create a new branch with
```bash
git branch <branch_name>
```
and then load the new branch with
```bash
git checkout <branch_name>
```
If you made changes to the source you
could check the status of the repo with
`git status`, `git diff`, or `git log`.

To commit the changes you must add the changed files to the repo with
`git add <files>` or `git add --all` and then commit the changes
```bash
git commit -m "very helpful commit message here"
```

To merge the branch back into `master` first check it out with
```bash
git checkout master
```
and then merge with 
```bash
git merge <branch_name>
```

You can push your changes to the remote repository with
```bash
git push origin master
```
but doing this with this book will give
you a permissions error since you are not an owner of the remote repo.

If you forked the repo on github and repeated the steps, it would
push the changes to your fork on your github account. Then you
could submit a pull request to merge your changes to my repo.
If I approve, the changes will merge into my repository.

This workflow is all you need to know for basic git usage.
You can even skip the branching steps in basic cases.
Once you get this workflow down you can maintain a complete
history of all the changes you make in your code.
