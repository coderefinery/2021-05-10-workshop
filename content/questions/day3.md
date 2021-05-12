+++
template = "page-with-toc.html"
+++

# Questions and notes from workshop day 3

## Icebreaker

Are you collaborating with others on a version-controlled project? What's the size of your team? And what do you see as the biggest challenge in collaborating?
- Yes, two to three persons.
- Yes, six people. When we forget to merge the codes, then, we all are working on codes that are not up to date.
  - Yes, that is what easily happens. One good habit is to strive to merge back code from development branches to the main branch continuously, and not only when the new feature has been completely developed. Automated testing is helpful in this context as it lower the barrier for continuous integration of code.
- we are starting to use git and collaborate more but in collaborated work, the biggest challenge is to determine who is the main person who is responsible for the codes
  - typical situation. it's often 1-2 people who overlook things but good to share the code review among everybody.
- Nope, have used Github to share code within our team but without actually collaborating properly (e.g. branching and then merging)
  - I see this happening a lot too!
- Yes, two collaborators. Since I am beginner I have issues with merge and rebase.  I would like to know which is better in what circumstances. Some examples would be great.
  - rebase creates more linear history but it moves/changes commit hashes. this is fine for local branches or for side-branches but once the commits are in the default branch, we often are not changing them anymore.
  - merges and merge requests create merge commits. which I don't see as a problem but as a good thing. But some projects may prefer if contributions are "moved to the end" before integrating them.
  - I use rebase when I want to clean up and combine commits. So I first move them all "back", then you can "squash" them into one or few commits.
  - I consider "rebase" a more advanced feature, though.
- not yet but plan to. Challenge is to follow same "flow" is agree on when to commit, how much to comment etc
  - I recommend to make the default branch read-only and only make changes on new branches. Better too many commits than too few. They can always be combined later. The barrier to create a commit should be low.
- Working on the BIG community models for climat modelling = < 200 participants and a central software engineer team to organize. Biggest challenge: communicate the "rules" for contribution and standards for the code development. 
  - Very interesting. I would be interested to learn from you how you manage that.
- Yes, in a small groups, 2 or 3 collaborators.
   - Nice!
- yes, 2-4 collaborators
   - Nice!
- Not yet but will be working with a group of 3 or 4. I see the main challenge being when to agree on commits and how best to comment so everyone understands the code in the same way
  - Code review might help with that. Then at least 2 people see a change instead of only 1. Not for gate-keeping but more for collaborative learning.
- Yes, 2 collaborators now, 4-5 in total in the last years; we develop a radiative transfer code, that allows to make synthetic observations of the Sun out of numerical simulations of its atmosphere
  - Interesting project! 
- Have been using Git repositories & zenodo for documenting reseach code for publications, and done some collaborative work on Git (2-3 collaborators), but very little with "proper" branching,merging etc. Would like to have a more structured approach and make this a more established practice in the group (sharing repos, collaborative remote work, code review, and then archiving the repo for publication)
  - I recomment to write-protect the main/master branch. Not for gate-keeping but for bringing everybody on the same level and to increase group learning by sharing code review. But of course code review may slow things down a bit and there may be resistance to that.
- Up to 10 developers. The most challenging is to avoid merge conflicts - we do that by carefully planning tasks for each developer.
  - Do you coordinate via issues? Or via chat?
- trying to bring old coder to common use. Difficulties with cleaning and old os and dependencies.
  - Branches can be used to keep track of existing older code, newer code, and 
- Worked on my own project with another collaborator. I also did small contributions to existing open source projects with many contributors.
  - Nice! 
- I do not do it myself, but I manage projects where the team uses version control and works more or less collaboratively. I am also part of a large community of practice around an open source energy modelling tool where all contribute through GitHub.
  - Nice! 
- I do all the time on numerous projects; typically 2-5 persons. The biggest challenge is on-boarding new collaborators with no prior version control experience.
  - How do you solve it?
- Not yet, but it looks so cool that I want to start right now!
  - Excellent!
- Yes, maybe ten people or so. I haven't contributed a huge amount yet and contributions have been separate enough that merging conflicts haven't really happened yet, so no major issues so far. Biggest problem on my part is probably me being bad at committing changes often enough.
  - To find the right pace for making commits comes with practice. In general, it is better to commit more often than to seldom.
- Yes, 2-4 collaborators
  - Nice!
