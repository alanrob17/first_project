### Advantages of Distributed Version Control Systems

Torvalds insisted on a distributed system because of the independence it affords to
developers. With a distributed system, you can work on your copy of the code
without having to worry about ongoing work on the same code by others. What
makes it even better is that any distributed copy of the project can contain all the
history of the project. A distributed system also lets you work offline, meaning you
can make changes without having access to the server that stores the central repository.

Another advantage of distributed systems is that you can sync your repositories
among yourselves, bypassing the central location. Let’s say the access to the main
server goes down and you have to collaborate with a colleague. You can share
changes with your colleague and continue to work on the project together, and then
later push all your changes to the location everyone has access to.

In a centralized system, anyone who makes a change needs to be given access to
the central location. In contrast, in a distributed system, new developers can make
changes to their own repositories without being granted write access, while more
experienced contributors can be given write access and the ability to review other
contributions before merging them into the repository. Managing access is easier in
distributed systems.

### Adding information to the User config file

		git config --global user.name "alanr"
		git config --global user.email "alan@robsonmail.com"

Take me to my home directory
		
		cd ~

(c:\users\alan)

### To list the folder .congfig

git config --list

or a particular setting

git config user.name


### Help

	git help

	git help log

### Create a new project repository

		$ cd ~
		$ cd documents
		$ mkdir first_project
		$ cd first_project
		$ git init
 
#### Results

		alanr@LION ~/documents/first_project
		$ git init
		Initialized empty Git repository in c:/Users/alanr/documents/first_project/.git/

The storing and tracking information is stored in the **.git** folder.

### To create a first commit

		git add .
		git commit -m "Initial commit"
		
#### Results

		alanr@LION ~/documents/first_project (master)
		$ git commit -m "Initial commit"
		[master (root-commit) 38498c8] Initial commit
		2 files changed, 86 insertions(+)
		create mode 100644 GitCommands.md
		create mode 100644 GitCommands.md.bak		

The process we are going to use for our work will be,

> make changes
> add the changes
> commit changes to the repository with a message

### Writing commit messages

Our first message was too simple. We need to write more descriptive messages. In the first case we should have said that we had created a file named ...

Label in the present tense not the past tense. "Fixes a bug" not "fixed a bug".

Use a text editor to create multiline messages for major changes. Try and make the line lengths to a maximum of 72 characters.

#### Commit History

		git log
		
#### Results

		alanr@LION ~/documents/first_project (master)
		$ git log
		commit e4b4226421a73ff1c5bbd48a29f12d089c8b556d
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:10:57 2016 +1100
		
			more information added to the file.
		
		commit 38498c8e0fd2f7484f96e337a43b4624637a4fe0
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:00:47 2016 +1100
		
			Initial commit		

Limit the number of commits from the log.

		$ git log -n1
		commit e4b4226421a73ff1c5bbd48a29f12d089c8b556d
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:10:57 2016 +1100
		
			more information added to the file.			
			
Will just bring back the latest.


Can search for a date

		$ git log --since=2016-01-1
		commit e4b4226421a73ff1c5bbd48a29f12d089c8b556d
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:10:57 2016 +1100
		
			more information added to the file.
		
		commit 38498c8e0fd2f7484f96e337a43b4624637a4fe0
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:00:47 2016 +1100
		
			Initial commit


Everything until the 2nd of January

		$ git log --until=2016-01-02
		commit e4b4226421a73ff1c5bbd48a29f12d089c8b556d
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:10:57 2016 +1100
		
			more information added to the file.
		
		commit 38498c8e0fd2f7484f96e337a43b4624637a4fe0
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:00:47 2016 +1100
		
			Initial commit

Search for an author. You can use quotes or leave them out. Can search for a part name

		$ git log --author=alanr
		commit e4b4226421a73ff1c5bbd48a29f12d089c8b556d
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:10:57 2016 +1100
		
			more information added to the file.
		
		commit 38498c8e0fd2f7484f96e337a43b4624637a4fe0
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:00:47 2016 +1100
		
			Initial commit
			
			
Can use grep

		$ git log --grep="Init"
		commit 38498c8e0fd2f7484f96e337a43b4624637a4fe0
		Author: alanr <alan@robsonmail.com>
		Date:   Sat Jan 2 13:00:47 2016 +1100
		
			Initial commit
			
Will search for the string "Init"	

### Get the status of you files

        git status
        
This command will tell you if you have any changes that haven't been committed.

e.g.

		$ git status
		On branch master
		Changes not staged for commit:
		(use "git add <file>..." to update what will be committed)
		(use "git checkout -- <file>..." to discard changes in working directory)
		
				modified:   GitCommands.md
		
		no changes added to commit (use "git add" and/or "git commit -a")
		
### Differences in files


		git diff

or
		
		git diff GitCommands.md

### Remote Repositories

To create a remote repository on Github

		git remote add origin https://github.com/alanrob17/first_project.git
		
		git push -u origin master

When this is working properly there is some code added to **.gitconfig**.

		[remote "origin"]
			url = https://github.com/alanrob17/first_project.git
			fetch = +refs/heads/*:refs/remotes/origin/*
