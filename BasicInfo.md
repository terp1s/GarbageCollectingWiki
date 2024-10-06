# Garbage
# What is computer garbage?


## What is Garbage in Git? ##

In Git, garbage refers to Git objects (like commits, blobs, or trees) that are no longer referenced by any branches, tags, or reflogs (references logs). These objects are still stored in the Git repository, but they are effectively unused or unreachable and could be safely removed.

Examples of Garbage in Git:

1.    Dangling Commits: Suppose you create a branch, make a few commits, and then delete the branch. The commits that were only part of that branch now become dangling because they are no longer reachable from any other branch or tag. These dangling commits still exist in the repository as garbage.

2.    Orphaned Blobs: If you modify a file and then commit the changes, the old version of the file is stored as a blob in Git. If there are no branches or tags pointing to the commit that contains the old version of the file, that blob becomes unreachable and is considered garbage.

3. Expired Reflog Entries: Git's reflog allows you to recover changes that might not be referenced by any branch, but after some time, the reflog entries can expire. The objects that were only referenced by these expired reflogs can become garbage.
