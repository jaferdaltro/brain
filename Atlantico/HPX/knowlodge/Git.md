
```
git config --list
```

![[comandos git.png]]


The original error was caused by a conflicting Git reference where refs/remotes/origin/testBranch/PenFeatureFlag existed, preventing the creation of refs/remotes/origin/testBranch
The git remote prune origin command cleaned up many stale references but didn't resolve this specific conflict
Manually removing the conflicting reference directory with rm -rf .git/refs/remotes/origin/testBranch resolved the issue
The git pull origin main then worked successfully, fast-forwarding your main branch by 9 commits