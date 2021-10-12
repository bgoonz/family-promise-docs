# Git Prune:

## Git Prune

The `git prune` command is an internal housekeeping utility that cleans up unreachable or "orphaned" Git objects. Unreachable objects are those that are inaccessible by any refs. Any commit that cannot be accessed through a branch or tag is considered unreachable. `git prune` is generally not executed directly. Prune is considered a garbage collection command and is a child command of the [`git gc`](https://www.atlassian.com/git/tutorials/git-gc) command.

### Git Prune Overview <a href="installing-git-lfs" id="installing-git-lfs"></a>

In order to understand the effects of `git prune` we need to simulate a scenario where a commit becomes unreachable. The following is a sequence of command line executions that will simulate this experience.

```
~ $ cd git-prune-demo/
~/git-prune-demo $ git init .
Initialized empty Git repository in /Users/kev/Dropbox/git-prune-demo/.git/
~/git-prune-demo $ echo "hello git prune" > hello.txt
~/git-prune-demo $ git add hello.txt
~/git-prune-demo $ git commit -am "added hello.txt"
```

The preceding sequence of commands will create a new repository in a directory named `git-prune-demo`. One commit consisting of a new file `hello.text` is added to the repo with the basic content of "hello git prune". Next, we will create modify `hello.txt` and create a new commit from those modifications.

```
~/git-prune-demo $ echo "this is second line txt" >> hello.txt
~/git-prune-demo $ cat hello.txt
hello git prune
this is second line txt
~/git-prune-demo $ git commit -am "added another line to hello.txt"
[main 5178bec] added another line to hello.txt
1 file changed, 1 insertion(+)
```

We now have a 2 commit history in this demo repo. We can verify by using `git log`:

```
~/git-prune-demo $ git log
commit 5178becc2ca965e1728554ce1cb8de2f2c2370b1
Author: kevzettler <kevzettler@gmail.com>
Date:   Sun Sep 30 14:49:59 2018 -0700

        added another line to hello.txt

commit 994b122045cf4bf0b97139231b4dd52ea2643c7e
Author: kevzettler <kevzettler@gmail.com>
Date:   Sun Sep 30 09:43:41 2018 -0700

        added hello.txt
```

The [`git log`](https://www.atlassian.com/git/tutorials/git-log) output displays the 2 commits and corresponding commit messages about the edits made to `hello.txt`. The next step is for us to make one of the commits unreachable. We will do this by utilizing the [`git reset`](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset) command. We reset the state of the repo to the first commit. the "added hello.txt" commit.

```
~/git-prune-demo $ git reset --hard 994b122045cf4bf0b97139231b4dd52ea2643c7e
HEAD is now at 994b122 added hello.txt
```

If we now use `git log` to examine the state of the repository we can see that we only have one commit

```
~/git-prune-demo $ git log
commit 994b122045cf4bf0b97139231b4dd52ea2643c7e
Author: kevzettler <kevzettler@gmail.com>
Date:   Sun Sep 30 09:43:41 2018 -0700

        added hello.txt
```

The demo repository is now in a state that contains a detached commit. The second commit we made with the message "added another line to hello.txt" is no longer displayed in the `git log` output and is now detached. It may appear as though we have lost or deleted the commit, but Git is very strict about not deleting history. We can confirm it is still available, but detached, by using [`git checkout`](https://www.atlassian.com/git/tutorials/using-branches/git-checkout) to visit it directly:

```
~/git-prune-demo $ git checkout 5178becc2ca965e1728554ce1cb8de2f2c2370b1
Note: checking out '5178becc2ca965e1728554ce1cb8de2f2c2370b1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

      git checkout -b <new-branch-name>

HEAD is now at 5178bec... added another line to hello.txt
~/git-prune-demo $ git log
commit 5178becc2ca965e1728554ce1cb8de2f2c2370b1
Author: kevzettler <kevzettler@gmail.com>
Date:   Sun Sep 30 14:49:59 2018 -0700

      added another line to hello.txt

commit 994b122045cf4bf0b97139231b4dd52ea2643c7e
Author: kevzettler <kevzettler@gmail.com>
Date:   Sun Sep 30 09:43:41 2018 -0700

      added hello.txt
```

When we check out the detached commit, Git is thoughtful enough to give us a detailed message explaining that we are in a detached state. If we examine the log here we can see that the "added another line to hello.txt" commit is now back in the log output! Now that we know the repository is in a good simulation state with a detached commit we can practice using `git prune`. First though, let us return to the `main` branch using `git checkout`

```
~/git-prune-demo $ git checkout main
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

      5178bec added another line to hello.txt

If you want to keep it by creating a new branch, this may be a good time
to do so with:

     git branch <new-branch-name> 5178bec

Switched to branch 'main'
```

When returning to main via `git checkout`, Git is again thoughtful enough to let us know that we are leaving a detached commit behind. It's now time to prune the detached commit! Next, we will execute `git prune` but we must be sure to pass some options to it. `--dry-run` and `--verbose` will display output indicating what is set to be pruned but not actually prune it.

```
~/git-prune-demo $ git prune --dry-run --verbose
```

This command will most likely return empty output. Empty output implies that the prune will not actually delete anything. Why would this happen? Well, the commit is most likely not fully detached. Somewhere Git is still maintaining a reference to it. This is a prime example of why `git prune` is not to be used stand-alone outside of `git gc`. This is also a good example of how it is hard to fully lose data with Git.

Most likely Git is storing a reference to our detached commit in the reflog. We can investigate by running [`git reflog`](https://www.atlassian.com/git/tutorials/rewriting-history/git-reflog). You should see some output describing the sequence of actions we took to get here. For more info on `git reflog` visit the [`git reflog`](https://www.atlassian.com/git/tutorials/rewriting-history/git-reflog) page. In addition to preserving history in the reflog, Git has internal expiration dates on when it will prune detached commits. Again, these are all implementation details that `git gc` handles and `git prune` should not be used standalone.

To conclude our `git prune` simulation demo we must clear the reflog

```
~/git-prune-demo $ git reflog expire --expire=now --expire-unreachable=now --all
```

The above command will force expire all entries to the reflog that are older than now. This is a brutal and dangerous command that you should never have to use as casual Git user. We are executing this command to demonstrate a successful `git prune`. With the reflog totally wiped we can now execute `git prune`.

```
~/git-prune-demo $ git prune --dry-run --verbose --expire=now
1782293bdfac16b5408420c5cb0c9a22ddbdd985 blob
5178becc2ca965e1728554ce1cb8de2f2c2370b1 commit
a1b3b83440d2aa956ad6482535cbd121510a3280 commit
f91c3433eae245767b9cd5bdb46cd127ed38df26 tree
```

This command should output a list of Git SHA object references that looks like the above.

### Usage <a href="speeding-up-pulls" id="speeding-up-pulls"></a>

`git prune` has a short list of options that we covered in the overview section.

```
-n --dry-run
```

Don't execute the prune. Just show an output of what it will do

```
-v --verbose
```

Display output of all objects and actions taken by the prune

```
--progress
```

Displays output that indicates the progress of the prune

```
--expire <time>
```

Force expiration of objects that are past 

```
<head>…
```

Specifying a  will preserve any options from that head ref

### Discussion

#### What’s the Difference Between Git Prune, Git Fetch --prune, and Git Remote Prune?

`git remote prune` and `git fetch --prune` do the same thing: delete the refs to branches that don't exist on the remote. This is highly desirable when working in a team workflow in which remote branches are deleted after merge to `main`. The second command, `git fetch --prune` will connect to the remote and fetch the latest remote state before pruning. It is essentially a combination of commands:

```
git fetch --all && git remote prune
```

The generic `git prune` command is entirely different. As discussed in the overview section, git prune will delete locally detached commits.

#### How Do I Clean Outdated Branches?

`git fetch --prune` is the best utility for cleaning outdated branches. It will connect to a shared remote repository remote and fetch all remote branch refs. It will then delete remote refs that are no longer in use on the remote repository.

#### Does Git Remote Prune Origin Delete the Local Branch?

No `git remote prune origin` will only delete the refs to remote branches that no longer exist. Git stores both local and remote refs. A repository will have `local/origin` and `remote/origin` ref collections. `git remote prune origin` will only prune the refs in `remote/origin`. This safely leaves local work in `local/origin`.

### Git Prune Summary

The `git prune` command is intended to be invoked as a child command to `git gc`. It is highly unlikely you will ever need to invoke `git prune` in a day to day software engineering capacity. Other commands are needed to understand the effects of `git prune`. Some commands used in this article were `git log`, `git reflog`, and `git checkout`.

Ready to learn Git?

Try this interactive tutorial.[Get started now](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)\
