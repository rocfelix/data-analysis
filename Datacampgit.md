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

Add one or more files to the staging area.
Commit everything in the staging area.
To add a file to the staging area, use git add filename.
