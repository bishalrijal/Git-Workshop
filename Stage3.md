## Log of commits
#### View log of git
`git log` Shows the commit logs.
```bash
git log
```
#### View last 2 commits
```bash
git log -2
```  

## Discard uncommitted changes to a file
Situation:  you've changed a file, but not yet committed the changes  
 
```bash
git checkout README.md
```
### amend commit
when you commit too early and possibly forget to add some files, or you mess up your commit message. 
If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the
```--amend``` option:
#### let's try
open your test.txt file and write something and commit it
```
level: Bachelor
```
```bash
git commit -m "Age is added"
```
Ohh!! we did commit wrong  
don't worry we can change the commitmessage
``` 
git commit --amend -m "Level is Added"
```

## Git Reset
The git reset command is a complex and versatile tool for undoing changes
#### ```git reset --hard```
open your test.txt and make some changes and commit it
after commiting check your log 

check your commit log
```bash
git log
ommit d1f59c4bd2a52e6860d11f2eeb1df159feb6186a (HEAD -> master)
Author: Bishal Rijal <bishalrijal110@gmail.com>
Date:   Fri May 3 09:19:29 2019 +0545

    Age added

commit be77bd6df12248c3026119df81bee367bbaf1ef9
Author: Bishal Rijal <bishalrijal110@gmail.com>
Date:   Fri May 3 08:08:16 2019 +0545

     level added


     test
```
copy your second hash
```bash
git reset --hard be77bd6df12248c3026119df81bee367bbaf1ef9
```
check our status 
``` 
git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
#### ```git reset --soft```
again open your test.txt and make some changes and commit it
after commiting check your log 

check your commit log
```bash
git log
commit 3bea9066ee58c211f26387ebf1b6b9e5d470a731 (HEAD -> master)
Author: Bishal Rijal <bishalrijal110@gmail.com>
Date:   Fri May 3 09:23:51 2019 +0545

    Age added

commit be77bd6df12248c3026119df81bee367bbaf1ef9
Author: Bishal Rijal <bishalrijal110@gmail.com>
Date:   Fri May 3 08:08:16 2019 +0545

     level added
```
copy your second hash
```bash
git reset --soft be77bd6df12248c3026119df81bee367bbaf1ef9
```

check your status 
```bash 
git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   test1.txt
```

