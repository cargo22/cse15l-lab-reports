## How to Connect to Course-Specific Account 
Hello incoming CSE 15L students,

If you're wondering how to get started on your lab, here's a quick rundown as to how you need to connect to the remote server. 

However, we need to set up your coding environment.

First, you're going to need an interpreter. The one we recommend is VS Code. Download links for all operating systems are found here: [Link](https://code.visualstudio.com/download)

![image](https://user-images.githubusercontent.com/97927174/230689518-ba69dfad-d08b-4f19-860c-e6e396e4b42f.png)


Now, if you're like me and use a Windows machine, you'll need to install Git. The Git install link for Windows users is found here: [Link](https://gitforwindows.org/)

![image](https://user-images.githubusercontent.com/97927174/230690760-df0abf37-66fc-40c4-b1a0-df3694369e41.png)


Once you install Git(REMEMBER WINDOWS ONLY), you'll need to set it up in VS Code. Here are a couple steps to set it up:
  1. Open VS Code
  2. Open the terminal (Press ctrl + `)
  3. Open the command pallette by pressing (ctrl + shift + P)
  4. A search bar will appear. Type "Select Default Profile" in the search bar.
  5. Select "Git Bash"
  6. Press the "+" in the terminal (found in the upper right hand corner of the terminal)
  7. You're all set! You can now choose between Bash and Powershell

For everyone else, open up VS Code. It should look like this: 

![image](https://user-images.githubusercontent.com/97927174/230691744-df1e3a27-24bd-43a4-b576-67bce923c5b3.png)

Now that your VS Code is all set up and ready to go, we will now shift our focus to your course-specific account.

First, you're going to want to visit this website here: [Link](https://sdacs.ucsd.edu/~icc/index.php)

It should look like this:

![image](https://user-images.githubusercontent.com/97927174/230690845-a7a14acd-6932-42ab-bc6d-20570678b484.png)

Now that you've gotten there, input your username (the part before the @ in your UCSD email), and your ID (your PID with the A included).

You will be led to a page that looks similar to this: 

![image](https://user-images.githubusercontent.com/97927174/230691917-285ba8d6-5667-44d5-8471-f480b37d3771.png)

Now, click on your user-specific CSE 15L page and then click the Global Password Change Tool. It looks like this: 

![image](https://user-images.githubusercontent.com/97927174/230692182-e4d1aa42-fc31-46c9-8ccc-df860b9b0ed1.png)

Change your password for that account and REMEMBER IT. YOU WILL NEED IT TO CONNECT REMOTELY.

Now that you've set up your course-specific account, it's time to head back to VS Code and connect to the remote server.
When you're at VS Code, open a new terminal. Found here:

![image](https://user-images.githubusercontent.com/97927174/230692787-7325183c-9723-4955-8c1e-012608ff5225.png)

Once you open up your terminal, type this in:

$ ssh cs15lwi23zz@ieng6.ucsd.edu

Now remember, replace zz with the two letters that are relevant to your unique course-specific account.

For example, mine looks like this: 

![image](https://user-images.githubusercontent.com/97927174/230693960-6355e027-0989-42e2-8bb5-ff823032606e.png)

Press enter, and your result should display something along the lines of :

The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 

Type yes, and proceed.

Now, you should be prompted for a password. It should look like this: 

![image](https://user-images.githubusercontent.com/97927174/230694072-4a10fd31-124d-4f5d-a497-18e306313c1b.png)


Remember the password I told you to remember? Input it. I understand that you won't see a cursor or any letters that you are typing, but THAT IS OK. This is a security measure taken to prevent other people from seeing your password. Just type your password slowly and carefully and press enter. If done correctly, you should get something like this: 

![image](https://user-images.githubusercontent.com/97927174/230694250-98b64af5-2344-4cc2-bf61-0b9e068fd00a.png)

Now you have successfully connected to the remote servers in the CSE Basement!