- Is there best practice for testing out whether changes on multiple branches actually "work" together? I.e. there may not be lines of code that conflict but the changes may be incompatible with each other. Should you create a new "test" branch and merge the new features together and test the software before incorporating with the master branch?
  - (we forgot to answer this one yesterday)
  - yes, if I wanted to test whether branch A and B work well together before merging back to main, I would create a test branch or integration branch where I only merge A and B into it, but I do no other "work" on it. In other words all commits go to A or B and the integration branch only merges them. This can be better than merging A into B or B into A because after that it may be difficult to untangle A and B if only one of the two is ready to be merged to main/master/production branch.
      - 👍🏽


## Questions day 3
- Sorry just a question ... it is only on my side that the sound is not as good today as it was the 2 previous days ?? 
  - Sound seems to work. Please check if Zoom has set the volume low on your computer (happens on Linux systems some times)  
  - I can hear you typing more than I can hear Juho talking more or less...
  - Yes, there is a lot of background noise. Would be nice if everyone except the speaker was muted.
    - better now?
    - Not really ... well no sound anymore now ...
       - I am assuming this is Zoom? or Twitch? which operating system?
    - I'm on twitch ... ubuntu 20.04  
        - ok checking ....
        - working on it ... sorry for troubles
           thanks
           THE SOUND IS WITHOUT ANY NOISE !! THANKS! 
             - thanks again for patience :-) many toggles to toggle and many places where things can go wrong
        - The problem: the desktop audio device was actually capturing from the microphone, despite clearly being set to the sound card.  I switched it to something else, then back, that made it select the right thing.  How is this possible?
- We did not really do "pushing" yesterday afaik.
   - it was only very briefly demonstrated (when we pushed the recipe repository to github but it was only shown)
- I have a question regarding importing history. When is this useful and which actions allow to do that and which do not? (forking, cloning, creating from template, etc.) Thanks
  - can you please clarify: what do you mean by "importing history", in which sitaution or from where to where?
  - but I can already say that creating from template is not useful for importing history since it flattens history. templates are useful to create new repositories with a certain starting structure
  - forking: you copy everything and it stays in the cloud, good backup
  - cloning: you copy everything, typically to the computer
  - one can also "import" a repository into github or into gitlab from some other place which copies everything but does not create a "fork" relation.


## Collaborative Git
https://coderefinery.github.io/git-collaborative/01-remotes/

- where can we find the page shown now?
https://coderefinery.github.io/git-collaborative/01-remotes/

- is the template a template of the repository or a template or one/more files?
  - It is a template of the repository

- Does a template copy contain all the branches as well?
    - when using the template you can decide whether to include all branches or not
    - but generating from a template "flattens" the history so you end up with one commit only (on each branch). so this is good for "cookiecutter" templates where you want to generate new projects that start with a certain structure. but it is different from a "fork" where you copy the full history also.

- What exactly is "the remote"?
  - "remote" is also a Git repository, with commits and branches. typically it is on a cloud service but it could also be on a different folder on the same computer. we use "remote" repositories to synchronize work among multiple collaborators or among multiple computers.
- I have a very general question about GitHub - it is all free, there are no ads or anything, but for it being a commercial service, when it starts to cost?
   - Good question. The free of charge offers all of the main functionality. Here is https://github.com/pricing
   - for public repositories, you will not experience limitations (apart from automatic testing CPU minutes, more about this next week). For private repositories there may be a limit on the size of team but there is no limit on the number of repositories
   - also good to remember that Microsoft owns it and the commercial interest for them to have a very generous offering on GitHub is to get people and companies excited about Azure compute cloud

- If I delete a repository that I forked, does it affect in any way the original one? I.e. I forked a repository a long time ago, but I forked a fork. I would like to delete this and fork the original.
   - It does not affect the original repository. Each of the repositories exist on their own. 

- Can you elaborate a bit on "history". When is it important/useful to "import" (?) the history (of commits, I guess) in your repo, on top of the repo files I mean, and which commands allow to do that (fork, clone, create from template, etc.)? Thanks

- Importing all history is normally what you would do. Importing a template (which flattens history, results in new repo with only one commit) is only for special circumstances when you want to start new repositories from pre-defined structure
    - Forking gives you an exact copy including all history, branches etc

