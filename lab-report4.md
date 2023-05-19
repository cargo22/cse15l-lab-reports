# Working With Vim

This week, we will be working with vim (and git) to make changes to code that needs to be changed. The code we're working with has errors, and we will use vim instead of a file explorer in an IDE to make edits and traverse files.

We will be completing these specific tasks:

1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file to fix the failing test
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account (you can pick any commit message!)

Let's get started.

## First Step

First, we need to log into ieng6 by typing in this:

```
ssh cs15lsp23mb@ieng6.ucsd.edu
```

We are now logged in: 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/a6082e46-4f04-4745-9785-1e74faafbf5c)

## Second Step

Now we need to fork this [repository](https://github.com/ucsd-cse15l-s23/lab7).

Press the fork button in the upper right hand corner,

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/7ef51e68-b83a-45ec-8ae7-2e29b3b659b3)

and then press the big green button that says 'Create fork'

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/4e4c358f-9d2f-4183-b8b1-fa3efefe62bf)

Now that we have our fork, we need to clone it into our ieng6 account. 

In order to do that, press the big green button that says 'Code'

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/14c393a8-ab61-452d-af5b-8357726b3d2c)

Then make sure you are in the SSH tab and copy the link to your clipboard.

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/2c5cb38b-1364-4c53-9717-d3d7a67f43bd)

Once you've copied the link to your clipboard, clone it in your terminal. This is what you should be typing in:

```
git clone git@github.com:cargo22/lab7.git
```

This is what the output should look like: 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/988502bd-937d-4580-a228-38c2c5df62f2)

Now that we have successfully cloned the repository into our ieng6 account, we need to make sure we're in the right place. Change into the lab7 directory by typing this:

```
cd lab7
```

Now, if you type 'ls' into the terminal, you should see all the files we are going to work with.

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/c56b193c-bdd6-42bf-96a5-9e9ba45f1889)

## Step three 

Now that we are in the right directory, we need to run the code to make sure that it fails. We do this by typing the following:

```
bash test.sh
```

This is the output: 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/d90cd51c-fadc-4f28-80c2-4ae6b7722cf5)

## Step four

Now that we know that the code is faulty, we need to fix it. This is where vim comes into place.

Into the command line, type the following:

```
vim ListExamples.java
```

You should see the entire file pop up.

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/abadaa22-8b1a-40eb-9300-30f3d82fddff)

Now that we have access to the file, we need to edit it to make sure that the code runs correctly. Thankfully, there is already a comment advising us of the change that needs to be made. We need to change index1 to be index2 in its very last instance. Keep note that when you first enter vim, we are in normal mode and it should stay that way.

Now that we are ready to edit, pay attention to every key I input.

First, type 

```
/x1 <enter>
```
(the '/' command allows us to search for certain patterns in a file)

This is the result:

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/8cdb249f-3a8c-4b0e-aa9f-f66bf3515fa0)

As you can see, it shows us the first instance in which x1 is called. So, how do we find that last index? Type this in:

```
<shift> n
```
(the 'n' command while searching allows us to look through all found instances of the patter in a file)

This is the result: 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/1dbb1677-ebf4-402d-9b5a-bbead1e6298d)

When in search mode, n scrolls down and N scrolls up. However, since we are already at the first instance, N takes us to the very last instance of 'x1'. Now we are right where we want to be. Now all we have to do is change the 1 to a 2. However, because the cursor placed us at 'x' we need to shift right one character by pressing

```
l
```
('l' is equvalent to the right arrow)

Now the cursor is over 1.

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/92fdb9b9-0360-4e87-a9e1-9de3b2d7b5bd)

Now we need to replace the one with a 2. In order to do that, we need to type:

```
r2
```
(the 'r' commands stands for replace and allows us to replace the value the cursor is on with the one we want to insert. Hence, the '2')

Now it should be replaced. 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/adb38fee-e909-4290-817c-2000fc7c1b84)

Now that we successfully edited the file, we need to save the changes and exit. Note, we are still in normal mode. So now we type this:

```
:wq <enter>
```
('wq' stands for save and quit)

Now we should be back in the terminal. 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/95a273a4-3929-4724-8c50-44531bbbec97)

## Step five

Now that we've made the edits, we need to rerun the tests to make sure that we've done it successfully. Because it's already in the history, we need to press the up arrow twice in order to be back at the bash test.sh command. Now, we press enter to rerun the tests. This is the output:
  
![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/819ac184-7f9b-4baa-a899-556372cf572b)

  
## Step six

Now that we've been assured that we successfully edited the file, we need to commit and push the changes back to our fork. This is how we'll do it. First, we need to type 

```
git add ListExamples.java
```
If done correctly, nothing should appear and it should just prompt the next input like this: 

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/eef3351f-9889-4db2-b491-7497ee605735)

Now, we need to commit the changes using this command:

```
git commit -m "save index change"
```

Keep in mind, whatever we put in the quotation marks doesn't really matter; it's just a way to remind us of the exact changes we made.
The result should look like this

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/e21e888f-bfd1-49b2-af1a-f36b57145de5)

Now that we have commited the changes, we need to push them to the main branch by typing this in:

 ``` 
 git push
 ```
 
 The output should look like this:
 
 ![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/6a6c3c57-bea1-4ac1-8da6-8d1ab8234e60)

We have successfully made our changes and we can check for ourselves on our GitHub account. It should appear and look something like this:

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/e4a3150c-535f-4bed-8a5b-d50111aa1231)


## Conclusion

Now you know how to edit files with vim as well as commiting those changes to the repository using git at the command line. However, it is important to note that this only works once you've set up your github account to be linked to your machine. Otherwise, you won't be able to push any commits. Hope these tips were useful!
