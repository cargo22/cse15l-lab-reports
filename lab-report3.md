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

```
$ less -I technical/government/Alcohol_Problems/Session2-PDF.txt
```

Here is the immediate output:

```
Session 2.
Identifying ED Patients with Alcohol Problems

Robert Woolard, MD
Many patients in the emergency department (ED) have alcohol
problems, and they can be identified.1 Research on techniques used
to identify these patients has been conducted, but several areas of
interest should be addressed by further research. We need to
further examine and refine alcohol-screening questionnaires in the
ED. We need to determine the sequence and combination of questions
and tests that constitute the best screening process. We need to
study barriers to screening, identify factors that promote
screening implementation, and demonstrate the impact of a screening
program in the ED. The final aim of screening must be improved
outcomes through referral and counseling. Identification is only
the first step in a process of care.
Alcohol problems defined
Alcohol problems designate a spectrum from risk behavior to
illness, and from problematic consumption to alcohol use disorder.
We must be careful when interpreting the results of studies, and in
our own design of screening procedures, that we are clear about the
endpoints we are measuring. Clinicians in the ED are interested in
screening for several alcohol endpoints. Acute intoxication is of
concern to emergency physicians. Intoxication in a driver would
certainly be considered an "alcohol problem." The blood or breath
alcohol concentration (BAC), coupled with our clinical
observations, may help us identify intoxication. Most alcohol
screening tests identify patients with alcohol use disorders or
:
```

Now let's try to find a string within the file. Let's try to find "bAc"

```
/bAC
```
Here is the result:

