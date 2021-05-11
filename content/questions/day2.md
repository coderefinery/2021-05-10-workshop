+++
template = "page-with-toc.html"
+++

# Questions and notes from workshop day 2

## Icebreaker question

What is your favorite programming/scripting language? Do you know any unusual ones?
- looking forward to Julia workshop.
- Python and R
- matlab...+1
- Favorite: Python; Unusual: x (C-like, extended to handle standard deviations)
- Julia
- Python and matlab
- Python is my most used, Med Associates / MED-PC is my most 'unusual' (for programming hardware in animal behavioral apparatus)
- Python
- Bash
- Python and C ... started with C and working with python since few months now
- C++
- Python +1
- python
- R is my most used and Python is what I most need to learn
- Python, IDL
- Python, C++, CUDA
- Python and JS
- Python, fortran
- Python, C++
- Unusual: FP (radical functional programming without variables and lambdas)
- Python for fast prototypes/development, C++ for fast code +1
- My favorite is C++, but i use python for postprocessing
- Python and Rust, really like the combination of both
- Python, but I would like to explore Julia more.
- Python, but I would also like to learn Julia.
- Julialang!
- I like using R but sometime python seems more logical. Now, I am more interested to learn Julia, Just waiting to see if it does not become another Theano.
- Unusual: LabVIEW
    - Not unsual, but I found it really different in comparison to Matlab or Python. 
- Python!
- JAVA
- Matlab and Python
- Unusual: Scala
- English (with ML- machine learning)
- HTML (just kidding)
    - 🤣 
- Python, C
- SML, Python, C++
- Python, Fortran



## Questions

Questions from today moved to https://coderefinery.github.io/2021-05-10-workshop/questions/ but feel free to add questions for tomorrow:

- @Sabry: how did you set up that amazing whiteboard + video behind? Could really use it for my own teaching :)
  -  I want to make video on how to make it but did not have time as the procedure is never finlized (trying with different material). I wll try my best to document this comeback to you. Not sure how to collect info please open an issue here so I would have some sort of list : https://github.com/Sabryr/LightBoard/issues

- Q: "See you tomorrow (Zoom and HackMD link stays the same!)"... Recommend always sending the zoom/hackmd links rather than leaving people to search old emails!
    - A: We sent one mass email to everyone, who need slightly different information.  We optimized by sending just one, but hopefully we can do better in the future
    - thanks for feedback. we should send one email to stream participants and one to zoom

- Just joined via Twitch and missed yesterday. Will the video end up permanently somewhere? I have the impression that you extended the course content since last year. Is this true?
  - It's somewhat similar, but continually developed.  Video at twitch.tv/coderefinery for 14 days, and hopefully (if no audiece appeared in the stream) on youtube permanently

- I can't turn on my video in a breakout room
  - We had to turn it off for you in the main room.  Use HackMD and request video on in your room, and a co-host will come.

- When I watch later the video on Twitch, how could I find the hackmds for each day, please? Via your website?
    - https://coderefinery.github.io/2021-05-10-workshop/questions/
        - The logic will be date-workshop/questions for all days?

- Instructor advice: how do you show your terminal with the command history in a sort of separate window above?
  - https://coderefinery.github.io/manuals/instructor-tech-setup/#terminal-history-window


## Git intro, branches and merging
https://coderefinery.github.io/git-intro/06-branches/

- What does `detached head` mean? If it is always pointing to the latest commit? 
    -  The easiest way to undestand this is as a tape recorder head. i.e. where will the changes be recorded if the record button is pressed.(There will be more about this soon)
   - and in this case the recorder head points to a commit directly and not to a branch; a branch is a label pointing to a commit hash

