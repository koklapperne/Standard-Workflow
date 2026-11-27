# Standard-Workflow
```
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

```
## Clone from the remote repository to the local repository
Do this first time or if somthing has gone wrong in the local local repository
```
Example:
$ cd "/C/Users/mnis0035/Desktop/Udvikling/GitTutorial/Standard-Workflow"
At home:
$ cd "/C/Users/mnis0035/Desktop/Udvikling/GitTutorial"
$ git clone https://github.com/koklapperne/Standard-Workflow.git
```
## Pull from the remote repository to the local repository
Do this before work begins in the local repository
```
Example:
$ cd "/C/Users/mnis0035/Desktop/Udvikling/GitTutorial/Standard-Workflow"
$ git pull
```
## Create repository from scratch if needed
```
Do this first time only to create a new repository from scratch. 
Create a local repository.
Create a remote repository on GitHub and Push the local repository to the remote repository. 
Create the readmefile on GitHub and pull it to the local repository. 
```
## Create develop branch if needed
```
Git Command:
$ git branch develop
$ git checkout develop
$ git add -A
$ Commit "First commit of the develop-branch"
$ git push origin develop
This will create a new branch under the master-branch called: develop, add all changes, commit all changes, create a remote branch on GittHub under the master-branch called: Develop
```
## Work on topicA
```
Git Command:
$ git branch topicA
This will create a new branch called: topicA
```
Change to the new branch topicA
```
Git Command:
$ git checkout topicA
This will change to the branch called: topicA
```
## You can push and pull files from the topic branch
```
Push to GitHub:
Git Command:
$ git add -A
$ Commit -m "Comment"
$ git push origin topicA
This will commit all changes and push the topicA branch to GitHub
Pull from GitHub:
Git Command:
$ git pull origin topicA
This will pull all changes on topicA form GitHUb
```
## Merge the topic branch in to develop
```
Git Command:
$ git checkout develop
$ git merge topicA
$ git add -A
$ Commit "Merge of topicA"
$ git push origin develop
This will merge the topicA branch with the develop branch and push develop to GitHub. 
```
## Merge deveop to the master branch
```
When development of topicA is complete you ready to merge from development in to master
Git Command:
$ git checkout master
$ git merge develop
$ git add -A
$ commit -m "comment"
$ git push origin master
The master branch now contains the all the work done in topicA
```
## Work on topicB
```
To start work on topicB you create it an merge the content from development. IMPORTANT this contains all the work done on topicA!
Git Command:
$ git checkout development
$ git pull origin development
$ git branch topicB
$ git checkout topicB
$ git merge development
This will pull the development branch from GitHub, create the topicB branch and merge the develop branch with topicB.
```
Merge to develop and master branch
```
Complete the same steps as for topicA 
