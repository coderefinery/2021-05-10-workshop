+++
+++

# Questions and notes from workshop day 1

## Icebreaker

What’s the most important thing you’d like to learn this week?
- Jupyter notebook
- Version control
- Learn more about how to use git and GitHub
- Reproducible research and collaborative workflow.
- Version control (Git) and basic programming set-up
- Learning to use Git properly
- Better workflows
- Version control
- Reproducibility
- Jupyter.
- Workloflow for test and production environment.
- Managing complex code and CI
- How these workshops are conducted and how to be a good excersise lead
- code organization..
- Share code with collegues
- Do not know
- Collaborative distributed version control
- Project organisation / version control
- Git /Github
- good coding practices
- Git/Github usage, writing clean code
- writing clean code
- Jupyter notebook
- Getting comfortable with Git (and to motivate myself to use it even when I am not collaborating)
- Jupyter
- Jupyter
- Collaborative version control
- Reproducible workflows, version control and modular code development
- good practice software documentation and control
- using Git and GitHub
- Modular coding
- Get my group up to speed with colaborative coding!
- FAIR
- Using Git and GitHub
- What are all the potential uses of Git and GitHub by open source modeling communities of practice
- Write cleaner codes
- Jupyter Notebook
- Incorporating git and version control practice in researh code development.
- Efficint git-use
- writing more efficient codes
- Git tricks and testing
- collaborative coding
- testing in git
- license
- structured perspective on coding in general
- Advanced version control


## Workshop introduction

https://github.com/coderefinery/workshop-intro/blob/master/video.md

- How to change name on zoom?
  - click on participants, then next to your name there is "rename"

- How to exit the edit mode? I see it now, thanks
  - top right there is an "eye" button
  - sometimes the "eye" button is on the top left

- How do we access the recorded lessons? And for how long?
    - The recording will be available in Twitch (the streaming service we use) for two weeks. If possible (we have a clean recording), it will also be posted to youtube
    - we probably will also put them on youtube (https://coderefinery.org/lessons/#video-recordings) but this depends on some postprocessing to make sure nobody appears there who did not want to

- Should we leave answering questions here to coderefinery staff only, or should participants also try answering questions posed in hackmd?
    - Instructors and expert helpers are also learning here, so it might well be that participants have valuable input. Actually that is pretty much certain! So feel free to also participate in providing answers! :+1:
    - we will see that it will be interesting to sometimes see multiple different answers so please answer, comment, complete :+1:

- Will breakout rooms be recorded? May we unmute ourselves there?
    - They will not be recorded.
    - We encourage unmuting and openly discussing/collaborating during the break out rooms.
    - If you are uncomfortable with this, then you of course do not have to use video/audio.


## Introduction to Git https://coderefinery.github.io/git-intro/

- Will we have breaks?
  - there was a coordination problem but for future sessions we plan 10 minutes every hour. sorry that this was not clearly communicated at this stage but we will communicate this more clearly for other workshop days.

- Awesome screen sharing of the instructor there:)
  - Congrats to the instructor for the coolest setup
  - It is amazing. The future is here. I want this too.
  - Mad skills at mirrored writing ;)
  - I am jealous, rocking setup! +1
  - Woah! What an amazing way to make us understand the importance of version control

- What is the URL to the video the instructor showed?
    - https://www.youtube.com/watch?v=CvbLVVRzJF8
    - love it!

- Once you undo from v3 to v2, is v3 completely lost?
    - one can do this in multiple ways in Git. Some are "unsafe" and throw away changes, while others are "safe" and allow you to always retrieve work. We will learn about this soon

- so a snapshot is like the doc v1.1. in the video?
    - Kind of! The version control snapshots have some extra features, like the information about from which snapshot it was derived (this solves the "I have a 1.2 but I think it's different than your 1.2"). And then later, when you for example feel like you want to release a specific version of your work (e.g. "this is the code with which the results in the paper were obtained"), many version control platforms, including GitHub, offer the option of releasing specific versions of the repository. So it might get a bit confusing to hold on to the "v1.1" thinking at that point, but the analogy is good for the moment.

- Is it a bad error? "Stopping at filesystem boundary (GIT_DISCOVERY_ACROSS_FILESYSTEM not set)."
    - The git repository has not been created yet.  `git init` in the right place.
    - It's not possible to give a Single True Answer that covers all situations, but my first guess might be that you are perhaps initializing your git repository somewhere where there is already a lot of content, and perhaps e.g. other storage media (usb stick etc)
    - solution (probably/hopefully): create a folder first, step into it, `git init` inside the new folder

