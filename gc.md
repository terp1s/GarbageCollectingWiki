`git gc` calls [`git prune`](prune.md) and performs various tasks to save space.

#### Options:  
- `--aggressive`
  - try to save space more aggressively, causing the command to run longer than usual
- `--no-prune`
  - don't invoke [`git prune`](prune.md)


`git gc` is run automatically from time to time, unless disabled in configuration by setting `gc.auto` to `0`.