- Sorry for this but the difference between a fork and a clone is still unclear to me.
    - A fork is a replica or copy of a repo on the remote cloud- so hosted on github/gitlab wherever.
    - A clone is a replica of a repo on your local machine, not hosted remotely. So like your personal copy that is downloaded only once
    - One example when you would want to create a fork instead of directly cloning is when you plan to make modifications/contributions, and then send a pull request, to a public repository hosted by someone else (especially if you don't have write permissions here).
    - See question+answer below on pro/cons of forking vs cloning.

- There is still background noise. Like traffic humming and human voices in the background? Now the sound is better :-)
  - sorry again for troubles. this is Twitch and we had/have some problem with picking up wrong audio channel. please let us know if it got better of if it remains bad.
  - we found the problem (hopefully) and hopefully it's better

- What are pro/cons of forking vs cloning?
  - fork can have more of a "backup" function, since it stays in the cloud
      - wouldn't a branch do the same?
        - yes, if you have write permissions, a branch would be enough but if you don't ... (see next answer) 
  - if you don't have write permissions to the repository, then you cannot push to the "central" repo but you can push to the fork so then the fork can be the only way to contribute changes back (or not to contribute but to at least have them somewhere visible)


## Centralized workflow
https://coderefinery.github.io/git-collaborative/02-centralized/

- what GitHub roles give the write access?
    - you can invite members and set priviledges (read-only, read+write, administrator) by going to the settings of a repository, e.g. https://github.com/username/repository-name/settings/access
    
- Are exercise leaders expected to add collaborators to the centralized repo or not? It is not clear. Exercise in this link (https://coderefinery.github.io/git-collaborative/02-centralized/) says that we should, while originally posted in Zoom chat (https://coderefinery.github.io/git-collaborative/03-distributed/#exercise-preparation) does not.
    - Yes, you should share the GitHub usernames while you're doing the exercises in the breakout room.
        - Thank you! Maybe it should be mentioned that the template and the exercise in the originally posted link in the chat does not correspond to what we are supposed to do as the first exercise. 
 
- I also have an email filter for GitHub notifications. So useful!
  - oh yes :-)
 
- suggestion for the excercise instructions: use a URL "variable" (e.g., &lt;URL&gt;) to discourage copy paste of the coderefinery URL
  - thanks, creating issue: https://github.com/coderefinery/git-collaborative/issues/171

- Question regarding exercise: the text reads;
     ```
     In this case we do not add collaborators to the repository
     (this is the point of this example). Share the link to the
     newly created repository in the shared document with your
     group. Should we do as instructor says or follow the text?
     No, in that case we are not using a template, the instructor started by template
    ```
  - I think you are looking at the second exercise, not at the first (earlier on Zoom we acccidentally shared link to the second exercise; sorry)
  - In other words, in this exercise we add collaborators because they need direct git push access (in a later exercise we will try collaborating without adding write access)

- Please, have the instructor specify if we should use a template or create a new repo in the first exercise
  - One person from the group creates ("generates") a repository from the template. everybody else will provide their username so they can be added as collaborator to this one repository and everybody else will clone.
  - The link to the template is give in the exercise description: [Centralized exercise: preparation](https://https://coderefinery.github.io/git-collaborative/02-centralized/#exercise-preparation) and it is [template-centralized workflow-exercise](https://https://github.com/coderefinery/template-centralized-workflow-exercise)

- When cloning, do I clone all branches?
  - yes, they are all there but you may need `git branch --remote` or `git branch -r` to see them. But you copy everything, also all tags, all history.

- Not sure about the power of forking: if I fork, I have a snapshot of the original repository at a certain time; after that, can I pull changes from the original repository to keep the fork updated?
    - Exactly, one normally updates the fork to keep synchronized with the "upstream" repository
    - Since recently this had to be done via terminal (or probably some GUI), but now one can also do it on github.com
    - A fork also allows you to send pull requests to a repository where you normally don't have write permissions (e.g. think a very popular public repository)

- Could you explain in a bit more details what is the difference between head and master branches? 
  -  The head is a pointer to one commit in the repository. This commit can be in any one of the branches

- Could we revisit the picture the instructor was drawing and reinforce the differences between master, origin/master, HEAD and how these move when the remote is updated (say by a collaborator) and when my local repo is updated by myself? How everything sync then?
  - Let's see how timing goes but we also have all steps here which hopefully show how the repositories progress as we make changes with local and remote branches: https://coderefinery.github.io/git-collaborative/02-centralized/

- May I ask what is the difference between `origin/master`, `master` and `head`? Is the last one a pointer and the first two branches? 
- Can you explian a bit more about -u parameter in push command? 

:::info
## Break until xx:05

- "Take a break, don't work!" is a good sentence :)
    - as a PhD student I sometimes dropped by my colleagues' offices and told them to "stop their research" :-)
       - haha. nice.