- Rather than typing `git add ....` two times (for different files), could we have not done `git add .` directly so that all the changes could've been saved at once?
  - Yes.  Sometimes we do things a certain way for demo purposes
  - Sometimes `add .` might add too much if it's not ignored (`git status` would hint at that).

- Do you always work from terminal? Are git GUIs really that useless?
  - no they are useful but we start in the terminal to get an understanding of what is really happening "underneath" but later we will also move to the web interface and mention other graphical interfaces. GUIs can be great for this
  - for example GitHub Desktop is quite good, or the online Gitpod.io. But to learn and understand the concepts, it is indeed good to learn the commands in a terminal. And most of the special and advanced options are only available as commands

- Git replaces LF with CRLF. Can there be a case where this becomes a problem?
    - No, as far as I know. This is because Windows and Linux use different line endings and git is adjusting to make them compatible. I have never seen it cause a problem.
    - For the purposes of this workshop, almos certainly not a problem
    - Does anyone remember how to _safely_ turn off this warning? Is `git config core.autocrlf true` always OK?
    - The command posted above didn't work for me. I'm still having the warning. But, if it doesn't cause any problems, it's supposed to be fine I guess.
      - we can also try to fix this later via screenshare when we have some time but it won't cause any trouble for the workshop
    - It's correct to get the **warning**!👍🏽 And `core.autcrlf true` is the correct setting, always 😊

- My video is disable, can you enable it please?
  - Solved!
      - A host or co-host can click "ask to start video"
      - great

- When saving and closing nano I get the message: 'Error in /usr/share/nano/git.nanorc on line 1: Regex strings must begin and end with a " character  - (other line) not understoodare/nano/git.nanorc on line 2: Command' and more. Any idea?
   - which operating system?
       - Win 10
   - I haven't seen this error before but it means that a file installed along with Nano contains unexpected characters so to me it looks like installation didn't go 100% well. We could look into that git.nanorc file to find out what characters confuse it, or ignore it or we could try a different editor.
   - Does it still save the file though?
       - Thank you, I can try a different editor; anyway, it does save the file. Adding and committing work well
       - vs code is working well, no strange errors

- Can I use other text editors than nano? What commands may I use for them?
    - You can use any text editor you prefer (both graphical and terminal-only). Which editors are available depends on your OS and environment. Which OS are you using?
        - Win 10
        - Good other alternatives on Win can be VS Code, Atom, or NotePad++. Here we show how you can connect Git to them: https://coderefinery.github.io/installation/shell-and-git/#step-2-setting-an-editor
        - Here we have overview of other editors: https://coderefinery.github.io/installation/editors/
        - Thanks very much! I have VS code; will configure that

- Isn't the GUI an option only if you push the commit to the remote repositpry? (Or if we start with the GUI from the remote repository in the first place)
    - not really. try typing git gui on your gitbash terminal on windows. you can do stages and commits via the gui. some text editors such as Atom, VScode also have git gui integrations even for local commits and changes. hope this answers you!
        - Thanks! Didn't know about this :)
        - TIL! nice


## Exercise: Git basics

Exercise goals:
- start with an introduction
- redo this section on your side: https://coderefinery.github.io/git-intro/02-basics/#type-along-tracking-a-guacamole-recipe-with-git
- up to and including: https://coderefinery.github.io/git-intro/02-basics/#exercise-record-changes
- Ends at 10:25 CET, be back in main room then
- Have a 10 minute break
- for older zoom the "raise hand" is under participants instead of reactions

- how do we access the 'task instructions' page that Sabry is using?
    - Scroll up a bit to see links to this
    - https://coderefinery.github.io/git-intro/02-basics/#exercise-record-changes
    - has this answered the question? (because I didn't 100% understand the question but I was also distracted)
    - yes thanks!! :)

- Could you address this, please: warning: LF will be replaced by CRLF in ingredients.txt.
    - see a bit above (same question), it is a warning about different line endings used by different OS and may be ignored for this workshop
    - Windows represents the end of a line differently than Linux, and it just converted between them.

- I'm testing sharing my terminal, but how do I finish sharing? Can not find any button, nothing.
    - OK, I see now, there's a bar in the middle top of the whole screen area, not in the shared window.
    - There's likely a thin bar at the top or bottom of your zoom with "stop sharing" or something like that
    - it may vanish in between but can usually be found when moving mouse around at the edges of the screen
    - If you have multiple screens, the status bar might also show up on one of your secondary screens.


## Summary of Git basics

https://coderefinery.github.io/git-intro/02-basics/#summary


