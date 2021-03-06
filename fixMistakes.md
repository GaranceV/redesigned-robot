# Fixing mistakes
Sometimes I do dumb stuff, or _radically_ change my mind on the best way to solve a problem, and want to remove the previous version from history.  
This can only work if absolutely no one else is working on my branch.

## Undoing local stuff
Soft reset of the last commit:
```shell
git reset HEAD~
```
Soft because all the changes will still be in my repo, I can do whatever I want with them.  
To completely get rid of my local commits and changes, and get back to the remote branch HEAD, I can:
```shell
git reset --hard origin/<branch_name>
```
Reset always needs a commit to refer itself to.

## "Cancel" a renamed file
```shell
git mv <renamedName> <originalName>
```

## Undoing remote stuff
I have the bad habit of not seeing my biggest mistakes on the repo, _especially_ if I know how to fix them right after I made them!
(the real bad habit is to not think enough before pushing :grin: )
If I need to go back to a previous commit: 
This will put the branch back to the specified commit. 
I can then force push to erase everything that happened before. 
```shell
git reset <commit_hash>
```

## Get a group of files back to previous version
Quick how-to:  
* Find the guilty commit hash, with the beginning of downhill changes   
If we want to recover from file deletion, we can do a command directly:
```shell
git rev-list -n 1 HEAD -- <path>
```
With that hash, we can checkout the version of the project at the commit before that one:  
```shell
git checkout <hash>^ -- <path>
```
Then, we have the previous version of the files in our unstaged changes! :tada:

# More
* [Studying repo History](studyHistory.md)
* [Fixing conflicts](fixConflicts.md)
* [Stashing](stash.md)
* [My git config](myConfig.md)
* [Housekeeping the repo](housekeeping.md)
* [Meddling with commits](meddling.md)
* [Juggling with several git config](severalConfigurations.md)
* [Back to the Readme](README.md).