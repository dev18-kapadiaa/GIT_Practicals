# GIT_Practicals
GIT and GITHUB Command demonstration.

# Practical :1 >>
# Difference between Merge and Pull and merge request.

Pull requests are a GitHub and Bitbucket-specific feature that offers an easy, web-based way to submit your work. The name “pull request” comes from the idea that you’re requesting the project to “pull” changes from your fork. 

- A merge request is simply a request from a user to merge their code from one branch to another, typically to the master branch. Like the Git pull request, the Git merge request allows the team members to discuss the suggested changes and merges, offering feedback and possibly adding new commits to make the process smoother
 
<b>Task :</b> Created .gitignore file and master branch on the tip of the master branch git_practicals branch created, and from git_practicals branch practical branch created.practical1.txt file created and commited and from practical-1 branch to_be_merged branch created.In which <b>merging_file.txt</b> was added and commited. <br>
                        <p> After checked out to practical_1 branch git merge will merge to_be_merged with the practical_1 branch, and will reflected to the practical_1 branch.  </p>

```python
git init 

touch .ignore 

git add . 

git commit -m "Master Branch Created and .gitignore file commited."

git branch git_practicals 

git checkout git_practicals 

git branch practical_1 

git checkout practical_1 

touch practical1.txt 

git add . 

git commit -m "Practical-1 text file commited on main branch."

git remote add origin https://github.com/dev18-kapadiaa/GIT_Practicals.git

git remote -v 

git push origin master 

git push origin git_practicals 

git push origin practical_1 

git branch to_be_merged 

git checkout to_be_merged 

touch merging_file.txt 

git add . 

git commit -m "This is creation of merging file and commitment on to_be_merged Branch."

git checkout practical_1 

git merge to_be_merged 

git push origin practical_1 

git push origin to_be_merged 

```
            
# Practical :2 >>
# Rebasing :

```python
git checkout git_practicals 

git branch practical_2 

git checkout practical_2 

touch rebase.txt 

git add . 

git commit -m "rebase text file created and commited on the practical-2 branch."

git push origin practical_2 

git branch to_be_rebase 

git checkout to_be_rebase 

touch rebase2.txt 

touch rebase3.txt 

git add . 

git commit -m "Both rebasing files are commited on the to_be_rebased branch."

git push origin practical_2 

git push origin to_be_rebase 

git checkout practical_2 

git rebase to_be_rebase 

git push origin practical_2 –f 

```
Here after checking out to the <i>git_practicals</i> branch once again, new branch of practical_2 is created.in which rebase.txt file was created and commited under practical_2 branch.from practical_2 branch another sub-branch of to_be-rebase created and in which commitment of rebase2.txt and rebase3.txt carried out.So we have 2 separate branches like to_be_rebased and practical_2. 
<p>using <b>git rebase to_be_rebase</b> we can merge/rebase practical_2 branch over to_be_rebase branch and now both branches have same log history and creates linear structure this technique is fast-forwarding because there is direct path from to_be-rebase branch to the practical_2 branch.</p>

# Practical : 3 >>

# Change Commit Message
```python

git checkout git_practicals 

git branch practical_3 

git checkout practical_3  

touch commitmodify.txt 

git add . 

git commit -m "Initial Commit is Unchanged under practical-3 branch."

git push origin practical_3 

git commit --amend -m "Changes commited message this will be updated one."

git push origin practical_3 –f 

```
Again checkout to git_practicals branch.From git_practicals create new branch practical_3 in which commitment of commitmodify file takes placeusing initial commit. for change commit message <b><i>--amend</i></b> command is used. So commit message will change from <br> 
        <i> "Initial Commit is Unchanged under practical-3 branch."    --->     "Changes commited message this will be updated one." </i>
      
  
# Practical : 4 >>
# Cherry Picking :

```python
git checkout git_practicals 

git branch practical_4 

git checkout practical_4 

touch cherry_pick_file.txt 

git add . 

git commit -m "This is cherry pick base file and branch commitment."

git branch target_cherry_pick 

git checkout target_cherry_pick 

touch target_cherry.txt 

git add . 

git commit -m "Target Cherry pick branch Commitment with target cherry file."

git push origin practical_4 

git push origin target_cherry_pick

git log --oneline 

git checkout practical_4 

git cherry-pick 9e88267 (SHA value of --oneline for the latest commit meassage.) 

git push origin practical_4 
```
After checkout to the git_practicals branch we created another branch of practical-4. In which cherry_pick_file was created and commited under practical-4 branch. From this target_cherry_pick branch was created.In which target_cherry file was created and commited under target_cherry_pick branch. <br> 
<p> Now we need to cherry pick commit with commit message "Target Cherry pick branch Commitment with target cherry file." So using git log --oneline we can get SHA Hashing value of corresponding commit. We will put this commit or cherry pick this commmit over practical_4 branch. </p>
<p> Hence, now we have cherry-picked commit hased 9e88267 to the practical_4 branch. </p>

# Practical - 5
# Drop Commit :

```python
git checkout git_practicals 

git branch practical_5 

git checkout practical_5 

touch commit_deletion.txt 

git add . 

git commit -m "Initial commit in practical-5 branch."

git push origin practical_5 

git add . 

git commit -m "Updated commit_deletion file and updated line will be removed." 

git log --oneline 

git revert fbcf4a8 

git push origin practical_5

```
Here from git_practicals branch we created practical_5 branch. In which commit_deletion.txt file created and commited with initial commit message.Now we modified commit_deletion.txt file and added to the staging area and commited with another commit message and updated one.git log --oneline will show log history of this branch along with their SHA Hash values.
<p>Now using revert command it will do undo operation and do undoing changes to the repository's commit history till the SHA value specified.
Here fbcf4a8 is the SHA value associated with the commit message "Updated commit_deletion file and updated line will be removed".Hence this commit effect will be undone by revert command.</p>

