Nice gist: https://gist.github.com/robmiller/6018582

Cherry pick your commits in FIFO order.
Ex.: For 2 commits do
git cherry-pick topic-branch~1
git cherry-pick topic-branch

Use git pickaxe to find first occurrence of text:
`git log -S SEARCHED_PATTERN --patch --reverse`

Trace git history of a file:
`git log --follow ./path/to/file`
