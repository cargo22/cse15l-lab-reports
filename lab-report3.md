# Working with less

This week, we'll be taking a look at the less command in the command line. We will take a look at all the different options and ways in which we can use less to help us 
look through files in a directory/repository. For reference, we will be basing off of this website: [less commands](https://phoenixnap.com/kb/less-command-in-linux).

## First Option -E
The -E extension to less allows us to scroll through the file in the terminal and then it'll completely disappear once you've reached the end of the file. With less, 
the entire file shows in the terminal. Every time you press the down arrow, you essentially scroll through the file and then the terminal will advise you once you've 
reached the end. However, the -E extension makes the entire file disappear in the terminal once you've reached the end.

In this case, we are at the end of the file.

![image](https://user-images.githubusercontent.com/97927174/236658076-85c468ff-e125-405c-846a-75e7b65f704d.png)

When I press down one more time, the terminal will collapse instead of telling me that I am at the end of the file. Here is the result:

![image](https://user-images.githubusercontent.com/97927174/236658155-0a80c676-efbe-4152-a067-1ec6094ac48e.png)

It takes me right back to the terminal, and the history shows that we did indeed call less -E.
I know that might've been a bit difficult to understand, so here's how less without -E works. When you scroll to the end of a file in less, it gives you this alert:

![image](https://user-images.githubusercontent.com/97927174/236658212-7adde74c-63ce-420b-9c90-277fd8d2fe77.png)

As you can see, the terminal advises you that you are at the end of the file, but it is hard to find your way back to the terminal if you don't know the shortcuts.
Therefore, less -E allows us to exit just by pressing the down arrow one more time. Let's try another example. In this case I will call a different file from the same 
directory.

Here is the end of the file:

![image](https://user-images.githubusercontent.com/97927174/236658561-3ffc4e68-6d36-4ab0-9497-31c36f9e6444.png)

...and here's the result of pressing the down arrow one more time.

![image](https://user-images.githubusercontent.com/97927174/236658574-6bbc1f1f-9a52-4890-b900-0b886ab55c60.png)

That's pretty much all there is to the -E extension. It's useful to avoid extra keystrokes when navigating a file and allows exit to be much easier.

## Second Option -I
One of the many benefits of the less command is that it allows you to search for specific things within a file. However, problems may arise. What if a word is overly 
complex and is hard to remember, or if you don't remember if a certain word is capitalized or not. With less, you can search for certain patterns by typing '/' at the 
terminal followed by the pattern you want to search for. However, -I allows us to search without worrying about case.

Here's what the initial input was

```
$ less -I technical/911report/preface.txt
```