:::

- Will the EL be able to do the exercise themselves?
  - I think so

- Could you please open breakout rooms? In an online workshop, the only way to meet is through breakout rooms... it is possible to be in these rooms without working! Thanks.
    - Sure! Please socialize in your BO rooms but do not forget to take a break from the lesson!
    - Thanks for the feedback. We had a bit of hiccup with too few rooms but for next breaks we will remember this.

- Could you please address this before the BO start: "If the helper in the room is the one who sets up the central repository, he/she cannot easily demostrate the steps via screen-sharing as the repository’s owner."
  - I think what he meant is that: the owner of the cloned repo cannot easily screen share all the steps that the others will take (as that would require the owner being able to invite themselves)? Thanks for asking. I think we should not worry too much about this comment.

- If I develop a project just by myself, and I have a public Git repository in GitHub and want to add new features. I do not want the new features to be public. Should I use the public repo as a template with preserved history, set it private and add the new features there (new research, would not want to have it publicly available anywhere but still backed up somewhere). When I want the features to be public, how to marge the private branch with the public branch?
   - There are ways to do that, e.g. https://stackoverflow.com/questions/8834755/github-pull-request-from-private-to-public-repo-possible shows some. But it's a bit of a hassle
   - I would suggest considering if the features under development could be in the public repository: people aren't likely to try to use code from a branch other than main/master, especially if you have [tagged](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/managing-tags) or [released](https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository) (similar features are also available on other platforms, e.g. gitlab) versions that are "official" and meant for public use
       - Another reason for having the development branch public is that others have a chance to review the development and potentially find bugs/suggest improvements.
       - If your motivation for having a private branch is hiding incomplete or "ugly" work, just merging a private branch won't necessarily even solve that: unless you do some history-altering, depending on what kind of a process you use to merge the private branch, the intermediate commits will be public any way
          - Which is a great thing, as it e.g. acts as an evidence that you were the original author!

- Just curious: could it be that the lags/bugs of HackMD are somehow connected to the browser/OS ? 
   - Good point. There might be a difference in how often the different browsers update. You can always force a refresh of the HackMD page with the browser reload button.
       - Maybe it would be interesting to run a short survey after the workshop to see what browsers/OS people used when they encountered issues. For the future :-) 
   - Good suggestion
   - I also think there is a difference whether you are logged in or not. I am logged in and see no lag. But of course I don't want to require everybody to be logged in.

- Question for the centralized exercise. The exercise leader is also supposed to clone, branch, etc the template repository on the local computer, right? Thanks
  - Not the template repository but the newly created repository
      - yes I meant that. Thanks
  - But the EL can also watch others do their work and help them. our goal is to have few contributions. we don't need everybody to have a contribution. also ok to use screensharing.
  - Long story short, as EL i would perhaps not clone and create branch but rather help somebody else who screenshares their work. but there is flexibility. you can also do that and demonstrate via screenshare.

- As an EL can i not clone my own repo from GH?
  - You can

- When doing a git pull we get to see all branches with git graph, but I don't have the branches locally. How can I pull all branches locally?
  - Try `git branch --remote` or `git branch --all`
  - More background: after you clone, you clone all branches, but git renames them to `origin/somebranch` where `origin` refers to the place you cloned from. if you want to work on them locally, you need to switch to them: `git checkout somebranch` which will create a local branch from the remote branch and switch to it.

- From GitHub user's page, where do we find the link to the reposity cloned in the excercise?
    - Also clicking on the GitHub logo (the Optocat) in the black bar will show the list of repositories and activity
    - Solved

- Question about push vs pull request: by pushing my changes, it doesn't automatically create a pull request. Why?
  - right, by pushing, it either creates a branch or updates a branch and opening a "pull request" is an extra step. motivation is that you may be working on the branch for few weeks and add a number of commits and only at the end you want to signal that "this work is ready for review" 
  - note that you can also append changes to a "pull request" by pushing new commits to the same branch. with this it hopefully makes some sense that not every push opens a pull request
  - "pull request" is a bit unfortunate/confusing naming (for historical reasons). maybe better name: "merge request" (this is the naming on gitlab)

