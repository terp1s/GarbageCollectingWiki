`git prune` deletes unnecessary objects. These are objects only accessible via unreachable commits. `prune` calls `git fsck --unreachable`, which lists such objects, and then `prune` prunes (deletes) them.
Options:
`-n`
`--dry- run`
only show what would be removed without actually removing it
`-v`
`--verbose`
print a list of all the removed objects
`--progress`
show progress
`--expire <time>`
only delete objects older than `<time>`

Additionaly, multiple commits can be passed as an argument, in which case reachability will be checked as if there were pointers to those commits. This means these commits will be "spared" as well as anything reachable from them. Example: Consider commits A, B, and C, all of which are unreachable from all our refs, but B is reachable from A. Then while normal `git prune` would remove all of them, but if add the commit A as an argument, A won't be deleted, and neither will B, because it suddenly became reachable via A, but C will still get removed.

Users rarely need to run `git prune` manually as it gets called automatically when running [`git gc`](gc.md).
