# Standard-Workflow
An introduction to simple three stage development
## Concept
The idea of this workflow is to introduce a three step development process defined by a dedicated branch. 
Master: 
This branch contains all production files and should only be updated through merge with the underlying develop branch.
Develop: 
This branch contains all deveopment files and should only be updated through merge with the underlying topic branches.
Topic:
This is where the actual work is done. When a topic has to be resolved, a topic branch is created from develop. 
It is good practice to give it a name related to the topic. In this example the are three topic branches. IMPORTANT this workflow only allows for sequential 
work on the individual branches NOT simultaneous work!
### Create master branch
```
Go to the local repository.
Create a master repository.
Create a remote repository on GitHub and Push the local repository to the remote repository. 
Create the readmefile on GitHub and pull it to the local repository. 
```
### Create develop branch
```
Git Command:
$ git branch develop
$ git checkout develop
$ git add -A
$ Commit "First commit of the develop-branch"
$ git push origin develop
This will create a new branch under the master-branch called: develop, add all changes, commit all changes, create a remote branch on GittHub under the master-branch called: Develop
```
### Work on topicA
```
Git Command:
$ git branch topicA
This will create a new branch called: topicA
```
Change to the new branch.
```
Git Command:
$ git checkout topicA
This will change to the branch called: topicA
```
You can now update the textfile on your computer. You can push and pull files from the 
topic branch to and from GitHub as you like.
```
Push to GitHub:
Git Command:
$ git add -A
$ Commit -m "Comment"
$ git push origin topicA
This will commit all changes and push the topicA branch to GitHub
```
```
Pull from GitHub:
Git Command:
$ git pull origin topicA
This will pull all changes on topicA form GitHUb
```
When work on topicA is done it is time to merge it with develop
### Merge the topic branch in to develop
```
Git Command:
$ git checkout develop
$ git merge topicA
$ git add -A
$ Commit "First merge of topicA"
$ git push origin develop
This will merge the topicA branch with the develop branch and push develop to GitHub. 
```
When development of topicA is complete you ready to merge from development in to master
### Merge to the master branch
```
Git Command:
$ git checkout master
$ git merge develop
$ git add -A
$ commit -m "comment"
$ git push origin master
```
The master branch now contains the all the work done in topicA
### Work on topicB
To start work on topic you create it an merge the content from development. IMPORTANT this contains all the work done on topicA!
```
Git Command:
$ git checkout development
$ git pull origin development
$ git branch topicB
$ git checkout topicB
$ git merge development
This will pull the development branch from GitHub, create the topicB branch and merge the topicB branch with develop.
```
You can now update the textfile on your computer. You can push and pull files from the 
topic branch to and from GitHub as you like in same was as with topicB