- after the push command my git got stuck... cannot go back to typing in it
    - Try with `control-c`. 
-it worked but how do I know if the push worked?
    - You can execute the push command once more. If it has already completed, git will tell you that there is nothing to be done.
-how long should it take? it s suspiciously long time... Maybe I am doing something wrong: do we need to push the branch name or the file we created?
     - No, it is enough to specify where you are pushing. The default is that you push from the url from which you cloned.

- Can one change the name "origin" to something else after cloning? (I know that it is possible to do `git remote add [alias] [url]` but not know how to change after it is named as "origin")
  - yes
      - Good, how?
         - sorry, was slow looking it up: `git remote rename origin somethingelse`
             - Excellent! Thanks :)

- When you do `git remote -v`, then you will see 2 lines about, for example, origin; one is for "fetch", the other is for "push". They show the same url (or .git), but can it happen that they are different? What is the importance of these two?
  - They point to the same URL almost always unless you change it
  - Nut you can change it if you want them to point to different places
      - Can you give an example of how to change, e.g. fetch? +1 (and what is the motivation to change?)


  - this can be useful when working with forks (as we will try later)

- suggestion for excercise instructions: use two orage boxes. One up and ingluding step8, call it first excercise, and the second for the rest, call it excercise two.
  - thanks! https://github.com/coderefinery/git-collaborative/issues/172

- after merging we tried deleting branches. One of them couldn't be deleted: `git branch -d branchname` produces `error: Cannot delete branch branchname checked out at filelocation` however another branch was successfully deleted. Any idea why?
    - Had the branch that could not be deleted been merged?
        - Yes
    - But you were able to delete them on GitHub, right?
        - We were about to try when the breakout closed!
        - If the branch is deleted on the remote repo and you fetch/pull all, will it disappear from your local repo?

- I followed the wrong instructions and that's what happened: 1) I cloned; 2) I created a file on the master and someone did the same on their local; 2) I pushed back to the master after the other person and got a conflict; 3) then I pulled the origin and pushed again - so I pushed to the master; 4) After that, I got back on my steps, created a branch and associated it to the previous commit; 5) I pushed the branch back to the origin but it pointed again to the master! I.e. it did something different than it did for all the others who pushed a branch in my group. How can I create and push a branch and get the same as the others?
    - When you pulled in step 3, you will have automatically merged the changes pushed to master with your local copy in a commit. Then, creating a new branch after this merge commit means that the branch points to this merge. Pushing the branch means that the branch will be visible on the remote, but as the commit has already been merged, it just points to the merged commit.
        - Ok got it. And if now I wanted to push a branch that points forward where all the others do, is it sufficient to do again push origin -u nameofbranch? (after all the others pushed...)
            - No. Unless you add commits to that branch, it will continue to point to the same merge commit.
                - ok perfect. Understood.
                    - Instead, start again:
                - I made another change on the branch instead. Then I pushed. But now the branch is there pending.. I suppose it'd need to be merged into the Master?
                - 
- If we didn't use `-u` to track the new branches upstream (so basically stayed on master while creating the new branches), how to change it so we are properly tracking our pushed branches?
  - without the `-u` the branch still gets pushed but as you say it does not track the remote. you can fix it by pushing the same branch later, that time with the `-u`.
  - additional info: I use the `-u` if I also want to later pull. But it is not required for the push.
  - We can also explicitly do it with `git branch --set-upstream-to origin/[branch name]`, right?

- Wouldn't git push from a local branch create that branch on remote anyway?
  - Yes exactly. I often don't bother about the `-u` if I want to share some finished branch. It can only be useful if I want to continue working on it later. But it still works.

- From zoom chat: significance of `-u` flag?
   - See answer above
   - Thanks!

- The only option for sending a pull request is via web UI? is it possible to send a pull request from the terminal in our local computer?
    - Good question. Hang on a bit
    - one option is this: https://cli.github.com/
    - another one: https://github.com/NordicHPC/git-pr (written by one of the organizers here)
        - 🙏🏼

- In the instruction "$ git push origin -u yourname-somefeature" is yourname-somefeature a file or the branch name?
   - the branch name. it's always "git push whereto whichbranch"

- can anyone of the group members do the merge?
   - in this case yes, since all have write permissions and since the main/master branch is unprotected
   - Another setup, common in larger projects, is that only some members of a repository have write permission to main.