## The staging area

https://coderefinery.github.io/git-intro/04-staging-area/


### Advantages and disadvantages of the git commit message examples

This is referring to https://coderefinery.github.io/git-intro/04-staging-area/#discussion

- pro of Example 2: independent features are in independent commits. Can cherry-pick.
    - Can be especially useful for debugging purposes if one of the features breaks something elsewhere. With approach #1, finding the feature that breaks things would be more difficult.
- Con of Example; good luck finding out what you actually did 2 years later.
- .
- .Ex1 and 2 both include the name of files that has been changed but nothing about the change (in Ex. 2)
- Pro of Example 4. Easy to find changes to specific features.
- .Ex4 con: Too much information! May be hard to track back
-  Con of example 4: hard for outsiders to understand and committing separate changes in the same commit
- Con of Ex.5 : No information at all! Just the date doesn't give one any idea as to what happened
  - also the date is anyway already tracked in metainformation
- Example 2 is good for outsiders, since it says when some feature was implemented, and example 4 is good for the developer in order to keep track of everything, while the others are super bad
  - that's a great summary! because often we work as in 4 but may or many not want to clean up towards 2
    - right, in the end if everything is good it would be better to clean up! Thanks!
- Pro of 1: concise, but if features are very important could easily be lost if you search for the addition of a specific feature, 2 is pretty good, clear and easy to search back, 3 is useless because of the volume of things that are tied to this one commit, 4 is way to wordy and hard to track, 5 is not useful because date and what was done are not tracked elsewhere
    - will be a problem when these features become bugs :wink:


### More questions/comments

- What does "feature" mean?
  - A single (ideally independent) piece of functionality implemented in code. For example:
      - add a test for a function
      - adds a new function to plot a graph
      - replace an existing function to plot a graph
  - Content in a repository is not necessarily code. A feature could also be a new section in a text document or revisions from a proofreading of a text document. :+1:

- Is there a keyboard shortcut for the clear command in the terminal?
   - One can define an alias for the commands that one is using often.
   - Control-L does it in some terminals (:+1: on OSX terminal & Git Bash on Win) :+1:
     - Control-L works! Thanks!

- AFAIK git only works with plaintext source files. Is it possible to use with word files somehow? :smile:
  - git can work with any format but it is true that it works less well with huge binary files and also with non-plaintext files it will not show useful "diff"
  - thanks!
  - I am not a Word expert but in this case I would track the manuscript in some other format (like markdown or LaTeX or something plain text) and use conversion tools like pandoc to convert to Word if this helps communicating with co-authors who refuse to use other tools.

- Why `git diff` or `git diff --staged` do not give any resuls?
    - if your repository is up to date (no change after last commit) there is nothing to show.
    - use `git status` to check if there are any changes and whether your repository is up to date (works for both staged and unstaged changes)
    - also git diff shows changes in modified files, but does not show if you have e.g. added a whole new file.

- In the previous example we used git commit without using git add before. How does that work? Ok i see the explanation is just coming now :)
  - you can `git commit somefile` without staging first but in the long run, staging first (maybe multiple times) and committing in a second step can be a useful practice to review the staged (prepared) commit before committing it

- How can I see the difference between working dir and commited section? Is it possible?
  - if nothing is staged: `git diff`
  - if something is staged: `git diff HEAD` (because here a `git diff` would only show difference between staged and working dir)
  - not sure `HEAD` was explained yet but we will clarify latest tomorrow. Instead of `HEAD` you can also refer to the branch name (typically `master` or `main`; again more about it tomorrow)

- It says "git reset # unstages staged changes" but in the image, it shows reset: committed --> staged?
  - good catch! this is confusing and I think the text description is possibly not fully correct. will follow-up in an issue: https://github.com/coderefinery/git-intro/issues/293
  - to unstage I would use `git restore` as indicated there
      - but restore isn't even there at all :/
        - we need to update the image, `git restore` is relatively new
      - the good news is that git will remind you of the command to use. If you do `git status` after you have staged some changes, git will tell you what command to use to unstage the changes
  - and indeed `git reset --soft` can move from committed to staged

- I find this staging difficult to understand without hands on example.
    - Agree
    - exercise coming up :)
    - let us know if it is unclear after the exercise


## Exercise: staging area

https://coderefinery.github.io/git-intro/04-staging-area/#exercise-using-the-staging-area

Also: "test your understanding" if time allows.

