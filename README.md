# Intro-to-Git-exercise-1
In this exercise you will learn how to create a git repository, add files to it and track changes to those files.


First we need a folder to put our files and git repository in. **Create an empty folder.** Call it _example1_.

**Open a command line** tool of your choice and navigate to the empty folder you just created. (If you **right-click in the empty folder**, GitBash should be available in the menu)

On the command line, create an empty git repository.
```bash
git init
```

(If you set view to show hidden files, you should now see a _.git_ folder in your example1 folder.)

Congratulations. You have just created an empty git repository.
  

Now we need some files to track with our git repository. **Create some plain text files** in the example1 folder. You can add as many as you want, but **name one of them _code.txt_.**
  
  
**Type** `git status` on the command line now, to see how git is handling our new files. You should get something like the following:

```git
On branch master
Initial commit
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        code.txt
        lol.txt
        tests.txt
nothing added to commit but untracked files present (use "git add" to track)
```

We can see that git isn’t tracking our files. We need to _add_ them to the git repository. Add all the files.

```
git add .
```

git status will now look something like

```
On branch master
Initial commit
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   code.txt
        new file:   lol.txt
        new file:   tests.txt
```

We’re now ready to take our first snapshot of our files. In git, this is called a commit.

```
	git commit -m “Initial commit. Added empty project files.”
```

(The -m switch allows you to add a comment in the same command as making a commit.)


Congratulations, you have just made the first commit of your repository. You can see this commit if you type the command `git log`.


 
Let’s add some pseudo-code. **Open code.txt in a text editor and add the following**

>#variables  
>int i  
>string s  
>string git-foo  
>  
>#program  
>if git-foo is equal to good  
>    s = the fonz   
>else  
>    s = sad-face  
>  
>print 'hello world'  
>print s  

**Save** the file.

Typing `git status` on the command line should show _code.txt_ as being modified. This is good. Git knows that we have changed the file.

Let’s **commit that change.** (Remember that first, we have to add the file to staging before we can commit it.)
```bash
	git add code.txt
	git commit -m “Added pseudo-code.”
```
Git status should now show the working directory as _clean_.


**Go ahead and make some changes to the other files in your example1 folder and commit the changes.**  Remember, the `git status` command will show you what has changed since the last commit. `git log` will show you a list of your commits.


Go back to _code.txt_. We’re going to make some changes to the pseudo-code we wrote earlier. **Change the variable _git-foo_ to an array called _array-of-doom_.** Replace all the references throughout the code and save the changes.

Oh no, that hasn’t worked at all. Now our code doesn’t run. Fear not, we can use git to get our code back to how it was before. Type the following command
```bash
	git checkout -- code.txt
```
If we open _code.txt_ now, you should see that it has reverted back to when we had the _git-foo_ variable.


In this exercise, we have learned how to create a git repository and we have started to use it to track our files.