- The push does not work. it get stuck... It just hungs on for ever
  - hmm... if you have time we can have a look via screenshare after the official part or during an exercise or break (but I also don't want to take away break time)


## Collaborative distributed version control
https://coderefinery.github.io/git-collaborative/03-distributed/
- Is there any automatic workflow to link pull request with the issue, so if the pull request is accepted the issue will update automatically?
  - absolutely and we will see that later
  - https://docs.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue
  - it's a good practice to do since it relates both and gives issues a well defined lifetime
https://hackmd.io/qIlUPDTbSVCCstUto10kTw?edit
- How do you reject changes? I have received a pull request that I don't want to merge. I have reviewed and asked for changes. What happens now? What if I wanted to just "reject" the request?
    - This could be a sensitive matter on open repositories. When people contribute work, they might get dissapointed if their contributions are rejected for some reason.
    - Technically: "close". but socially: complicated
    - To prevent this awkward situation it's good to agree to first open an issue where the idea is discussed before the person spends half a year implementing something that may not fit. but it's complicated, not everybody might follow this and it is difficult to reject good intentions. but you can always then recommend to fork a project if it goes completely against your design/goals.

- Are we learning about the 3 alternatives for merge? (squash, rebase etc.?)
  - Squash will be mentioned
  - For rebase we don't have enough time but we have hopefully useful material and exercises: https://coderefinery.github.io/git-branch-design/
      - Excellent :) Thanks!

- I noticed that if I make a commit to a branch after I make a pull request, both the commits get included to the pull request. Is it possible have them exist as seperate requests that need to be reviewed?
  - You would need to create a separate branch for the other request.

- I think it would have been much better to finish the centralized workflow exercise in the BR. That way learners would have touched with their own hands the pull requests, revision, and closure.
  - Thanks for suggestion. good for next time to improve this.

- Why does it say "(once)" next to the green dotted line in the graph? If the central repo is updated while I work on my fork won't I need to pull those changes in to my fork?
   - You would usually pull the changes to your local copy (blue). Then push from local to fork.
     1. pull from central
     2. make changes
     3. push to fork
     4. make pull request
  - Thanks

- Comment: about not "completely trusting collaborators": forking workflow is good and maybe the only way for collaborators we don't know yet. So it's for me less about trust but more about enabling derivative work for people who may find my repo and find it useful.
    - Good observations. We will discuss matters of this type also in next week.

- in the figure forking layout: why are there arrows from "central repo" to "local clone on a computer"?
  - because from time to time we may want to update the fork and there we pull from central and push to fork.
  - but since last week this got easier on GitHub which added a button to update your fork. but before last week it had to be done via local computer.
      - Wow finally 🥇🐙😸
        - I was also waiting for this button for years :-) (I even wrote GitHub about it few times) 
  - ok thank you!
  - To save effort, I usually fetch|pull only from central (upstream), and use my fork only as a placeholder for pushing, never updating it. This should be an ok workflow, shouldn't it? Or can it cause a trouble?
    - This is the standard way, I think.
    - You don't usually need to keep the fork up to date. You only need to when the fork is intended for others to use.

- when we make the new repo from template, should we again choose to not include all branches?
    - confirming that it does not matter. for this exercise we will not need more than one branch to start with. participants will then again create new branches from the one default branch.
    - and now I also see there is only one branch :-)


- for this next exercise, would the exercise leader just follow along with one of the learners? or I guess we can fork our own repos too.
  - in this case it will be difficult to fork for the person who created the repository (unsure, maybe it can be done in the same namespace). so here I recommend that the EL helps others but does not fork
  - At least one problem like this was caused by the window requesting the ssh key passphrase was hidden under other windows (i.e. solved by just locating the small dialogue window and providing the passphrase)


