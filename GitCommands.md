### Adding information to the User config file

		git config --global user.name "alanr"
		git config --global user.email "alan@robsonmail.com"

Take me to my home directory
		
		cd ~

(c:\users\alan)

### To list the folder .congfig

git config --list

or a particualr setting

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

