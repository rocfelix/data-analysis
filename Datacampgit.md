# 1. Basic Workflow

Repository has two parts:
1. Files
2. Directories

## Where does Git store information?

Git stores all of its extra information in a directory called '.git'

Suppose your home directory /home/repl contains a repository called dental, which has a sub-directory called data. Where is information about the history of the files in /home/repl/dental/data stored?

Answer: /home/repl/dental/.git



## How can I check the state of a repository?

$ Git status 

This command is used to check the state of repository. 

## How can I tell what I have changed?

Git has a staging area in which it stores files with changes you want to save that haven't been saved yet. 

$ git diff

----------------------------------------
diff --git a/report.txt b/report.txt
index e713b17..4c0742a 100644
--- a/report.txt
+++ b/report.txt
@@ -1,4 +1,4 @@
-# Seasonal Dental Surgeries 2017-18
+# Seasonal Dental Surgeries (2017) 2017-18

 TODO: write executive summary.

--------------------------------------

## What's the first step in saving changes?


You commit changes to a Git repository in two steps:

1. Add one or more files to the staging area.
2. Commit everything in the staging area.

To add a file to the staging area, use git add filename.


## How can I tell what's going to be committed?

To compare a file's current state to the changes in the staging area, you can use git diff -r HEAD path/to/file. The -r flag means "compare to a particular revision", HEAD is a shortcut meaning "the most recent commit", and the path to the file is the relative to where you are (for example, the path from the root directory of the repository). We will explore other uses of -r and HEAD in the next chapter.




## How do I commit changes?

To save the changes in the staging area, you use the command git commit. It always saves everything that is in the staging area as one unit: as you will see later, when you want to undo changes to a project, you undo all of a commit or none of it.

When you commit changes, Git requires you to enter a log message. This serves the same purpose as a comment in a program: it tells the next person to examine the repository why you made a change.

By default, Git launches a text editor to let you write this message. To keep things simple, you can use -m "some message in quotes" on the command line to enter a single-line message like this:

git commit -m "Program appears to have become self-aware." (Here all files in staging area have been commit)

## How can I view a repository's history?

The command git log is used to view the log of the project's history. Log entries are shown most recent first, and look like this:

commit 0430705487381195993bac9c21512ccfb511056d
Author: Rep Loop <repl@datacamp.com>
Date:   Wed Sep 20 13:42:26 2017 +0000

    Added year to report title.
The commit line displays a unique ID for the commit called a hash; we will explore these further in the next chapter. The other lines tell you who made the change, when, and what log message they wrote for the change.

When you run git log, Git automatically uses a pager to show one screen of output at a time. Press the space bar to go down a page or the 'q' key to quit.

## How can I view a specific file's history?

A project's entire log can be overwhelming, so it's often useful to inspect only the changes to particular files or directories. You can do this using git log path, where path is the path to a specific file or directory. The log for a file shows changes made to that file; the log for a directory shows when files were added or deleted in that directory, rather than when the contents of the directory's files were changed.

You have been put in the dental repository. Use git log to display only the changes made to data/southern.csv. How many have there been?


## How do I write a better log message?
Writing a one-line log message with git commit -m "message"is good enough for very small changes, but your collaborators (including your future self) will appreciate more information. If you run git commit without -m "message", Git launches a text editor with a template like this:

/# Please enter the commit message for your changes. Lines starting
/# with '#' will be ignored, and an empty message aborts the commit.
/# On branch master
/# Your branch is up-to-date with 'origin/master'.
/#
/# Changes to be committed:
/#       modified:   skynet.R
/#
The lines starting with # are comments, and won't be saved. (They are there to remind you what you are supposed to do and what files you have changed.) Your message should go at the top, and may be as long and as detailed as you want.



