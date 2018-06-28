

# What is Git?

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.



### What is version control?

Git is, first and foremost, a version control system (VCS). There are many version control systems out there: CVS, SVN, Mercurial, Fossil, and, of course, Git.

Git serves as the foundation for many services, like GitHub and GitLab, but you can use Git without using any other service. This means that you can use Git privately or publicly.

If you have ever collaborated on anything digital with anyone, then you know how it goes. It starts out simple: you have your version, and you send it to your partner. They make some changes, so now there are two versions, and send the suggestions back to you. You integrate their changes into your version, and now there is one version again.

#### Git snapshots
Git takes snapshots of a project, and stores those snapshots as unique versions.

If you go off in a direction with your project that you decide was the wrong direction, you can just roll back to the last good version and continue along an alternate path.

If you're collaborating, then when someone sends you changes, you can merge those changes into your working branch, and then your collaborator can grab the merged version of the project and continue working from the new current version.



### Difference between ***Git*** and *GitHub*
Before we dive in, let's clear up a common misconception: Git isn't the same thing as GitHub. Git is a version-control system (i.e., a piece of software) that helps you keep track of your computer programs and files and the changes that are made to them over time. It also allows you to collaborate with your peers on a program, code, or file. GitHub and similar services (including GitLab and BitBucket) are websites that host a Git server program to hold your code.


## Code along

*** For this presentation I have created an automated script that will auto install programs useful to git **

Main script is a setup script that will setup any mac system
Things that will be installed 

* HomeBrew - A package manager that will download any programs you need and install through command line
* Git - Version control
* Mac down - A markdown editor helpful in editing readmes
* Git completion - press tab on half completed text to cycle through options in CLI

To run the installation 

Paste this script into a Terminal prompt:

```
bash <(curl -sL https://raw.githubusercontent.com/ilya0/OracleGit/master/main)
```


### Manually Installing Git on your computer
Install Git with Homebrew
If you have installed Homebrew to manage packages on OS X, you can follow these instructions to install Git:

Open your terminal and install Git using Homebrew:

$ brew install git
Verify the installation was successful by typing which git --version:

$ git --version
 git version 2.9.2
Configure your Git username and email using the following commands, replacing Emma's name with your own. These details will be associated with any commits that you create:

$ git config --global user.name "Emma Paris" 
 $ git config --global user.email "eparis@atlassian.com"
(Optional) To make Git remember your username and password when working with HTTPS repositories, install the git-credential-osxkeychain helper.



### Creating an online Repository

Step 1. The easiest way to get started is to create an account on [GitHub.com](www.github.com) (it's free).

Step 2: Create a new repository
A repository is like a place or a container where something is stored; in this case we're creating a Git repository to store code. To create a new repository, select New Repository from the + sign dropdown menu (you can see I've selected it in the upper-right corner in the image above).

