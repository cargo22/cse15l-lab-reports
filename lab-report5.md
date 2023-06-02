# Debugging

This week, we'll be working towards becoming more efficient when it coems to debugging code. No one is perfect. Programmers make mistakes ALL THE TIME. There's no shame in making an error, and sometimes, pinpointing the error seems almost impossible. Therefore, we will be looking at a scenario where a student is stuck and doesn't know how to move forward. My job is to help them find an answer and to fix the bug.

This is the student's submission on EdStem:

________________________________________________________________________________________________________________________________
Title: **Unknown Bug - Need Help**

Type of Question: **Debugging**

What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

**I am on a Windows operating system. I am using VS Code, and that's where my problem lies.**

Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

**I wrote a bash script to run my java files and called it test.sh. However, upon calling the command I get an error in the terminal indicating that the file does not exist. Here is a screenshot of the output:**

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/31628b26-1ab0-4219-bf25-28f63cd1f19f)

**I expected the result of the JUnit test.**

Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

**In this case, running bash test.sh in the terminal is the failure-inducing input. My code seems correct and I don' think the error is coming from there.**

________________________________________________________________________________________________________________________________

In this case, it can be extremely frustrating trying to figure ou what needs to be fixed. The best we can do is try to figure out more of the code and trying to really understand the student's coding environment. When a file is not found, the likely case is that these files are in different directories. In this case, I would respond with something along the lines of:

________________________________________________________________________________________________________________________________

**Can I see your VS Code window? I would like to assess your coding environment to see if we can pinpoint the bug. Thank you!**

________________________________________________________________________________________________________________________________

Once we get a screenshot of the student's work environment, hopefully we can find the answer to the student's question. Often times, it's hard to understand how a bug is happening if we aren't given the entire picture. It's sort of like trying to find where a puzzle piece goes if we are only given 10% of the puzzle. The chances are, we won't know where to put the piece. Sometimes it will be doable with little information, but most of the time it would just be an educated guess. Now let's look at the student's screenshot.

________________________________________________________________________________________________________________________________

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/45ca13d9-f4d5-4af3-80e0-0cf4de356409)

________________________________________________________________________________________________________________________________

There's our answer. Now that we see his file explorer on the left hand side of the screen, it is easy to note what the error is. All the files that they want to test is in the starter directory, but the test.sh file is in the parent directory of the file. Therefore, there are plenty of ways we can help this student. Here's how I would reply: 

________________________________________________________________________________________________________________________________

**It looks like the test.sh file is not in the same directory as the Java files you are trying to test. The files are in the starter directory, meaning there's two ways you could go about this.**
1. **You could go to the test.sh file and write "cd starter" on the first line, before you call the JUnit tests.**
2. **You could move the test.sh file in starter directory and then cd into the starter directory to run the files.**

________________________________________________________________________________________________________________________________

Great! Now we fixed the student's problem. It's easy to find bugs once we have all the pieces to the puzzle. However, it turns out we aren't done. The student replies indicating that they are receiving another error. This is what they say: 

________________________________________________________________________________________________________________________________

**The bug seems to be fixed. However, I now get an error when running my tests. Once again, I'm confident that my code doesn't have any errors, so I just wanted to know why I'm getting errors again. Attached is a photo of the environment.**

![image](https://github.com/cargo22/cse15l-lab-reports/assets/97927174/c3f1e393-8540-485f-99ea-d77c1af31d0d)

________________________________________________________________________________________________________________________________

This is a very common thing to happen with programmers. One bug dies, but another one arises. There could be a chain of a million bugs, and we won't see what the expected output is until we fix every single bug. It's just the way it is. The good thing is, the student understands how important it is to assess the environment and sent a screenshot in which we could observe everything wrong with the code. In this case, we can see exactly what type of error it is and what line it is found at. This is what the terminal yields: 

java.lang.IllegalArgumentException: Could not find class [PublicTester.java]

When we cannot find a class, that could mean a variety of things. However, if we look closely at the class name, we see that the class name has the extension '.java'. This shows that there was at one point in the code in which the terminal was told to search for a class named PublicTester.java. Let's look further down to see if we can find a line at which this happens.

After looking at where the error was found, it's not really clear. In this case, we just have to think to ourselves, where would we need the name of a class. Typically, that comes when calling the javac and java commands. Therefore, let's look to see when they're called and hopefully we can pinpoint the error. When looking at the test.sh file, we see the java commands. Sure enough, there is the error. On line 4, when the student calls the java command to compile the code, the student put PublicTester.java instead of PublicTester. Let's get back to them and make sure they fix that error. My response would look something like this:

________________________________________________________________________________________________________________________________

**It seems that you have made an error when compiling the code. Make sure that when you run the java command, you give a class name, not the entire name of the file.**

________________________________________________________________________________________________________________________________

Now we have successfully fixed the student's code! 

## Reflection

I have learned a lot of cool things. However, the thing I learned and thought was the coolest was changing my coding environment. Funnily enough, I was getting tired at looking at the boring Visual Studio Code, so I changed my font and color scheme and it surprisingly made me really excited to do some more coding. This class really inspired me to learn more code on my own, and it also taught me a lot of essential fundamentals for bash and other things like VIM and SSH. Everything I learned this quarter has been extremely useful and I can't wait to continue with my coding journey. Thank you for an amazing quarter.




