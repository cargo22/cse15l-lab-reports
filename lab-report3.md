# Working with less

This week, we'll be taking a look at the less command in the command line. We will take a look at all the different options and ways in which we can use less to help us 
look through files in a directory/repository. For reference, we will be basing off of this website: [less commands](https://phoenixnap.com/kb/less-command-in-linux).

## First Option -E
The -E extension to less allows us to scroll through the file in the terminal and then it'll completely disappear once you've reached the end of the file. With less, 
the entire file shows in the terminal. Every time you press the down arrow, you essentially scroll through the file and then the terminal will advise you once you've 
reached the end. However, the -E extension makes the entire file disappear in the terminal once you've reached the end.

Here is an example of running less -E:

```
$ less -E technical/911report/preface.txt
```

Once running the command, the terminal immediately greets you with this:

```
            PREFACE
            We present the narrative of this report and the recommendations that flow from it to
                the President of the United States, the United States Congress, and the American
                people for their consideration. Ten Commissioners-five Republicans and five
                Democrats chosen by elected leaders from our nation's capital at a time of great
                partisan division-have come together to present this report without dissent.
            We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                the United States. The nation was unprepared. How did this happen, and how can we
                avoid such tragedy again?
            To answer these questions, the Congress and the President created the National
                Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November
                27, 2002).
            Our mandate was sweeping. The law directed us to investigate "facts and circumstances
                relating to the terrorist attacks of September 11, 2001," including those relating
                to intelligence agencies, law enforcement agencies, diplomacy, immigration issues
                and border control, the flow of assets to terrorist organizations, commercial
                aviation, the role of congressional oversight and resource allocation, and other
                areas determined relevant by the Commission. In pursuing our mandate, we have
                reviewed more than 2.5 million pages of documents and interviewed more than 1,200
                individuals in ten countries. This included nearly every senior official from the
                current and previous administrations who had responsibility for topics covered in
                our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
                From the outset, we have been committed to share as much of our investigation as we
                can with the American people. To that end, we held 19 days of hearings and took
                public testimony from 160 witnesses.
            Our aim has not been to assign individual blame. Our aim has been to provide the
                fullest possible account of the events surrounding 9/11 and to identify lessons
:
```

To better understand what is being displayed, we need to understand the use of ':' The colon basically prompts user input so that we can do certain things within the file. 

In this case, we are now at the end of the file.

![image](https://user-images.githubusercontent.com/97927174/236658076-85c468ff-e125-405c-846a-75e7b65f704d.png)

When I press down one more time, the terminal will collapse instead of telling me that I am at the end of the file. Here is the result:

![image](https://user-images.githubusercontent.com/97927174/236658155-0a80c676-efbe-4152-a067-1ec6094ac48e.png)

It takes me right back to the terminal, and the history shows that we did indeed call less -E.
I know that might've been a bit difficult to understand, so here's how less without -E works. When you scroll to the end of a file in less, it gives you this alert:

![image](https://user-images.githubusercontent.com/97927174/236658212-7adde74c-63ce-420b-9c90-277fd8d2fe77.png)

As you can see, the terminal advises you that you are at the end of the file, but it is hard to find your way back to the terminal if you don't know the shortcuts.
Therefore, less -E allows us to exit just by pressing the down arrow one more time. Let's try another example. In this case I will call a different file from the same 
directory. I will be running this command: 

```
$ less -E technical/biomed/rr196.txt
```

Once again, we are immediately greeted with output of the file in the terminal:

```
        Introduction
        Elastase-induced emphysema in rodents is the most widely
        studied animal model for human emphysema. Several
        alterations in diaphragmatic structure and function have
        been demonstrated in this model. Among these are diaphragm
        fiber shortening with a corresponding shift in the
        length-tension curve [ 1 2 3 4 5 ] and variable changes in
        the contractile properties of diaphragm strips
        in vitro [ 2 3 5 6 ] . Increased
        fatigue resistance of the muscle is the single alteration
        in contractile properties that has been most consistently [
        2 3 6 ] , though not always [ 7 ] , identified. This
        fatigue resistance has been accompanied by an increased
        oxidative capacity in the diaphragmatic muscle fibers as
        demonstrated by increased activities of citrate synthase [
        7 8 ] and succinate dehydrogenase (SDH) [ 2 3 ] .
        In contrast, fiber type has generally not been found to
        be significantly altered in the diaphragms of emphysematous
        animals [ 1 2 3 8 ] , although in all reports addressing
        this issue the fibers were typed histochemically rather
        than by myosin heavy chain (MHC) composition. Furthermore,
        the kinetics of diaphragmatic muscle contraction that one
        would expect to result from shifts in fiber type
        distribution, such as time to peak tension, have also
        generally [ 2 3 6 9 ] , but not always [ 7 ] , been found
        to be unaltered in emphysema. A change in fiber type
        distribution in the diaphragm of emphysematous hamsters was
:
```

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

Once again, we are given the text in the file, exactly like what was displayed when we called less -E (which is why I won't display it again). However, this time, let's say we want to search for a pattern within a file. Let's say that I input this after the colon:

```
/ThAnK
```

This will search for all words in the file that contains the string 'thank,' regardless of case. The results will be highlighted within the terminal. Let's see what that looks like.

```
...skipping...
            As we complete our final report, we want to begin by thanking our fellow
                Commissioners, whose dedication to this task has been profound. We have reasoned
                together over every page, and the report has benefited from this remarkable
                dialogue. We want to express our considerable respect for the intellect and judgment
                of our colleagues, as well as our great affection for them.
            We want to thank the Commission staff. The dedicated professional staff, headed by
                Philip Zelikow, has contributed innumerable hours to the completion of this report,
                setting aside other important endeavors to take on this all-consuming assignment.
                They have conducted the exacting investigative work upon which the Commission has
                built. They have given good advice, and faithfully carried out our guidance. They
                have been superb. We thank the Congress and the President. Executive branch agencies
                have searched records and produced a multitude of documents for us. We thank
                officials, past and present, who were generous with their time and provided us with
                insight. The PENTTBOM team at the FBI, the Director's Review Group at the CIA, and
                Inspectors General at the Department of Justice and the CIA provided great
                assistance. We owe a huge debt to their investigative labors, painstaking attention
                to detail, and readiness to share what they have learned. We have built on the work
                of several previous Commissions, and we thank the Congressional Joint Inquiry, whose
                fine work helped us get started. We thank the City of New York for assistance with
                documents and witnesses, and the Government Printing Office and W.W. Norton
                & Company for helping to get this report to the broad public.
            We conclude this list of thanks by coming full circle: We thank the families of 9/11,
                whose persistence and dedication helped create the Commission. They have been with
                us each step of the way, as partners and witnesses. They know better than any of us
                the importance of the work we have undertaken.
            We want to note what we have done, and not done. We have endeavored to provide the
                most complete account we can of the events of September 11, what happened and why.
                This final report is only a summary of what we have done, citing only a fraction of
                the sources we have consulted. But in an event of this scale, touching so many
                issues and organizations, we are conscious of our limits. We have not interviewed
                every knowledgeable person or found every relevant piece of paper. New information
:
```

I know you can't see it here, but every word with 'thank' is highlighted in the terminal. Here's an image:

![image](https://user-images.githubusercontent.com/97927174/236691623-18912570-688a-45dc-9567-8c5def6a3b63.png)

Pretty cool right. Now we will try it on a different file.