![](https://opensource.com/sites/default/files/u128651/git_guide3.png)

Enter a name for your repository (e.g, "Demo") and click Create Repository. Don't worry about changing any other options on this page.

Congratulations! You have set up your first repo on GitHub.com.





Step 3: Create a file
Once your repo is created, it will look like this:

![](https://opensource.com/sites/default/files/u128651/git_guide4.png)

This is a new repo on GitHub
Don't panic, it's simpler than it looks. Stay with me. Look at the section that starts "...or create a new repository on the command line," and ignore the rest for now.

Open the Terminal program on your computer.

Copy the block under create a new repository on the command line.

~~~
echo "# Demo" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ilya0/Demo.git
git push -u origin master
~~~

Paste the text in terminal in the folder you have created.

Press enter and a readme and the file association will be created.





### Stages of a commit

1. echo "# Demo" >> README.md
	* Creates #Demo text and places it in the README.MD file to be created	
2. git init
	* intializes git file to store all the git information
3. git add README.md
	* add readme to git 
4. git commit -m "first commit"
	* That's it! You just created a Git commit and included a message that says first commit. You must always write a message in commit; it not only helps you identify a commit, but it also enables you to understand what you did with the file at that point. So tomorrow, if you add a new piece of code in your file, you can write a commit message that says, Added new code, and when you come back in a month to look at your commit history or Git log (the list of commits), you will know what you changed in the files.
5. git remote add origin https://github.com/ilya0/Demo.git
	* Let's look at this command step by step. We are telling Git to add a remote called origin with the address https://github.com/<your_username>/Demo.git (i.e., the URL of your Git repo on GitHub.com). This allows you to interact with your Git repository on GitHub.com by typing origin instead of the full URL and Git will know where to send your code. Why origin? Well, you can name it anything else if you'd like.
6. git push -u origin master
	* push the commit to the master directory

	
	
	
	
	



## Git Branching - Branches in a Nutshell
	
	
Nearly every VCS has some form of branching support. Branching means you diverge from the main line of development and continue to do work without messing with that main line. In many VCS tools, this is a somewhat expensive process, often requiring you to create a new copy of your source code directory, which can take a long time for large projects.


### Git Branches
A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, staging area, and project history. New commits are recorded in the history for the current branch, which results in a fork in the history of the project.

The git branch command lets you create, list, rename, and delete branches. It doesn’t let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands.


![https://wac-cdn.atlassian.com/dam/jcr:746be214-eb99-462c-9319-04a4d2eeebfa/01.svg?cdnVersion=jc]()

The diagram above visualizes a repository with two isolated lines of development, one for a little feature, and one for a longer-running feature. By developing them in branches, it’s not only possible to work on both of them in parallel, but it also keeps the main master branch free from questionable code.


Common Options
~~~~~
git branch
~~~~~
  
List all of the branches in your repository. This is synonymous with git branch --list.

~~~~~
git branch <branch>
~~~~~

Create a new branch called <branch>. This does not check out the new branch.

~~~~~
git branch -d <branch>
~~~~~

Delete the specified branch. This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.

~~~~~
git branch -D <branch>
~~~~~
Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.

~~~~~
git branch -m <branch>
~~~~~
Rename the current branch to <branch>.
~~~~~
git branch -a
~~~~~
List all remote branches. 

##Creating Branches
It's important to understand that branches are just pointers to commits. When you create a branch, all Git needs to do is create a new pointer, it doesn’t change the repository in any other way. If you start with a repository that looks like this:

![https://wac-cdn.atlassian.com/dam/jcr:80aa77d2-c28f-415e-ab10-e3612456a9c1/02.svg?cdnVersion=jc
]()

[https://www.atlassian.com/git/tutorials/using-branches]()

~~~~
git branch crazy-experiment
~~~~
The repository history remains unchanged. All you get is a new pointer to the current commit:

![https://wac-cdn.atlassian.com/dam/jcr:b0e2f237-9337-4385-be22-43f623e133d0/03.svg?cdnVersion=jc
]()

### Deleting Branches
Once you’ve finished working on a branch and have merged it into the main code base, you’re free to delete the branch without losing any history:

~~~~~
git branch -d crazy-experiment
~~~~~

###The Merge Option
The easiest option is to merge the master branch into the feature branch using something like the following:

![](https://wac-cdn.atlassian.com/dam/jcr:01b0b04e-64f3-4659-af21-c4d86bc7cb0b/01.svg?cdnVersion=jc)

~~~~
git checkout feature
git merge master
~~~~

Or, you can condense this to a one-liner:

~~~~
git merge master feature
~~~~

This creates a new “merge commit” in the feature branch that ties together the histories of both branches, giving you a branch structure that looks like this:



![](https://wac-cdn.atlassian.com/dam/jcr:e229fef6-2c2f-4a4f-b270-e1e1baa94055/02.svg?cdnVersion=jc)

Merging is nice because it’s a non-destructive operation. The existing branches are not changed in any way. This avoids all of the potential pitfalls of rebasing (discussed below).

On the other hand, this also means that the feature branch will have an extraneous merge commit every time you need to incorporate upstream changes. If master is very active, this can pollute your feature branch’s history quite a bit. While it’s possible to mitigate this issue with advanced git log options, it can make it hard for other developers to understand the history of the project.



### The Rebase Option

As an alternative to merging, you can rebase the feature branch onto master branch using the following commands:

~~~
git checkout feature
git rebase master
~~~

This moves the entire feature branch to begin on the tip of the master branch, effectively incorporating all of the new commits in master. But, instead of using a merge commit, rebasing re-writes the project history by creating brand new commits for each commit in the original branch.

![](https://wac-cdn.atlassian.com/dam/jcr:5b153a22-38be-40d0-aec8-5f2fffc771e5/03.svg?cdnVersion=jc)

The major benefit of rebasing is that you get a much cleaner project history. First, it eliminates the unnecessary merge commits required by git merge. Second, as you can see in the above diagram, rebasing also results in a perfectly linear project history—you can follow the tip of feature all the way to the beginning of the project without any forks. This makes it easier to navigate your project with commands like git log, git bisect, and gitk.

But, there are two trade-offs for this pristine commit history: safety and traceability. If you don’t follow the Golden Rule of Rebasing, re-writing project history can be potentially catastrophic for your collaboration workflow. And, less importantly, rebasing loses the context provided by a merge commit—you can’t see when upstream changes were incorporated into the feature.

 
##Presentation
1.Explain the essence git and github

2.Create a github account

3.Install github 

4.Clone

5.Push and Pull

6.Branch and merge, rebase

7.Group merge and pull request



## Important commands - Quick guide

- Git status - Status
- Git remote -v - list all currently configured remote repos
- Git Init - initialize git
- Git add- add to the commit list
- Git reset - reset from a version
- Git merge - Merge gits
- Git Log - Show changes
- Git push - push to a repo
- Git diff - compair changes
- git diff [code] - shows changes between tracked files
- Git Pull - fetch and merge changes on the remote server
- Git Clone - create a working copy of local repo
- Git checkout - shows you the code
- Git fork - Copy git from one person to your git account
- Git Clone - Clone to local system from github account
- Git Push - push to local github account
- Git push <repo> <branch> 
- git push origin master
- Git pull - pull to git hub repo
- git pul <repository> <branch> -
- git pull upstream master - 
- Git Pull request (button)  -pull 
- Git add . - adds all the files                         - adds all the git changes on the list

- rm -rf .git - Remove a git
	
	Links
	https://www.atlassian.com/git/tutorials/merging-vs-rebasing
	