- git checkout had no effect (git version 2.30.0.windows.1)
  - I assume that there was no change between working tree and staging area and then `git checkout somefile` indeed has no effect
  - the command is `git restore --staged <filename>` in git 2.3
    - ah yes. this has been recently changed and the command is more intuitive. we have been a bit conservative changing the material because not everybody comes with recent enough git
  - `git reset <filename>` works (to unstage, not to undo latest changes in working dir)

- demonstration of `-p` with `git add` would be nice (or at least emphasize its use), since it's probably usually better to use `add` than `commit`
  - I use it when I did several changes in my file(s) but want them to become separate commits. So at least for me, most of the time, I can go fine without `-p` if I make small enough commits. But it is a super useful flag.
  - Example of a workflow:
      - `vi file1.txt` # edit file1.txt
      - `vi file2.txt` # edit file2.txt
      - `...`          # do further changes to files
      - `git add .`    # will add all the modified files to the staging area, which may not be what you want
      - `git add -p`   # selectively use which modifications to include in the staging area/index

- It was a bit annoying to be kicked out of BR just to wait for two minutes and then stop anyway...
  - Yeah, we know.  It's a bit of a strategic decision to force people to take breaks.  We will work on minimizing this downtime later.
  - In the past when we tried to take breaks inside the breakout room, we observed that breaks were often skipped.

- Is it possible to download all the material of the workshop?
  - All material is on GitHub and tomorrow we will learn how to clone it (download it): https://github.com/coderefinery
  - But also we plan to never remove any material. But it may and will evolve. Our plan is to also soon upload citable versions to Zenodo with a DOI.
  - Some lessons that we will go through will use a different webpage format which will make it easier to save to PDF directly.
  - Super! :+1:

- When trying to configure atom as text editor, by typing `git config --global core.editor "atom -nw"`, I get this message: `error: could not lock config file %USERPROFILE/.gitconfig: No such file or directory`. What is the fix?
    - Student here; you might need to specify the directory location of atom. Not sure though
    - Possible solution [here](https://superuser.com/questions/688563/trying-to-install-and-create-new-git-repository-for-first-time-i-think-disconn)

- In the example workflow, is it possible to revert to checkpoint 3 instead of 4?
  ```
  $ git add file.py                 # checkpoint 1
  $ git add file.py                 # checkpoint 2
  $ git add another_file.py         # checkpoint 3
  $ git add another_file.py         # checkpoint 4
  # ... further work on another_file.py ...
  $ git diff another_file.py        # diff w.r.t. checkpoint 4
  $ git checkout another_file.py    # oops go back to checkpoint 4
  $ git commit                      # commit everything that is staged
  ```
  - great question. no it would not be possible. so I use this strategy only when I know I don't need to go back to the step before. In doubt it would be better to commit every step since then you can go back to any previous commit. Also it's no problem to combine commits later so in doubt, make many commits :-)
  - In a real emergency, web search for "git reflog" and with enough effort I think you can
    - but I don't think `git reflog` will be able to go back in this particular case

- Apologies if I missed this, but will the recordings be ready before tomorrow's session? This would be useful for some of the learners who couldn't attend today's session.
  - The stream recording will be available on https://www.twitch.tv/coderefinery immediately after the course.
      - Finished broadcasts will end up here: https://www.twitch.tv/coderefinery/videos
  - YouTube posting if video quality is good and without attendee video.


## Ignoring files

https://coderefinery.github.io/git-intro/02-basics/#ignoring-files-and-paths-with-gitignore

- Can you ignore the entire directory?
  - yes, in your `gitignore` you can list folder names (e.g. a folder called `generated` or `build`) and it will ignore everything below. you can also use wildcards.
  - Example contents of a `.gitignore` file:
    ```
    # This is a comment.

    # Ignore build folder:
    build/

    # Ignore all .pyc and .so files:
    *.pyc
    *.so
    ```
  - can also use https://www.toptal.com/developers/gitignore to generate gitignore files

- I missed what one includes in the `.gitignore`: e.g. if I want to exlude .so files?
  - you want to list there all files and folders which are generated by the build process. For Python projects it would be `*.pyc` and `__pycache__`. If this was a LaTeX project, you may want to ignore everything except `*.tex` and `*.bib`.
    - How can you ignore everything except `*.tex`, for example? Is there a way?
        - I believe you must use ! ..
        - Ex. `!*.tex`. But it will be better to organize all your files in a folder and ignore the folder.
  - More examples depending on the programming language: https://github.com/github/gitignore
  - the `.so` files example was an example relevant for projects written in C, C++, Fortran, ...


## Undoing and recovering

https://coderefinery.github.io/git-intro/05-undoing/

