Let's take a closer look at this important Git command:
```
$ git pull origin master
```
The `pull` command directs the download process to occur. The `origin` and `master` designate the source of the download or `pull`. The `origin` describes the remote in other words, the GitHub repo, and `master` designates the branch or version in the remote repo we would like to `pull` from or download. Please note if the `<branch-name>` does not exist on the remote repo, the `pull` process will error and not complete.
> **Pause**: Wait, but how does the `pull` command know where the download will to go to?
any thoughts? guesses?<br />
> **Answer**: `git pull` will download to the current active branch or whatever branch you are currently checked-out on. That's why it's always a good idea to use a `git branch` to verify the active branch before doing a `git pull`.

> **Video -** Animation: Showing Data Flow [Git Pull & Git Push-Jira FSFO-108](https://trilogyed.atlassian.net/jira/software/projects/FSFO/boards/197/backlog?selectedIssue=FSFO-108)<br>
![Git Pull](assets/lesson-1/250-pull-git.png)<!-- Illustration lacks direction-->
<br /> 
As can be seen in this illustration, the remote repo has converged with the local repo in the "H" merge commit. Now our two repos are synced up and have duplicate code.

### Git Fetch
Let's dive deeper on the `pull` process. The `pull` command is actually a combination of two different operations, `git fetch` and `git merge`.
The git command `git fetch` updates the local repo with any new changes in the remote repo since the last `fetch` command. A use case for `git fetch` would be to look at a team member's feature branch for a review process or to help in finding a bug. This branch is downloaded through the Git command:
```
git fetch <remote branch name>
``` 
Next step is for the following Git command:
```
git checkout <remote branch name>
```
With these operations, the remote branch whether it be the remote `master` or any other branch currently occupied on the remote repo, a separate isolated version was created locally so no updates or merges occurred.
This code can be rendered in the browser, tested, code reviewed, or changed as needed separate from any other local branch. These changes can then be staged, committed, and pushed back to the remote repo.
### Git Merge
The `git merge` operation, on the other hand, will merge the target branch into the active branch. This will update the active branch with code differences in the target branch.
```
git merge <target branch>
```
In this operation Git will determine any differences in the code between the active branch and the target branch, and update the active branch with those changes whether they be added files or changes in the code. Conversely the target branch will remain the same and **not** undergo any changes.

![Git Pull](assets/lesson-1/260-git-fetch-merge-pull.png)<br>
After the merge, the active branch, in our case the `develop` branch, will not only receive the new file updates from the remote `master` branch, but also all the commit histories associated with that branch. 
For more details about different options and other useful commands, let's look at the official [Git docs](https://git-scm.com/docs/git-pull) (a great site to bookmark).