- discussion of `master` versus the move toward `main` would be good, I think.
    - Good point
    - In these basic lessons we make the strategic choice to not require almost everyone to upgrade to be able to change default name.  The point will come up later.
    - To setup local git to initialise new repos with `main`, use `git config --global init.defaultbranch main` (relevant only when starting a new repo locally with `git init`)
    - "Cultural sensitivity: The computer industry's use of the terms master and slave caught everyone's attention in the summer of 2020. Amid the many protests and the growing social unrest, these harmful and antiquated terms were no longer considered appropriate." (more @ https://www.theserverside.com/feature/Why-GitHub-renamed-its-master-branch-to-main)

"Both Conservancy and the Git project are aware that the initial branch name, 'master,' is offensive to some people and we empathize with those hurt by the use of that term," said the Software Freedom Conservancy."

- My git(2.7.4) don't have switch command. What should I do instead?
    - `git switch` requires a newer version of git (which is why we don't primarily recommend it)
    

- Do you know which version?
   - `git switch` requires version 2.23 at least (introduced on 2019-08-16 apparently)

- Can I delete the master / main branches?
    - If it is safe to delete, Git will let you do that (unless you force it). A safe condition would be that all commits on master already encoperated to a nother branch

- Can you branch from a branch? How far can you go with branching?
    - Yes you can
    - If there's a limit for the maximum depth, it's so ridiculously high you aren't likely to encounter it.



- If I have a public Git repository in GitHub and want to add new features. I can create a branch and modify it (or fork?). I would like to have the new branch private but still backed-up in GitHub or somewhere else if my computer brakes or if I want to work on the code on different computers? Will the branch be public or can you set it private? Other ways to deal with this?  Can one set different remote repository for different branches? How to marge the private branch with the public branch if they are in separate repositories?
  - The new branch will have the same visibility as the repository already has. 
  - If you work yourself, there is no need for forking. Forking is of relevance for instance when you want to contribute to a project that is private.
  - You can create a separate private repository (on Github or a local server)
    - When you push to the online repository, it happens for one branch at a time

- What does the tag "HEAD" stand for?
  - Basically "what is currently checked out", you see it points to a branch usually.
  - current position, "recorder head"

- Is there best practice for testing out whether changes on multiple branches actually "work" together? I.e. there may not be lines of code that conflict but the changes may be incompatible with each other. Should you create a new "test" branch and merge the new features together and test the software before incorporating with the master branch?

- I didn't attend yesterday, how could i understand my group number?
  - your question is how to find your group number?
  - You should have the group number in the email from us (sent on saturday). If not raise your hand on zoom and someone will help you (as you should not type your name here )

- I can't turn on video in breakout rooms
  - Write your breakout room number here and someone will come turn it on for you:

- What is the definition of the 'working tree?'
  - "The actually currently checkout files you can see with the file browser, which might possibly be edited already"

- What's the difference between the HEAD and the 'working tree'?
  - HEAD is pointing to a commit, so to a "saved" state. working tree can have local changes which could be neither staged nor committed.

- Is there a way to show the branch that a particular commit was done to? e.g. by using `git show <Hashid>` or something??
  - you mean: find out which branch(es) a commit belongs to?
  - If so, try `git branch -a --contains <commit>`

- How do I get the `git graph` command?
    - It is a custom alias, created via: `git config --global alias.graph "log --all --graph --decorate --oneline"`

- Why `git commit` does not work for newly created files and I am forced to use `git add` first? (the error is throwed was error: pathspec 'README.md' did not match any file(s) known to git)
  - git can only commit files it knows about. with `git add` we add a file or path to git to be tracked from here on.
 - So if added file ones (using `git add`) I can commit later directly right? 
   - yes, right. then only `git commit`, not `git commit somepath` 

- Note: `git switch` does not allow to "checkout" commits that are not "an end" of a branch (that is, it works to switch to branches but not to arbitrary commits _i.e._ DETACHED HEAD)
  - interesting! but you can do `git switch --create branchname somehash`
      - tested, nice 👍🏽
      - also for `git checkout` this is the preferred way to look at past commits, we will come back to that later today

- When staging, would you advise against using 'git add .' as good practice? I noticed we are not using it.
  - use `git add -u` which will stage all unstaged files. safer than `git add .` since the latter can stage too much (also new files that you may not want to track)
      - Thanks! Very useful!!

- yes emphasise one should be in the branch of interest. people might be in different branches. +1
    - If the question was about where to stand when issuing merge (if not let me know), ..
        - no question but a hint to 
            - OK

- is there any syntax for "merge from branch-A to branch-B" without being inside branch-B?
   - i don't think it's possible. A `checkout` of the target branch (that you're merging into) is always involved. This also makes most sense  because then you can solve possible merge conflicts in the right branch
   - From the manual (git help merge), "Incorporates changes from the named commits (since the time their histories diverged from the current branch) **into the current branch**.", so it is most likely not possible, but as pointed out above, probably not advisable either, in case conflicts arise...
   
   
- In BO there was a question about the options of `git graph` alias, in particular about the effect of the "`--graph --decorate`" options. Could you please comment on them ?
  - `--graph` adds the ASCII art at left, that shows the parent commits and merge history
  - `--decorate` adds the labels for all branch names, HEAD, tags, etc.

- are there norms for commit messages when it comes to merges? we talked yesterday about commit messages in general but I'm wondering about merges specifically.
    - a merge commit comes with a default commit message. I think it's good to keep that message because it's unambiguous, but there might be other opinions


- while merging experiment into master, I was not given the option of altering the commit message. Is it normal?
  - depends on settings. nothing to worry about and can be changed.
  - If you just want to edit the commit message (rather than the merge message) before mergeing, use `git commit --amend`
Merge made by the 'recursive' strategy did not give option to write commit message
       - was it a fast merge? in that case there is not a new commit so not commit message needed either

- (regarding the question above) how to change the settings for allowing me writing a message for the merging then, please?
    - I see that stackoverflow recomendation is to set a env variable 
        - export GIT_MERGE_AUTOEDIT=yes
    - I also see this option 
        - git config --global core.mergeoptions --no-edit
        - https://git-scm.com/docs/merge-options
        - But I did not work as expected on my Ubuntu setup, only the above export worked. Please indicate your experience here 

- I do not get the option to write a messag when merging as Diana has. How can I have this option as well?
  - see above

- If you got stuck: See https://coderefinery.github.io/git-intro/06-branches/#merging-branches to get a repo with all you need to follow along.


- Why this error has occured?
   ```
   Auto-merging ingredients.txt
   CONFLICT (content): Merge conflict in ingredients.txt
   Automatic merge failed; fix conflicts and then commit the result.
   ```

   - You made changes to ingredients.txt on both branches. This is ok and it can be merged manually (we'll get there soon)
      - I also made changes to ingredients.txt on both branches (as instructed) and didn't get any such error message. I presume this is due to different kinds of changes resolving easier than others.
        - Yes, git compares files line by line. In case you made changes in two different lines within the same file, you should avoid the confilct, otherwise not.

- I suppose we can delete several branches at once ?
    - yes, `git branch -d branch1 branch2 branch3`

- I forgot, how do we go back to a previous commit (restore)?
    - git checkout commit_checksum is a possibility; you can use git log to find the checksum of the commit you are interested in; you don't need to copy the whole checksum, the few first characters are enough for git to identify it
    - To move the current branch back one commit: `git reset HEAD~1`
    - To also reset the working directory: `git reset --hard HEAD~1` 

- Sorry if this is a duplicate question, but would it be possible to get the Terminal History for each day respectively in the Google doc? Thanks!
    - all of the used commands can be found in the lesson material https://coderefinery.github.io/git-intro/
        - great.
    - not all instructors use the logging into Googledoc
        - I see, yes I understand, thanks!


- "$ git branch --merged" What did this actually do/show? How do I interpret the output differently from "git branch"?
    - this shows only the branches that have been merged into the current branch

- Is it good and common practice to delete branches after merging them into the Master?
    - I would say this depends on your personal preference. I personally delete them and try to keep only the branches that are needed.
        - And I can always go back to the commits made in those (now deleted) branches and recover files (content of the files...) and changes, right?
            - Yes!
    - A short answer: yes 😊 (otherwise you may end up in a mess where it's hard to find the "active" branches quickly)


- Is there a way not to type `git` at the beginning of each command this much?
  - One way of doing it is to add aliases. E.g. `alias gl='git log'` 


- Advanced trouble-solving question: Similarly to https://coderefinery.github.io/git-intro/06-branches/#optional-exercise-moving-commits-to-another-branch, but commits related to featureB erroneously created in the branch for featureA which has unmerged commits for featureA first, followed by commits for featureB. FeatureB needs to be merged, without featureA. Is it possible to cherry-pick? I tried but haven't figured it out myself how to carry on (it wanted some merging). Unfortunately, this is a recurring mistake among less experienced or busy contributors. 😢
  - There is a way to cherry-pick, using the git-command `git rebase`. I usually use interactive rebase, `git rebase -i`. This will give you some instructions. First create a new featureB branch, then use rebase to 'drop' featureA commits.
      - 🙏🏽 1000000 thanks, will try
      - Always rebase in a new branch, keep the old one as a backup.
  - A simpler option (that does not do what you asked) is to checkout the last commit with featureA changes and create a new branch there. The original featureA branch is now featureB, but after featureA is merged.
      - Yes, this is a great simple resolution, in case FeatureA is "mergeable".
        - You can still work on FeatureA and merge it later to the featureA+B branch (can be from "main")

- Will we talk about squashing or fast-forwarding (or other options) commits on merging?
  - we may not have time to talk about rebase and squashing but we have some exercises and explanations here: https://coderefinery.github.io/git-branch-design/
  - we may mention squashing tomorrow on github
  - [fast-forward merge](https://coderefinery.github.io/git-intro/06-branches/#exercise-encounter-a-fast-forward-merge)
  - [squashing](https://coderefinery.github.io/git-intro/06-branches/#optional-exercise-squashing-commits)
  - [rebasing](https://coderefinery.github.io/git-intro/06-branches/#optional-exercise-rebasing)

- Can we discuss a bit more about the question above on branches on git vs github?
  - yes, we will also spend all morning tomorrow on this
      - nice :)


- Can we use `$ git merge -m "message goes here"` to  manually add in a message to the merge?
  - sure, it's really handy for short messages
  - similarly `git commit -m "awesome commit message here"` is great when the message is short
  - seems to be possible, the help page (`git help merge`) shows:
    ```
    -m <msg>
       Set the commit message to be used for the merge commit (in case one is created)
    ```


## conflict resolution
https://coderefinery.github.io/git-intro/08-conflicts/

- I can't read the lower lines of the terminal screen of the presenter, Diana. So I can't follow what she types. Can this be adjusted?
  - Good point, the Zoom interface is in the way when not in full-screen.
  - is this something the speaker needs to change?
    - that would be useful, as many are not using full-screen (to enable a separate window next to it)
  - follow up: If you know how to get rid of that bar without being in fullscreen, that would be great too... I realise  this isn't a zoom workshop but we had this problem in zoom elsewhere.
     - for what it's worth: i don't have full screen but in view option I use "standard" and I resize my window to be "portrait", taking half of my screen
         - Thanks, will try it out next meeting!
     - another option is "dual monitor" setup (does not require two monitors, I have one; it's in Zoom's video settings)
     - another option could be to press ALT/option key on keyboard which might hide the bottom bar allowing to see lower part of the screen 


- (sorry for auto-promotion) we have a 1 hour Research Software Hour video dedicated to git conflict resolution: https://researchsoftwarehour.github.io/ - it shows also all we do here and more :+1:



- Is there a good way for auto-completion? Not only for the file names but for e.g. branch names
    - Start typing the name and press tab. You are welcome.
    - but not all shells may "understand" this by default.
         - Yes, windows cmd prompt does not understand this sadly
             - https://www.maketecheasier.com/enable-auto-complete-feature-command-prompt-windows/
         - If you use the git bash terminal (on windows), autocompletition works also for branches (learnt today) :+1:
            - but it can be enabled, anybody has a good reference for how?

- Conflicts mean that you can do multiple things at once.  This is a good thing.
    - Yes. One should not be afraid of conflicts.


- Why did it not create a conflict for the first merge? Was it not also a change on the same line of text?
  - The first merge was between commits `4b3e3cc Merge branch 'less-salt'` (the master branch at the point, no change to cilantro content) and `55d1ce2 please more cilantro` (the like-cilantro branch, no change to anything but the cilantro content) so there was no conflict at that point
  - It is because Git knows the latest commit in the master branch was the same as the earlier commit of the like-cilantro branch, and treats the merge as a new commit of the same branch
  - if one commit is "ancestor" (parent, grandparent, ...) of the other commit, then there is no conflict since git assumes that there is a clear evolution and the child commit contains the other as history (hope this explanation made some sense)



## Sharing repositories online
https://coderefinery.github.io/git-intro/09-remotes/


- What was the split screen command?
   - I think maybe the instructor is using tmux to split screen, see also: https://coderefinery.github.io/manuals/instructor-tech-setup/#terminal-history-window

- What are the main differences between Github and Gitlab ? what are the advantages / drawbacks of each?
  - main difference is that you can host the community edition (which is open source) of gitlab yourself on your own servers, in-house
  - otherwise very similar in functionality

- It might be useful to have a word of caution about having git and dropbox tracking the same directories. (I am asking it in this section because dropbox is a commonly used online syncing/collaboration platform.)
    - What would happen in that case?
      - Git creates a lot of small files and Dropbox is slow when tracking large numbers of files
      - Also Dropbox will track the working directory, not just commits. So if two people work on the same project, they will create Dropbox-conflicts when editing the files.


- open-core vs closed-source... what is the difference?
  - open core: this means not all code is open source but part of it is open (the gitlab community edition part) and part of it is closed (proprietary features that can be bought)
  - closed source: everything is closed 
 
- Is there a plan to take a look into the actions part?
  - yes, next week we will have a 2 hour session on that (testing lesson)

> in case you have not set up the ssh keys yet, see the instructions here: https://coderefinery.github.io/installation/ssh/

- If I'm not wrong, there should be no issue tracking remote branch 'main' using local branch 'master'. Name is only changed for ease of use.
  - yes this is possible but we avoided this to minimize confusion. the local and remote branches do not have to have the same names.

- Error: git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
  - The ssh key is not set up. Try https://coderefinery.github.io/installation/ssh/.
  - You can also try the https-version ("https://github.com/..."). But you should set up the keys for tomorrow.

- (Similar to above): "The authenticity of host 'github.com (140.82.121.3)' can't be established. RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8."
  - Does it ask you to add the fingerprint? If so, type "yes".
    - Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

- What is exaclty 'origin'? The name of the "online" git repository? 
   - "origin" is a shortcut for a URL. we can rename it and we can also let it point to other places and add more remotes and tomorrow we will see how and why. in this case, "origin" refers to the repository on github

- Maybe it would have been beneficial to have a short break rooms time to be sure all of us were ready to push.
  - good point, but it is no::t critical that this works for the following. but thanks for the good point.


- I did not see were he found the url ON github
    - informed instructor

- What does '-M' mean in the "git branch -M main"; does it mean renaming the master?
    - `-m` stands for "move". 
    - Just as in the shell you rename a file with `mv old_name new_name`, in git you use "moving" to rename a branch.
        - Thanks!


- Can we also clone using SSH link. Does that make any difference?
  - The end result is the same, but if you have set up the ssh key, then using ssh is preferred: it's way more secure (and you don't have to type passwords etc every time)


- Is it possible to delete the default branch in GitHub? For some reason I now have both a Master (default) and a main branch, even if I renamed the origin to main.
  - first change default branch to "main"
  - then delete "master", you always want (and need) at least some default branch on github


- Unrelated remark: providing the hackmd link on the intro page would be helpful to find it if one has accidently closed the page
  - thanks
  - Since anyone can edit, we tried to keep it a bit private.  But it's public on twitch so maybe it doesn't matter and should be there...

- What if one clones a repository that has the same name as a local directory. I mean if one does it accidentally, what happens? will everything get overwritten as per the remote repository?
  - it will refuse to get cloned and tell you that there is already a folder with the same name and then you need to do `git clone someaddress someotherfolder` to create `someotherfolder`
--------

- How do github and gitlab free plans compare?
  - When I last checked, Github had more restrictions on private repositories (need to pay for continuous integration)
  - But public repositories on Github are more findable and there are more tools.


- Break-out room 24: There is an issue with screen sharing - only parts of the screen share works.
  - The "Screen share" options are very limited for this user, and there is no way to choose what to share.
  - somebody going there ...

- What is the significance of the flag -u while pushing the repository? I don't understand the description in the manual.
  - Each branch remembers "this is where I pull and push from".  It sets this config for the branch.
  - the -u stands for upstream. you can type git push -h to see an overview of all flags!


- what was the split screen command at the beginning of your session?
  - tmux, more details here: https://coderefinery.github.io/manuals/instructor-tech-setup/#terminal-history-window


 - Is it possible to edit commit messages after making the commit?
   - To edit the latest commit, you can use `git commit --amend`
   - This is shortly mentioned in [lesson 5](https://coderefinery.github.io/git-intro/05-undoing/) (though there the advertised use is for adding more files/edits, but it allows editing the message too)

- I have nothing against my face showing up elsewere, perhaps with a privacy statement this video on/off issue would be quick to solve
  - We do have one, but at least I'm not comfortable with having a warning as the only safeguard.
    - I meant a declaration that if you video is on, then it is understood as you do not mind appering in the video.
    - I'm still not quite confortable with only that.  privacy and avoiding the risk is too important
  - Would it work if people state in their name whether they consent (with a star or so?) 



## Inspecting history
https://coderefinery.github.io/git-intro/10-archaeology/


- How to step out of the repository at terminal? I am not in the recipe or cloned recipe-2021 folder, but still it shows I am on branch master
  - try `git status` to see whether you are in a repo (likely a repo got created somewhere above the current directory)
  - `git rev-parse --show-toplevel` shows where the repo is (it took way too long to find this...)
  - `cd ..` to change directory one level up
  - if it still shows `master` also above, perhaps you accidentally made your whole HOME into a git repo by `git init`. If that is the case, a brutal delete of the `.git` folder might solve it.
    - safer: rename `.git` to `dot-git-backup` (then you can always rename back) 👍🏽
    - I want to remove .git, it shows rm: remove write-protected regular file, how to deal with it?
       - try `mv .git dot-git-backup` does this work?
       - yes, thanks
         - after this, if you want to get rid of the latter: `rm -r dot-git-backup`
             - still can't delete the folder, shows: "rm: remove write-protected regular file" 
         

- something that is not fuuly clear tome: does git grep searches both the current and past content and any branch known locally?
  - only current state ("HEAD") on current branch but all tracked files
  - but it is also possible to search through changes (`git log -S` as demonstrated)
    - ok, thanks the instructor just said it

- Is "git annotate" an alias for "git blame"?
  - in my understanding they do the same and can be used interchangeably. please correct me if somebody knows better.

- is there a git command similar to 'svn info'? That is, to give a simpler pointer to the current location, simpler than the git log.
  - git show

- If we don't want to create and then delete a branch for examining past code, could we just use "git checkout <branchash>", which results in a detached head state or somesuch?
  - It's okay as long as you are not going to make any changes
     - because otherwise moving away from the new changes (commits) could make it difficult to find them if you don't have a branch pointing to them

- Earlier we used git branch experiment master to create a new branch. Can we also use git branch older-code <hash> to create the branch 'older-code' with a previous version?
  - yes!

- Not currently on any branch after clone. Is that normal?
    - You need to `cd <dir>` to be in the cloned repo on your local machine
    - What does the command `git branch` print ?
       - it's after the clone and before checking out the exercise branch in the exercise.
       - git status
       - Not currently on any branch.
       - nothing to commit, working tree clean

- What is `checkout -b`? is it the same as first create a branch and then switch to it? 
    - `git checkout -b <newbranch> <olderbranch>` creates a branch and switches to it
    - it is the same as the combined `git branch <newbranch> <olderbranch>` ; `git checkout <newbranch>`
    - note that the <olderbranch> argument is optional, default is the branch you are on


- could you explain the "detached HEAD" thing? Maybe later in the main room or
  - "I've checked out something that isn't a branch" (`git checkout <hash>`)
  - it means "HEAD" points directly to a commit hash but not to a branch ("HEAD" is detached from any branch). you can still make commits but if you move away from them, you will have difficulties finding them if no branch points to them.
  - if you do create new commits and "lost" them, you can still find them again using `git reflog` which keeps track of all hashes ever visited
  - if you see it, you can ask "will I want to make changes?" if no, don't worry. if yes, create a new branch and continue then
 
 - Are the commands `git switch --create <newbranch> <hash>` and `git checkout -b <newbranch> <hash>` equivalent?
   - yes, the latter is the traditional way, the former is available in newer git (and was introduced to have a more intuitive user interface)
  
- At the bisect exercise I did `git log --oneline` and pressed F to go towards the end of all commits. Now it says `Waiting for data.. (interrupt to abort)`
  - you can CTRL+C and also try: `git log --oneline --reverse` 
    - Thanks

- How do you return one commit back? Would something like git reset HASH~1 work? 
   - `git checkout HASH~1` (will not create new branch, so goes to "detached HEAD" state)
       - Thanks! Would this be the same as git reset --hard?
       - The `--hard` option means that all changes in the working directory will be lost. If you want to keep the file changes you should use the `--soft` option.
   - `git reset HASH~1` will return one commit back. Use with `--soft` (default) if you want to keep the changes in the local directory or with the `--hard` option to remove the changes from the local directory (all untracked and uncommited changes lost).


- What about the opposite? Is there a shortcut option to get the "children" (_i.e._ newer) commit(s) of the HEAD?
  - this is more difficult. in git, commits do not know children of commits, only parents. hence we always want a branch to point to a commit so that we can find them.
      - Related: There was some trick to list all commits, including ones not belonging to branches. (RB was mentioning it in one of the previous CR workshops. Sorry, I can't duckduckgo it😢)
          - `git reflog` can find orphaned commits
        
- Did the whole Zoom meeting just end or is it just me?
  - no, maybe your zoom client crashed (happens to me sometimes when moving back from exercise room)
  - Weird I just completely lost the meeting. Will try to get back in.
  - Unfortunately, this happens from time to time. Sometimes it can help to update your zoom version.

- Point 5 in the excercise needs to be explained: if this is not known already, there is no time to find this out in the BR.
  - thanks, we need to add more context there

- We couldn't get this part (2) of the exercise       "If this line got removed after we have created this exercise, find out when it was removed." Can you explain?
  - The exercise was to look for a file in the source code. In this case, the line exists in the latest version of the code. Imagine that we instead are looking for a line of code which no longer exists (has been removed in a previous commit). This is where `git grep` (searches through files in current working-tree - it will not find lines no longer existing) differs from `git log -S` (searches through history - will find lines that no longer exists). Hopefully this clarifies.

- I feel like the bisect command is not really explained within the document, what does it do exactly?- 
    - Lets say something goes wrong in the code at somepoint. You need to find out where that happend. Instead of manually checking out commits one by one this is systamatic way to do this. instead of manually checking out commits, we tell git a commit that was working and git will help you to locate the commit that broke

- Once I am pointing at the commit where the old file version was, how can I restore into the main branch the file as it was in that version?
  - `git checkout main`, then `git checkout somefile theworkinghash`, then `git status`
    - Should this be `git checkout theworkinghash -- somefile` ? (`--` is optional and just for clarity)


- A basic question, do the files update when we switch between the branches? i meant the files in my workstation.
    - yes, the files automatically get updated. If you have a tracked file open in some editor, the editor might complain "file changed on disk..."



- But why would I want to locate a bad commit? There is a bug that needs to be fixed. Debug -> create new commit and push. 
   - Seeing the change might help you debug the code
   - you may not know where the bug is
       - Ok so bisect has mainly debugging advantages, right?
         - It's basically a debugging tool



- are the good/bad flags from bisect stored somewhere (i.e., tag)?
  - Git will store them somewhere (but I don't know where)
  - but they're not usual tags (which would point to a given commit permanently)
  - you mean like if you want to retrace the "path" that git bisect took after you are done?

- Room 24: Screen sharing issues.
  - Issue seems specific to X/Wayland, occuring in multiple Zoom versions. Did not help to switch to browser version.
    - I have heard about screen sharing issues with Wayland but am not using it myself to give a more competent answer.
    - Possible "solution": switch to X.


## Feedback

One thing that was particularly good today:
- ...
- last exercise, and some new functions I had never seen before: cool!

- I finally understand how to make branches in the terminal (not just on github) and use git graph. Really good explanation!

- the balance between explanations and exercises in groups with group leaders is rreally good! (general for all sessions)
- Time management and HackMD activity.





One thing we should improve for next time:
- `git grep` output is pretty confusing: perhaps an example in the material would be good ("this first thing here on each line of the output is the file name, then comes the actual matching line in the file...")
- it happened that pushing using ssh failed due to not inputting the passphrase. The first time we push it asks for a passphrase and the learner not providing it caused stuff to not get pushed. It might be helpful to write it out in the material that if you are prompted for a passphrase 1) it's the passphrase you set when creating the key 2) you need to provide it
- Bisect actual example would be great +2
- Remove hints to dependencies that are not needed in the excercise (e.g., rebase)
- I got confused with the useage of new commands and old commands like git branch and git checkout -b. I think the instruction websites should maybe get updated, especially 'Inspecting history'
  - good point. we were a bit conservative  
- As an exercise leader, I had some confusion during the last exercise. I could not answer some questions about [git log -S] (my bad) and there was some confusion since one could use [git checkout -b] and [git switch --create] to do basically the same thing. Maybe it will be useful to have a link pointing to the description of some command line arguments (for those interested) that have been used throughout the day, like for the ones in the git graph alias.
  - yes sorry, introducing two different versions of commands perhaps didn't help, see also above 
- An exercise on merge conflicts right after the relevant session would be great. +1
- I got stuck in the last exercise because the instruction to complete the second bullet poin (Find out when this line was last modified) is (very) hidden in the last sentence of the instructions above (before the discussion box). Since that is a key info, it woul help to bring it up. Moreover, it was not clear to me that the instruction and the exercise were not following the same sequence (e.g. point 2 of the exercise uses point 4 of the instructions). That is fine, it should just be clearer.