- so checkout fetched the version from git and overwrites the local file?
  - yes. `git checkout filename` will overwrite local unstaged modifications with the latest staged or committed version. It is to my knowledge the only or one of the few Git commands where I cannot go back to how it was before. All other Git commits can be turned back.
    - and it only works when I haven't committed yet?
       - if all changes have been staged or committed, then `git checkout filename` will have no effect
       - Committing does not change the staging area, so it will work also after committing. If you stage the file again, checkout will get the newly staged version.

- Just to make sure, checkout only works for unstaged files, reset for the staged files and revert for commited, right?
    - Checkout will copy a file from staging area to the working directory.
    - Revert to staged.
    - (If you want, you can take a file from a commit instead. `git checkout HEAD filename` will copy it from the latest commit.)

- I am having trouble understanding the difference between the use of reset and checkout commands
    - If a file is staged, you may use:
        - `git reset <file>` or equivalently, `git restore --staged <file>` to remove a file from the staging area but keep the changes in the working directory
   - If a file is modified but unstaged:
       - `git checkout <file>` or equivalently `git restore <file>` will revert the changes done in the working directory, check out to the latest commited version
   - When applied to files (instead of branch switching): Checkout changes the "working directory".  Reset changes the staging area.  Both are some sort of revert of what they adjust.
   - And if you are confused, it is not your fault. It is confusing and the `restore` commands got added later because `checkout` was too confusing since it semantically can do at least two very different things (tomorrow we will see how it behaves when we use branches)
   - +1 git has really bad user interfaces
     - some of the interfaces have "evolved" and seem like they haven't been "designed" and now it can be too late to change them

* What does the `echo` command do?
  - `echo "something"` will print "something" in the terminal output (try it). This can also be used to write a text portion into a file (this is what the instructor did)

- Does `reset` change the file in the working directory after moving it out from the stage area?
    - No. `git reset <file>` will keep the changes in the working directory.
    - Side note: the exception would be when using the `--hard` flag - this might actually change the files.

---

## Feedback for today's sessions. What went well? What should we change?

Please write one thing that was particularly good:
- Sabry's cool explanation on the board
- Speakers mostly tried to talk clearly and slowly
- very interactive and carefully explained
- Nice intro on main basic commands to get started with .git, the break-out rooms were quite effective and helpful.
- very nice with breakout rooms for trying on our own AFTER being explained in the main room
- very nice to try the commands in the breakout rooms right after the explanation
- Having a flowchart about staging and committing was helpful :+1:
- Material accessible at all times, though a bit scattered (HackMD, schedule, material: we always need to keep looking at multiple windows)
- Overall good mix og "listening" and "doing" sessions
- Great materials and preparation.
- thumbs up for the effort and initiative
- It is really great to have a "sum up" of all the commands we used in the end of each section

Please write one thing we should change/remove:
- The staging part was confusing
- The last section on remove/retrieve file was a bit too fast to follow
- I think it would make it less confusing if we had a flowchart or smth to show the difference between `checkout`, `reset` and `revert` +1+1+1+1
- Some instructors were pretty fast when using the commands in the terminal. If one has never seen the commands just going slowly would make it a lot easier to follow.
- The git rm (message incomplete ...)
- less time dedicated to "can you hear me" and "do we do a break now?", and more to BR.
- a bit too fast the last part of the day, after the last break.
- not sure if it was open, but having the breakrooms open during the breaks. For people that is still doing the exercises or wants to interact
  - We have done that some times before, but also sometimes we want to ensure a break actually happens.  Maybe we should leave the rooms open even more.
- The first exercises basically assumes that all the creation of the recipe folder was already done. When that is not the case, time in the breakout room is used to create the starting point, which takes away time for doing the exercise and discussing.
  - We should be more clear about "type-along" times
- When zoom doesn't change on time, it takes time to rejoin, then it's a bit hard to follow up
- (Not about the presentations) it would be good as exercise leader to know how many people are supposed to be in your group.
- A program or the day can be created and shared with the instructors and exercise leaders prior to the workshop day. The program should include a time wise schedule of the topics to be covered in a 30 mins slot, when a breakout session will take place, etc. This will be helpful for the teaching team and exercise leaders to be aware that a breakout room is approaching for example
- the program and schedule could have been more transparent. Having clear heading helps focusing.
- Too many place to look at for the program, the exercises, the instructions and the questions. Bit confusing
  - We should clarify, focus on HackMD only during the workshop.  Plus lesson webpage, but you should be able to get those links from HackMD.
- The informal afterparty is useful, but we need to know when we can leave
  - After the course, or after the afterparty?
