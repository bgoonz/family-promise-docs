# Github Guide



1. Commit, Branch and Head\
   Git works mainly via Linked Lists. Here, Commit means to permanently store a changeset. A changeset indicates the changes in the files/source-codes etc. changesets include addition,modification and deletion of files. When you make a commit in Git, Git takes every file present in the changeset, makes a new node(in terms of linkedlists), creates a new copy of those files into the new node(other version control systems just copy the changes) and makes the new node point to the previous node. Git supports branches. The default branch is Master. The Head pointer represents the current snapshot(version) of your files. When you change the Head, the current snapshot is changed to the snapshot of the current Head. The other versions are hidden and you would only be able to view the current snapshots of the files

![](https://qph.fs.quoracdn.net/main-qimg-6b295aa3eb34dcc0a458202c589c7d31)

In the above diagram, you can see that A,B and C are commits and represent Linked List nodes. Here, we can see that there are two pointers, the branch pointer(master) and the Head pointer. The branch pointer is fixed and act as an identification and entry point to a branch. Head pointer indicates the current snapshot(node) of your work in git. Your changes gets added on top of the Node pointed to by the Head. Here, the commit A was made first followed by B and then C. Note, Head pointer can be moved to any node(commit) whereas the branch pointer remains fixed.

e.g. We can make another branch as follows.![](https://qph.fs.quoracdn.net/main-qimg-773d2befb8d016c81e7d3fe17011c80d)

In the above figure, we first move the Head to point to B. You can do that by checking out into a particular commit manually. The next thing is to make a new commit which points back to D and make it a new branch. Thus, Head is now on D and we also create a new branch pointer called Branch_Temp.

Index/Reset Head

Before you make a commit in git, there is something called the Index or the Staging Area. You need to add files into the staging area(new files/modified files) which can then go for commit. Think of Staging area as a stage. The performers need to be present in the stage and only then can begin to perform. Only files added in the staging area can be part of the new commit. Reset Head is used to remove the files from the staging area.

Merge

These are some of the advanced topics and makes Git extremely powerful. Think of a scenario when two different groups are working on two separate components of a program and once done they intend to merge their work into the master branch. For the sake of simplicity, lets assume there are no conflicts between the codes. We merge their work via Merge/Rebase.

![](https://qph.fs.quoracdn.net/main-qimg-cf01ec74f156b1eaa8b9a61a9f545232)

In the above figure, D is on Branch_Temp and C is on master. Now when you want to merge them (merge Branch_Temp on master) and use the “git merge” option a new Node E is created on top of master and contents on the HEAD of Branch_Temp is copied onto E(It occurs smoothly if there are no conflicts) and Head and master now point to E. Now, notice what happens when we delete Branch_Temp.

![](https://qph.fs.quoracdn.net/main-qimg-d494f002ad5f46961a8235d32b5d46ab)

The above figure indicates what happens when we delete the branch Branch_Temp.\
We can see that E still points back to both D and C. D now forms a part of the history of your current repository even after we delete the Branch.

Rebase

Rebase is another utility to merge two separate branches while keeping the history clean.

![](https://qph.fs.quoracdn.net/main-qimg-c00bf41d944c47665f09f9d84fbbb90a)

In the above figure, we wish to rebase Branch_Temp into master. Rebase first obtains the lowest common ancestor of both the branches and replays the commits from the Branch_Temp till the lowest Ancestor on top of Master. Here, D and E belong to Branch_Temp. When we rebase, git calculates B as the lowest common ancestor of Branch_Temp and master. Now git rewinds E and D on top of Master as it is. This results in a cleaner version of history when we delete Branch_Temp.
