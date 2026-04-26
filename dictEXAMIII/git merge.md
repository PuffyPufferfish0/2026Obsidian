Branching in Git allows you to diverge from the main line of development (`main` or `master`) and continue to do work without messing up that main line. This is essential for issue tracking, testing new features, and collaboration.

### Key Commands

- **Create a branch**: `git branch [branch-name]`
    
- **Switch to a branch**: `git checkout [branch-name]` or `git switch [branch-name]`
    
- **Create AND switch to a branch**: `git checkout -b [branch-name]`
    
- **Push a new local branch to GitHub**: `git push -u origin [branch-name]` (The `-u` configures the local branch to track the remote branch).
    

### Merging Branches

When work on a branch is complete, you bring those changes back into the main line via a merge.

1. Switch to the target branch: `git checkout main`
    
2. Merge the feature branch: `git merge [branch-name]`
    

### Resolving Merge Conflicts

Conflicts occur when the same part of a file has been edited in both branches differently.

1. Git will pause the merge and highlight the conflicts in the affected files using markers (`<<<<<<<`, `=======`, `>>>>>>>`).
    
2. Open the file, manually choose which code to keep, and delete the Git markers.
    
3. Run `git add [file]` and `git commit` to finalize the merge.