![image](https://user-images.githubusercontent.com/97927174/236692098-ad2643b0-fd9d-46d4-bcbb-9ea96edc1cff.png)

We see that although BAC is capital and we searched for bAc, it still highlighted the term because it ignores the case.

Now that we've had a look at the -I extension, it's clear to see how useful it can be, especially when searching through large files and you forget the correct casing for a certain word. There are plenty of useful applciations for -I and it's important to know how to use it.

## Third Option -m

When scrolling through a file with less, it's hard to know how far in you are the file. Sometimes, it feels like you're scrolling forever and you just want the file to end or at least to know when the file will end. The cool thing about -m is that it tells you a percentage of how far in you are into the file. Let's test it

```
$ less -m technical/government/Alcohol_Problems/Session3-PDF.txt
```

Here is the immediate output:

```
Session 3.
Intervening with Alcohol Problems
in Emergency Settings

Carlo C. DiClemente, PhD* Carl Soderstrom, MD
Excessive alcohol consumption plays an important role in many of
the medical conditions, accidents, and injuries that cause visits
to emergency departments and trauma centers. Many studies have
documented the presence of alcohol among patients admitted to
emergency depart-ment1-5 and trauma center6,7 settings. Other
studies have demonstrated that even blood alcohol concentration
(BAC) determinations under-estimate the extent of alcohol problems
among the patients who are triaged and treated in emergency
settings.4,7 The prevalence of this co-factor to the emergency
admission, and the fact that alcohol is a risk factor both for the
first visit and for a return visit to the emergency setting, have
occasioned a call for an effective method of intervening with
alcohol problems in these settings.8-12 Although there are problems
with and barriers to intervening in these settings, a number of
studies and a few controlled trials indicate that interventions
focused on patients' drinking can reduce the amount of drinking as
well as injury episodes, including repeat re-admission for injury
and other negative consequences of drinking. This review will
examine the rationale for intervening, types of interventions and
interveners, and barriers and concerns that need to be addressed.
Then we will offer suggestions for research and practice related to
intervening effectively with alcohol problems in emergency
technical/government/Alcohol_Problems/Session3-PDF.txt 2%
```

Notice the difference? It says 2% at the end, indicating that we are only 2% in to the file. Lets go to the end and see what that looks like.

```
DiClemente agreed that efficacy in the ED setting had not been
totally established. He noted that many practices that do not have
efficacy or effectiveness studies behind them are adopted and
become guidelines for standard practice. Once that happens, it is
very difficult to get support to re-evaluate them, so it is true we
must be careful when evaluating social science and psycho-social
interventions. However, we are so sophisticated psychometrically
and methodologically that virtually every piece of research can be
dissected, revealing flaws and problems. If we continue to do that,
we will never make any changes in services. He recommended a
balance between the rigor of research and the application process
that needs to happen.


100%
```

The 100% indicated that we have reached the end of the file and that there is nothing more to be read. Pretty cool. Now you can exit the file. However, what happens when you combine -m with -E. With just -E, you kind of just scroll until you reach an end. Once you reach the end, it's too late because you're already out of the file. Therefore, combining the two allows you to know that you've reached the end of the file and that pressing the down arrow once more will exit you out the file.

Let's try it:

```
$ less -m -E technical/government/Alcohol_Problems/Session4-PDF.txt
```

Here, we see that we are at the end of the file. What happens if we press down arrow one more time?
```
Robert Woolard favored continuing intervention research in EDs.
He believed that the realities of our practice settings help drive
the development of new ways of delivering counseling, for example,
computer-based methods. While emergency physicians may not have the
time or interest, the patients do. He suggested that research in
trauma centers and EDs can help alcohol researchers learn more
about the interventions they have already developed and can even
lead to novel interventions.

100%
```

This is the result:

![image](https://user-images.githubusercontent.com/97927174/236700420-6a747f2a-44a0-482d-9ba6-14b768f6f5b1.png)

It takes you back to the terminal, just like how -E does.

Overall, -m is useful to know generally how long a file is and how far deep you are into reading a file. If you want to know how much reading you have left or how much longer the file is, the percentage counter allows you to get a gist of just how far in you are into a file. This could be useful in many ways, especially when combined with other options, as shown above when we combined -m with -E. -m just makes life easier for the reader.

## Fourth Option -X

When we use less, quitting out of file view means everything disappears and we're back in the terminal. However, what if something important was in the file and we forgot to jot it down? Now we need to revisit the file and find the important information and that could take forever. However, -X allows us to keep the file in the terminal, at least where we left off. Instead of everything disappearing, everything you just read before prompting less to quit will still appear in the terminal right above the new command line entry. Let's try it.

```
$ less -X technical/plos/pmed.0020281.txt
```

This is the output: 

```

        Whistleblowers serve no function if they cannot tell their stories. The present story of
        whistleblowing—as discussed, in part, in
        PLoS Medicine —that involves the pharmaceutical industry, pharmaceutical
        benefit management corporations, the managed care industry, and the political and lobbying
        forces that zealously guard their secrets could not have been told without the help of
        courageous men and women [1, 2] For that reason, those of us who congregated in Washington,
        D.C., on May 15th, 2005, at the invitation and support of the Public Library of Science and
        the Government Accountability Project feel particularly humbled and grateful to these two
        sponsors. Our convictions could not have been aired were it not for the essential First
        Amendment work of responsible journalists, who exemplify the best in investigatory
        research.
        For me, whistleblowing is not a theoretical exercise. It has a human face and tangible
        features. It is the face of children and adults who have been injured or killed by
        misrepresented pharmaceuticals; clinical research trial results that have been sequestered
        from the scientific community and whose incomplete findings cause injury; and
        pharmaceuticals that are detailed to physicians, not to save lives or necessarily improve
        the health or welfare of the recipients, but to make money.
        In the lonely and, at times, discouraging world of whistleblowing, we whistleblowers are
        passionate, and often successful, because our efforts have a different goal than the
        corporations and political interests whose operations we occasionally challenge. Our goal
        is to tell the truth. That honest effort is the source of any ethical difference we can or
        might make. Truth is the basis for the power of a whistleblower, one that can withstand the
        assault of unprecedented odds against being heard put forth by that sum of political power,
        expediency, and money.
        A whistleblower's success depends upon competent and articulate media. The debate to
        improve the status quo—be it in pharmaceutical marketing or managed-care decision
        making—cannot proceed or flourish without it.
        Ralph Waldo Emerson, American essayist and philosopher (1803–1882), commented about
        success (I have adapted his comments for all of us who gathered in Washington in mid-May
        2005): “To leave the world a bit better, whether by a healthy child, a garden patch or a
        redeemed social condition; to know even one life breathed easier because you have lived;
        this is to have succeeded [as a whistleblower].
```

Okay, everything seems to be normal as it would when you normally call less. However, let's quit now. Let's see the result:

```
carlo@Carlos_Victus MINGW64 ~/Downloads/CSE/stringsearch-data-main
$ less -X technical/plos/pmed.0020281.txt





        Whistleblowers serve no function if they cannot tell their stories. The present story of
        whistleblowing—as discussed, in part, in
        PLoS Medicine —that involves the pharmaceutical industry, pharmaceutical
        benefit management corporations, the managed care industry, and the political and lobbying
        forces that zealously guard their secrets could not have been told without the help of
        courageous men and women [1, 2] For that reason, those of us who congregated in Washington,
        D.C., on May 15th, 2005, at the invitation and support of the Public Library of Science and
        the Government Accountability Project feel particularly humbled and grateful to these two
        sponsors. Our convictions could not have been aired were it not for the essential First
        Amendment work of responsible journalists, who exemplify the best in investigatory
        research.
        For me, whistleblowing is not a theoretical exercise. It has a human face and tangible
        features. It is the face of children and adults who have been injured or killed by
        misrepresented pharmaceuticals; clinical research trial results that have been sequestered
        from the scientific community and whose incomplete findings cause injury; and
        pharmaceuticals that are detailed to physicians, not to save lives or necessarily improve
        the health or welfare of the recipients, but to make money.
        In the lonely and, at times, discouraging world of whistleblowing, we whistleblowers are
        passionate, and often successful, because our efforts have a different goal than the
        corporations and political interests whose operations we occasionally challenge. Our goal
        is to tell the truth. That honest effort is the source of any ethical difference we can or
        might make. Truth is the basis for the power of a whistleblower, one that can withstand the
        assault of unprecedented odds against being heard put forth by that sum of political power,
        expediency, and money.
        A whistleblower's success depends upon competent and articulate media. The debate to
        improve the status quo—be it in pharmaceutical marketing or managed-care decision

carlo@Carlos_Victus MINGW64 ~/Downloads/CSE/stringsearch-data-main
$
```

I'm now back at the terminal, but as you can see, all the text is still there. Therefore, I can now access the text I just read just by scrolling up in the terminal, making access to certain phrases much easier.

Now let's combine it with -m. Let's see what happens.

```
$ less -X -m technical/plos/pmed.0020209.txt
```

This is the output: 

```
        A year ago, I received an E-mail from a research scientist at a major pharmaceutical
        company. The scientist had read my articles on whistleblowers who had raised concerns about
        the undue influence of the pharmaceutical industry on American medicine My industry source
        had information for me about drug company practices, but—out of fear of career ruin—would
        only talk on the condition that I would conceal the scientist's identity.
        For the next year or so, I had repeated contacts with the scientist. As I listened to
        this researcher—and to the other medical whistleblowers that I continued to interview—it
        occurred to me that each whistleblower was like the proverbial blind man with a hand on the
        elephant. Each could describe one piece of the puzzle, but the full picture could only
        emerge by bringing these whistleblowers together.
        With an eye to focusing on the systemic problems that have allowed American medicine to
        be unduly influenced by industry, on May 15, 2005, I brought together five whistleblowers
        in Washington, D. C. I asked them each to tell their story and to suggest ways to restore
        objectivity to medicine and medical research.


        The Whistleblowers
        Four whistleblowers attended in person, and the anonymous industry scientist
        participated via speakerphone. The whistleblowers came from an extraordinary variety of
        different professional backgrounds.



            David Graham
            This Food and Drug Administration (FDA) safety officer raised concerns about the
            cardiovascular side effects of rofecoxib (Vioxx) and other Cox-2 inhibitors. He
9%
```

As we can see, we know that we are 9% in to the file. However, let's quit now and see the result.

```
carlo@Carlos_Victus MINGW64 ~/Downloads/CSE/stringsearch-data-main
$ less -X -m technical/plos/pmed.0020209.txt





        A year ago, I received an E-mail from a research scientist at a major pharmaceutical
        company. The scientist had read my articles on whistleblowers who had raised concerns about
        the undue influence of the pharmaceutical industry on American medicine My industry source
        had information for me about drug company practices, but—out of fear of career ruin—would
        only talk on the condition that I would conceal the scientist's identity.
        For the next year or so, I had repeated contacts with the scientist. As I listened to
        this researcher—and to the other medical whistleblowers that I continued to interview—it
        occurred to me that each whistleblower was like the proverbial blind man with a hand on the
        elephant. Each could describe one piece of the puzzle, but the full picture could only
        emerge by bringing these whistleblowers together.
        With an eye to focusing on the systemic problems that have allowed American medicine to
        be unduly influenced by industry, on May 15, 2005, I brought together five whistleblowers
        in Washington, D. C. I asked them each to tell their story and to suggest ways to restore
        objectivity to medicine and medical research.


        The Whistleblowers





        A year ago, I received an E-mail from a research scientist at a major pharmaceutical
        company. The scientist had read my articles on whistleblowers who had raised concerns about
        the undue influence of the pharmaceutical industry on American medicine My industry source
        had information for me about drug company practices, but—out of fear of career ruin—would
        only talk on the condition that I would conceal the scientist's identity.
        For the next year or so, I had repeated contacts with the scientist. As I listened to
        this researcher—and to the other medical whistleblowers that I continued to interview—it
        occurred to me that each whistleblower was like the proverbial blind man with a hand on the
        elephant. Each could describe one piece of the puzzle, but the full picture could only
        emerge by bringing these whistleblowers together.
        With an eye to focusing on the systemic problems that have allowed American medicine to
        be unduly influenced by industry, on May 15, 2005, I brought together five whistleblowers
        in Washington, D. C. I asked them each to tell their story and to suggest ways to restore
        objectivity to medicine and medical research.


        The Whistleblowers
        Four whistleblowers attended in person, and the anonymous industry scientist
        participated via speakerphone. The whistleblowers came from an extraordinary variety of
        different professional backgrounds.



            David Graham
            This Food and Drug Administration (FDA) safety officer raised concerns about the
            cardiovascular side effects of rofecoxib (Vioxx) and other Cox-2 inhibitors. He

carlo@Carlos_Victus MINGW64 ~/Downloads/CSE/stringsearch-data-main
```

Interesting...This still does what it's supposed, but it doesn't print out the percentage that we were at. That tells us that -X only prints out strictly the contents of the file. Therefore, you can't get confused if there's a random number printed out in the terminal. When you use -X you can be assured that what you see is only what is in the file.

-X can be extremely useful. Instead of having to constantly call less again and again everytime you want to revisit a file, you can have it there in your terminal forever. All you have to do is just scroll up and find what you're looking for. This saves a bunch of effort, time, and keystrokes, making work more efficient, especially if you have to search through files.

## Conclusion
Those were four extensions to the less command. They all have their own purpose and can make life on readers much easier, especially when looking through large amounts of files with lots of contents stored in them. There are a bunch more extensions to the less command that are extremely interesting as well. If you want to look into them more, once again, visit this website: [less commands](https://phoenixnap.com/kb/less-command-in-linux).

Hack like a champion!


