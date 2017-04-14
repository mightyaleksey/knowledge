Git
===

A set of usefull commands and aliases.


## CI helpers

#### `git diff --cached --diff-filter=ACMX --name-only -- '*.js'`

Lists all staging files that were added, copied or modified (skips deleted) and outputs only those which have `*.js` extensino.

#### `git rev-parse --abbrev-ref HEAD`

Lists the current branch name.
