# What is Garbage in Git? 

In Git, garbage refers to Git objects (like commits, blobs, or trees) that are no longer referenced by any branches, tags, or reflogs (references logs). These objects are still stored in the Git repository, but they are effectively unused or unreachable and could be safely removed.

Examples of Garbage in Git:

1.    Dangling Commits: Suppose you create a branch, make a few commits, and then delete the branch. The commits that were only part of that branch now become dangling because they are no longer reachable from any other branch or tag. These dangling commits still exist in the repository as garbage.

2.    Orphaned Blobs: If you modify a file and then commit the changes, the old version of the file is stored as a blob in Git. If there are no branches or tags pointing to the commit that contains the old version of the file, that blob becomes unreachable and is considered garbage.

3. Expired Reflog Entries: Git's reflog allows you to recover changes that might not be referenced by any branch, but after some time, the reflog entries can expire. The objects that were only referenced by these expired reflogs can become garbage.

How Does Git Handle Garbage?

Git has a built-in process to deal with garbage, called garbage collection (GC). Git doesn’t delete garbage immediately. Instead, it waits for a while, usually 30 days, to make sure you really don’t need those objects anymore. After this time, Git will remove the unreachable objects from your repository when it runs garbage collection.

Git runs garbage collection automatically from time to time, but you can also run it manually if you want to clean up your repository right away.
Commands to Manage Garbage

1.  `git gc`
    The command git gc triggers Git's garbage collection process, which cleans up unreachable objects and optimizes your repository.

2.  `git fsck --unreachable`
    This command checks your repository for unreachable objects and shows you what might be considered garbage. It's a way to see what Git would clean up during garbage collection.

3.  `git prune`
    The git prune command removes objects that are no longer reachable from any branch, tag, or reflog. This is like a manual cleanup, but Git does this automatically when you run git gc.

## Why is Garbage Collection Important?

Garbage collection helps keep your Git repository clean and efficient. Over time, as you make many changes to your project, your repository can accumulate a lot of unreachable objects that waste space. By regularly cleaning up garbage, Git ensures your repository stays small and fast to use.