## Exercise
https://coderefinery.github.io/git-collaborative/03-distributed/#exercise-practice-collaborative-forking-workflow
[exercise preparation](https://https://coderefinery.github.io/git-collaborative/03-distributed/#exercise-preparation)

Steps A-E to be done in the BO room. Step F aon onwards in the main room.
Please keep us updated on the status in the HackMD.

- As en EL can I fork my own repo? 
   - Yes, it is technically possible to for you to fork your own repository.
        - are we supposed to do it now?
        - I am actually unsure whether you can fork in the same namespace and it is not required for this exercise. I would let all learners fork and rather help them out with that but not fork as EL.
    

- are the issues closed automatically by writing "closes #X" in the title of the pull request? 
  - yes. see also https://docs.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue
  - it understands "closes", "close", "fixes", "fix" and the issue number
  - they get auto-closed after merge
  - this is good practice to cross-reference issue and change and to give issues well defined lifetime (for later archaeology/reproducibility)

- Is HackMD more responsive now that we have moved old stuff out?

- The main loss of time in our group was looking for "issues" in the fork repos, but they were only present in the original repo. Is that true?
    - Yes, normally issues are only collected in the "main" repo.
    - However, you can enable issues in the fork but it makes sense to track them in one place to avoid confusion later. so I never enable them on forks
    - The one time when you would enable issues in a fork is if the fork itself becomes a "main" or sufficiently important project in its own right.

- How do I pull the changes from the main repository to my forked repository after all the branches have been merged? Git pull just resulted in cloning my fork, not the main repo.
    - We will go through this in step G.

- Issues should have been explained before the excercise. We took time to define what issues are.
    - Thank you for pointing this out.

- Do we always need to open an issue before sending a pull request? 
  - no.
  - but it can be good to open an issue when you are unsure how the pull request should be shaped/formulated/programmed.
  - alternative: you can open a draft pull request if you want feedback and are unsure

- I would need one day of exercising only this part of collaborating
  - It is a lot of new stuff in short time. One practical thing can be to set up a second github account so that you can mimic working in a team even if you practice on your own. But more fun to do it jointly in a group.
  - good point. it's lots to take it. I also encourage to form a small group where we practice this. Or ask somebody for code review and feedback. Feel free to ping me (`@bast`) on github.

- Is there a way to have forks that make commits be changed to another branch instead of the one the user has defined?  If i want to test the commits but not put in the master branch from foreign contributers.
  - yes in the pull request you can change the target branch. it does not have to be the default branch. can be from any branch to any other branch.
  - only difference here is that auto-closing issues only works towards default branch.

-


- Could you explain again where I have to write the keyword "closes" followed by #issuenr so that github automatically closes the issue? Thanks
  - In the message that you write when making the pull request
      - What is I write the wrong issue nr? (by mistake)
          - this is where review comes in. After submitting the pull request, the common thing is that one or two persons will review, and then either accepted or request the pull request to  be modified. The can then point out things in the code ase well as mismatch of issue numbers.
          - As you start typing "Closes #...", the git UI will also start showing suggestions of issue names, making it easier to select the correct issue number.

- Why the issue disappeared? i dont remember if i address that in my pull request?
  - it moved from "open" to "closed" because either it got autoclosed by a commit message or by a pull request title which contained something like "closes #1"
  - ssee also similar questions above with more background why this can be usefu
  - The issue is "closed" but has not disappeared. So the full issue history is kept - however, nice when issues can be ticked off as closed.

- using the "git remote -v" why are the repos listed twice, with fetch or push in parenthasis ?
    - Usually the two are the same, but you may want to fetch from and push to different repos

- What if you fetch and merge while working in some of the files altered in the upstream? Does it cause a fast forward/hard merge/...?
   - git will prevent you from fetching files from upstream if you have files that have not been committed

- it is still not very clear to me the difference between git pull and git fetch
  - git pull equals: git fetch, followed by git merge
  - git fetch only fetches all commits that you don't have and updates remote branches (the `origin/somebranches`), but does not modify any local branches
  - git fetch in the terminal can be useful if you first want to inspect changes before modifying your local branches
  - using `git fetch` first is a safer option. It also is the only good option if you want to test a branch downloaded from a remote (typically someone else's branch)
- If I update my master branch (from upstream) that will not update my other working branches, correct? How should we keep the other branches up to date? Or should we?
    - only those branches that you specify will be updated, in your case the `master` branch. 
    - whether other branches should also be updated will depend I guess. Where do you want to start your work from? In many cases you would branch out from the master/main branch and then only master/main needs to be synced

- Appreciate the Luke/Obi Wan quote

- how to update local copy after having merged the fork with the "new way?"
  - `git pull origin master` in the master branch
- How to remove these exercise repositories at local computer and also github website? Addtional question: we need to do this on both locations (or can delete on one and pull/push changes)?
  - github: top of the repo page -> "settings" - > scroll down to "danger zone" where you can delete a repository
  - local computer: if you remove the folder, the repository is gone (since everything is inside `.git`)
    - when remove folder at local computer, it always shows rm: remove write-protected regular file, I need to type in yes many times, any way to rm it once
       - You can use `rm -fr repo_name`, but be careful, this will delete anything without asking again
       - Or `yes | rm -r repo_name`, slightly safer

- :+1: for "I am not very good with jokes" on the Star Wars one :)

-I would like to know what are the best ways to write a commit messages, I heard that they should be in present tense for example. 


## How to contribute to somebody else's project
https://coderefinery.github.io/git-collaborative/04-contributing/
- why after "git merge upstream/master", we push "git push origin master"? is not my fork repository already updated? (refers to step G)
   - this was indeed to update fork, assuming "origin" refered to fork
       - the syntax should have been explained, but it was not, and we had to use time to dig out an explanation
   - the fork does not automatically update itself, unless you either pushed changes to it, or used that new button to "fetch and merge" via web user interface
## Reminder before next week: finish setting up your conda `coderefinery` environment 
https://coderefinery.github.io/installation/


## Feedback
### One positive thing about today

- For the first time, I think I actually understnnd the concept of branch and fork properly...
- very nice on time schedule and exercises
- time management
- Explanation of how thinks work under the hood.
- the figures of how the repos communicate are very useful (e.g. first figure after section G. is perfect). 
- I made a successufull pull request
- speed was good
- overall a very good experience, learning a lot of new things (although not able to follow everything, being a beginner and all). 
- As an exercise leader, i am not just teaching but also learning a lot from the participants in my BR :+1:


### One thing to improve/change/remove

- We really struggled to finish the exercises, 5 more minutes each time would have helped. We had to rush, couldn't really fix when things didn't go super smooth...
- We spent a lot of time describing the first exercise and I'm not sure how useful this was. Maybe demonstrating it would be better. Or just do it in the breakout rooms and give us more time. +1
- today it was quite messy. Especially, in the exersizes many things where the learners where supposed to stop and do things while intructor was talking.
- Would be nice to gather the instruction for leaders in a box at the beginning of the exercies in this session.
- got very lost with the exercises today (but I am slow)
- Got irritated with the instructor saying it was nice weather in Finland (very unnecessary ;-) )
- some explanations could have been a little better, like the automatic closing
- Perhaps the generic explanations (what is x, y, z, why we need each of these, and under what conditions these are used) coming at first and then the detailed steps in how to get it done would be good? (This was done for the most part, but sometimes it felt we first did the hands-on and then learn the generic explanation why/when this is done)
- I think the lessons ended up being a bit too much of an info-dump. I get that the exercises help digest the information, but what ended up happening was that, as an exercise leader, I had to clarify a lot of the logic of the tasks (which should be a part of the lesson) before we could proceed with the typing exercises. I think more pre-empting on the part of the instructors would be very useful for future workshops. Ideally, questions that we know will come up should already be built into the lesson rather than letting them come up then answering them post-exercise. (I'm happy to elaborate/give more detailed feedback on this issue if the instructors think it's useful. -group 6 exercise leader)
- some commands are sandwiched between figures making them a bit difficult to spot.
- maybe we can have a single way of syncing with upstream. at present there are 3: shortcut, *proper* way (adding upstream) and the github GUI.
- You are doing an amazing job in managing so many different learners together, of course there are some minor issues but overall it's great work. Main challenge today was keeping up with the exercises and finishing the exercises in time, but we managed. I think the documentation is extremely complete and clear though so that is not the problem/reason. We spent time discussing things in more detail because we liked that so that is probably why. Nothing really to do about that IMO. Keep up the good work.
- Would be great if the streaming video links can be made available 'permanently' somewhere (for later access)? Thanks.
- Please, make the instructions be an ordered list of point where oine instruction is one point. For example, https://coderefinery.github.io/git-collaborative/03-distributed/#step-c-modify-and-commit is very difficult to follow while having to switch back and forth between the web page with the instructions, the teminals, and the github page.
- today's session was maybe suited for learners who new already quite some git. Newby in our team had serious problems following. Having to explain many things on the BR took time and then time was up. So, constrarily to many comments above, I find that time managment was poor: too much time spent on explaining the obvious parts of the excercise, and too litte time to actually do the excercise and look at what was going on in the github repos.
- it seems that the timing for the exercies is allocated for a perfect world when everything goes right. It would be nice if there was a buffer of time for mistakes or problems which often arise in the breakout room. 
