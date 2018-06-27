

## What is Git?

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

### What is version control?

Git is, first and foremost, a version control system (VCS). There are many version control systems out there: CVS, SVN, Mercurial, Fossil, and, of course, Git.

Git serves as the foundation for many services, like GitHub and GitLab, but you can use Git without using any other service. This means that you can use Git privately or publicly.

If you have ever collaborated on anything digital with anyone, then you know how it goes. It starts out simple: you have your version, and you send it to your partner. They make some changes, so now there are two versions, and send the suggestions back to you. You integrate their changes into your version, and now there is one version again.

###Git snapshots
Git takes snapshots of a project, and stores those snapshots as unique versions.

If you go off in a direction with your project that you decide was the wrong direction, you can just roll back to the last good version and continue along an alternate path.

If you're collaborating, then when someone sends you changes, you can merge those changes into your working branch, and then your collaborator can grab the merged version of the project and continue working from the new current version.



### Difference between Git and GitHub
Before we dive in, let's clear up a common misconception: Git isn't the same thing as GitHub. Git is a version-control system (i.e., a piece of software) that helps you keep track of your computer programs and files and the changes that are made to them over time. It also allows you to collaborate with your peers on a program, code, or file. GitHub and similar services (including GitLab and BitBucket) are websites that host a Git server program to hold your code.



## Code along

Step 1. The easiest way to get started is to create an account on [GitHub.com](www.github.com) (it's free).

Step 2: Create a new repository
A repository is like a place or a container where something is stored; in this case we're creating a Git repository to store code. To create a new repository, select New Repository from the + sign dropdown menu (you can see I've selected it in the upper-right corner in the image above).

![](https://opensource.com/sites/default/files/u128651/git_guide3.png)

Enter a name for your repository (e.g, "Demo") and click Create Repository. Don't worry about changing any other options on this page.

Congratulations! You have set up your first repo on GitHub.com.





Step 3: Create a file
Once your repo is created, it will look like this:

![](https://opensource.com/sites/default/files/u128651/git_guide4.png)
New repo on GitHub
Don't panic, it's simpler than it looks. Stay with me. Look at the section that starts "...or create a new repository on the command line," and ignore the rest for now.

Open the Terminal program on your computer.

Copy the block under create a new repository on the command line.

~~~
echo "# needstobedeleted" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ilya0/needstobedeleted.git
git push -u origin master
~~~

Paste the text in terminal in the folder you have created.

Press enter and a readme and the file association will be created.





## Stages of a commit

1. echo "# needstobedeleted" >> README.md
	* Creates #needstobedeled text and places it in the README.MD file to be created	
2. git init
	* intializes git file to store all the git information
3. git add README.md
	* add readme to git 
4. git commit -m "first commit"
	* That's it! You just created a Git commit and included a message that says first commit. You must always write a message in commit; it not only helps you identify a commit, but it also enables you to understand what you did with the file at that point. So tomorrow, if you add a new piece of code in your file, you can write a commit message that says, Added new code, and when you come back in a month to look at your commit history or Git log (the list of commits), you will know what you changed in the files.
5. git remote add origin https://github.com/ilya0/needstobedeleted.git
	* Let's look at this command step by step. We are telling Git to add a remote called origin with the address https://github.com/<your_username>/Demo.git (i.e., the URL of your Git repo on GitHub.com). This allows you to interact with your Git repository on GitHub.com by typing origin instead of the full URL and Git will know where to send your code. Why origin? Well, you can name it anything else if you'd like.
6. git push -u origin master
	* push the commit to the master directory

	
	
	
	
	



## Git Branching - Branches in a Nutshell
	
	
Nearly every VCS has some form of branching support. Branching means you diverge from the main line of development and continue to do work without messing with that main line. In many VCS tools, this is a somewhat expensive process, often requiring you to create a new copy of your source code directory, which can take a long time for large projects.
	
	

	

	
	
	

Git merging

Git checkout -b <branch name>
git checkout <branch>
git merge <branch>




Git init - intialize repo

Git clone /path/to/repo - create a working copy of local repo

git add . - add all files

git commit -m “message” - commit files

git commit -a -commit all files you’ve changed

git push origin master - send changes to the master branch of your remote repo

git status - get the status of the git on that file directory

git remote add origin <server> - adding a server to push to

git remote -v - list all currently configured remote repos

git pull - fetch and merge changes on the remote server


Git status - Status
Git Init - initialize git
git add- add to the commit list
Git reset - reset from a version
Git merge - Merge gits
Git Log - Show changes
Git push - push to a repo
Git diff - compair changes
git diff [code] - shows changes between tracked files
Git Pull - pulling gits
Git Clone - Make a copy
Git checkout - shows you the code
Git fork - Copy git from one person to your git account
Git Clone - Clone to local system from github account
Git Push - push to local github account
Git push <repo> <branch> 
git push origin master
Git pull - pull to git hub repo
git pul <repository> <branch> -
git pull upstream master - 
Git Pull request (button)  -pull request button o 
Git add .                          - adds all the git changes on the list

rm -rf .git - Remove a git
	
	
	