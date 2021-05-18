+++
template = "page-with-toc.html"
+++

# Questions and notes from workshop day 4

## Questions before day 4

If you have further questions please ask them below
- Hey, I have the following message while trying to run the command python -c 'import sys; assert sys.version_info.major>=3': SyntaxError: EOL while scanning string literal. Any problems with that? Otherwise, all the other tests for the conda env passed just fine.
    - That happened to me too! It worked when using " instead of ' though. I wonder why
      - thanks for this find. We will update instructions to use " instead of ': https://github.com/coderefinery/installation/issues/194
          - Thanks!


## Icebreaker

When and how did you learn to program? Was it in a school or work setting, or on your spare time?
- I had to learn how to modify the source code of some audio plugins. After that it was scientific programming at the university.
- I needed half a credit to finish Masters degree and Matlab course was just the smallest and possible to do anytime... I did not become the HW person that my N credits suggested but the semi SW person the .5 credits started.
- I started to learn on my own when I was, like, 11? Some calculator implementation of the pythagora's theorem or something, in Casio Basic ;) Nothing serious until higher education though.
- We had also a small Casio with a line display. I made jumping figures go through the display.
- I don't think I ever really learnt programming, just learnt as I had some tasks to solve. Always pleanty of space to improve :)

- My mum taught me to to prepare me for school programming lessons
- In the third grade :D with "logo"
- I borrowed a C++ book from the library as a teenager.
- With a friend, trying to scrape a website.

- I got fed up with copying and pasting from text files into Excel (when I was a postdoc) so started writing macros, then moved onto VBA, then Matlab, then Python... (also the obligatory time playing with BASIC on a Commodore 64)

- I had to learn as my data became too large, so mostly online. Also took some courses recently.

- I had my first exposure to programming as a teenager was some basics about C++. The majority of my programming I learnd on my spare time, then the more I studied at school and especially now doing research I had to improve my skils even more. I mostly worked with Matlab, Python and some Julia.
- first on my own on Sinclair and C64, then in school for C and C++

- with some kiddy programming games on a vintage pre-PC computer (up-to-date back then), afterwards some school coding in high school & uni, and then some "business" coding when working in the software industry after uni. I never learned "real" (i.e. scientific) programming 😢

- I've been learning through my workplace but mostly on my own. I am hoping to take a coding class in a school program shortly.
- I've taken a course of C++ at university. After that it was some MATLAB, python. But since 2014 mostly Julia. I am mostly self taught and I use it for scientific computing tasks.

- My datasets got too large to handle them in spreadsheets. Got some help from a friend but mostly autodidactic learning on the problem.

- First year of University education, part of the curriculum. Later, heavily used in courses and research work.
- University classes. Had been interested in learning it for a while, but didn't take it up until then.
- I first started in my spare time back when I was still in school in the early nineties.
- I'm not sure if I know how to program, I just read documentation and implement things I need.

- I started as the same time as I started my PhD. I was in a lab where everybody was suppose to write his own code in order to perform simulations. SO I did write my code in C at this time.

- I started in my spare time when I was quite young, started reading a book "Turbo C"



## Questions day 4


## Reproducible research: motivation
https://coderefinery.github.io/reproducible-research/01-motivation/



### Have you run into problems reproducing your own previous research or research by others?
- Yes, on both sides.
    - I've been the one leaving a project as the main and only developer without leaving enough info for the person taking over to go on alone (net effect, I am still working on that project to help)
    - I've entered a project with no documentation and few comments, and... well it's tough
- Yes, when there is a big delay between paper reviews and the numbers don't have the same realtionship that thye used to before.
- Yes. I spent one year of my PhD trying to reproduce someone else's research from papers, book chapters but no code. I failed. Never again! It was a serious life lesson (know when to stop or when you cannot make progress) and the importance of reproducibility.

- In the end no, but had to spend significant amount of time. Could have been made shorter if the documentations were done properly.

- Yes, several times. From a field that science is basically done using quantitative models and data, it is really frustrating how the vast majority of publications don't offer basic means for reproducibility.

- Yes, I was careless when docummenting steps, or recording key decisions.
- Yes, both my own and others. I've spent considerable time failing to reproduce others results, either because necessary information was lacking, or that the others results turned out to be wrong.
- Yes, I am currently trying to replicate a computer vision related study, but they used very costly third-party company for feature detection and vectorization.

- Yes, I once spent several weeks - in vain - trying to reproduce a computational experiment published by another researcher.

- Yes, lacking informations in the paper I was basing my work on.

- I tried some code from someone but it didn't work while it was supposed to do!

- I emailed one guy to ask how he did a thing, and he answered "I don't remember"...

- Yes; So many times. I work with very big data sets that need sooo much pre-processing and cleaing and that takes many steps. I try to update teh code with comments but still it take a me a while when I get back to the code after a couple months.

- Very often - mostly because it often is completely unclear how people have obtained the results, or they have used desktop software instead of code, which makes it very hard to share your method

- using random-"ness" is challenging.. I think we should include a seed and results with that seed to be certain that the method is as wanted.
    - very good point, +1 for reporting on the seed used
    - Something to look maybe: I had problems in the past fixing seeds in Jupyter notebooks to replicate randomised studies (got different results nevertheless). Was using Julia, so not sure if it is replicable for other languages.
- Some projects are NOT "open" so methods and part of the data are not disclosable... at leasts, PI might think so...

- Yes, research by others. Mostly due to insufficient documentation.

- Yes, trying to use a project that was set up for a particular database that I was attempting to use on our own database. I have yet to get it to work for us.

- Yes, published research & research by others from my group. Either due to insufficient documentation or jumping to premature conclusions, without communicating that the preliminary data was everything but sound.






## Organizing your projects

https://coderefinery.github.io/reproducible-research/02-organizing-projects/

- Where do you think one could have the metadata and licenses for the DATA, in a project directory? And for figures / tables? What's best practice?
  - data often starts on the harddrive in the same project folder but upon publication could become its own repository or archive with its own DOI. what is then important and useful is that the data archive references the code and paper. in other words code, paper, and data, should cross-reference each other.
  - If the data needs a separate license from the project as a whole, my personal opinion would be to place that license in the data directory
      - [The example structure](https://coderefinery.github.io/reproducible-research/02-organizing-projects/#directory-structure-for-projects) for example could easily have a license file under `data` directory

- How to version data is a frequent question I am asked. How should we store, archive or manage large data sets in a way that is compatible with reproducibility goals?
    - good question. We will talk more about this later, but suffice to say here that there are many online services to store versioned datasets, e.g. https://figshare.com/ and https://zenodo.org/

- a problem with using Git as a data repository: format of the data can be completely customized. This means that to read the data one must first know how to read the files. It becomes impossible to find specific data without first digging the details of a specific project. This, in my opinion, is a very common problem in many data repositories (e.g., DataverseNO)
    - I'd recommend [frictionless datapackages](https://frictionlessdata.io/) which include metadata, together with packages for most programming languages to open, interrogate and use the data.
        - any generalizable example? Probably most of this is field-specific.
        - datasets published as frictionless datapackages [here](https://datahub.io/collections)



### Word-count example project: https://github.com/coderefinery/word-count

- example project following (hopefully all) best practices for project structure!

- if you missed how to get into the "generate from", you can Hlike Like in ave

- have we talked about .gitignore? Can you say something about it/example please?
    - haven't talked about it no, but see answer above. It's an empty file used to be able to git-track an empty folder

- Should we use 'requirement.txt' inside the 'src'directory, or 'environment.yml' in the root? Are they somehow interchangeable (not entirely, of course)?
  - in this case we made the `environment.yml` the same as the one you have already installed. we have offered both because `requirements.txt` is more interesting to those mainly using virtual environments. `environment.yml` is more interesting to those using Conda. both have the same role but in different ecosystems.

- Why do we have a soft link for the binder?
  - I am unsure....
  - sorry which soft link do you mean? +1
     - https://github.com/coderefinery/word-count/tree/master/binder (symlinks to one level up) my guess is that this is a way to force Binder to use `environment.yml` instead of `requirements.txt`
   - I am checking but this may be part of the binder format: binder looks there.  It also looks in the root but maybe this makes it more explicit.  Checking...
       - to avoid copying the same file in binder folder. But it is not needed but recommended (much clearer to understand what is required for binder); however, it could be moved instead of having a symbolic link.
   - https://repo2docker.readthedocs.io/en/latest/usage.html#usage-config-file-location (but, in this cakes it isn't really needed since it would equally find it from the root of the repo)
   - No it is not needed,. Ealier we had both requirements.txt and environment.yml and this is why binder folder was required and a symlink was added to avoid replication.


- Is using Doxygen outdated or just overkill?
  - we will talk more about it tomorrow. I would not call it outdated. It can be a good tool for C/C++ projects (also other languages). For many projects README can be enough. more tomorrow when we talk about documentation.

- there was a question about `.gitkeep` which got removed (?)
  - this file (actually any file) is in a folder so that Git can track an "empty" folder since otherwise you cannot `git add` an empty folder in Git
  - sorry it got removed! Must have happened by accident

- How to check if there are conflicting dependencies?
  - Conda (or other package managers) will complain if there are conflicting dependencies. Or did you mean how to check this before trying to installing them? Like a "dry run"?

- Is it my impression of in the old days the dependency hell was much less of a problem? For example, you could take an old Fortran77 code and use it provided you had the compiler (one, big dependency, but only one!). And you can still do that now... but you cannot do the same with python2 code from 5 years ago...
  - not only your impression. indeed dependency management did not get much easier and keeping project reproducible and running seems to have gotten more difficult. indeed rerunning a code written in the 90ies is sometimes easier than reviving a project from 5-10 years ago.

- I lost a moment of the previous discussion, what are the environment.yml and snakefile for?
  - where they are or what they are for or both?
  - they are here: https://github.com/coderefinery/word-count (we generate an exercise repository from this template)
  - what they are for:
    - `environment.yml`: documents dependencies
    - `Snakefile` we will see later: documents a workflow
      - Thanks, I wanted to ask what, typo :D




## Recording dependencies

https://coderefinery.github.io/reproducible-research/03-dependencies/

Compare these four requirements.txt solutions:

- A
    - Hell
    - A lot of work to get this one to function
    - Bad idea

- B
    - Relies on the projects to be updated in a backward compatible way (good luck with that)
    - No
    - No version numbers for packages

    - Might be difcult to get working after a few years

- C
    - I feel it's the best among the four, at least the packages and their versions are clear, and for the someproject and anotherproject the link is there to get access to. Maybe better to add the version, like that in D.
    - How do you update?
    - For C and D, if the software is not updated for a long time, we miss the new updated to the requirements too
        - Usually not a problem
        - What if there's a security problem with some of the dependencies that has been fixed years ago, but you are using an older version
        - Say you are parsing xml data: there are [numerous attacks](https://gist.github.com/mgeeky/4f726d3b374f0a34267d4f19c9004870) that can be a danger if you operate on data that comes from untrusted sources (big data stuff like scraping the internet, ...)

- D
    - Depends whether the less well-known packages are easily available from major channels(?)

- general notion from own experience... need some package to do something.. try installing several and not uninstalling all of them. Then my environment is working but a mess. How to avoid this?
  - I make sure my environments are disposable: deleting and re-creating should be a normal thing to do.
  - Do not hesitate to create a new environment: one environment = one purpose. when I need to do something else, I create a new environment.


- any advantages to using conda over pip or vice-versa?
    - conda is a package manager and is used for packaging many different software, not only python packages.
    - in addition, conda is also used for environment management (eg we use the coderefinery environment where we have everything we need for the workshop installed into, after the workshop we can remove the environment and the rest of our computer is not affected by it)
    - one could also use eg pip as python package manager and then eg virtualenv for environment management

- need to highlight issues with using conda and pip together
    - if you use pip in a conda environment, conda doesn't then know anything about the packages installed using pip
    - best practice is to install all dependencies (that are available) using conda, including the dependencies of the package you will install using pip. Finally, install the desired package using pip.
    - When using pip inside a Conda environment, install pip in conda, `conda install pip`. This helps coda track the pip packages.

-  What is binary (vs Python)?
    -  by binary we mean "exectuable" e.g. a program that can be executed.

- What does "activate" and environment mean?
  - meaning switching into the environment and making dependencies visible. later you can have multiple environments, one per project, and can switch them on and off (activate and deactivate it)


- What's the difference between "requirements.txt" and "environment.yml"?
  - answered further up. same idea but different ecosystems (former is for virtual environments, latter is for Conda environments)

- Why do I need to deactivate before activating another environment?
    - it's not needed, don't think it makes any difference
        - good because I never did...

- If I have two environment using the same python libraries, will they share the lib with a pointer to the sole one or in my computer conda will keep both libs?
    - It used to do it (to save space); I am not entirely sure it still does.
    - I am also unsure but I thought that it recently changed from duplicating to not duplicating :-)
    - Checking now, it seems it duplicates (on windows).
       - thanks for clarification!

- Is there any way to use auto completion within conda?
  - I am using fish shell which has great autocompletion for tools, including conda
  - But also other shells can learn this but I am not sure how.
  - Last time I checked there was no bash-completion available for conda.
  - There is a fix for bash here: https://github.com/tartansandal/conda-bash-completion
      - This will also be fixed in the next conda version


- if I install a package in two environments, will it actually take twice memory from my pc, or is there a shared place to physically install packages?
    - conda is clever about not re-installing same files in two locations, instead it uses hardlinks in a new environment to point at packages installed in another environment

    - does it update the hardlinks if I delete the package from the first environment?
        - there you hit the limit of my knowledge of conda. Hope someone else knows!
    - As mentioned previously, it looks like packages are duplicated (at least this is what I have now on my windows laptop). Earlier, (or many on other systems) packages were not replicated when they exist in the base environment and I had issues (packages were deleted in conda env too). Another reason to avoid "adding" packages in conda

- ```Your shell has not been properly configured to use 'conda activate'.``` Is it just a problem with the bash?
    - when I had this problem yesterday `conda init shellname` fixed it, e.g. `conda init bash` if you are using git bash

- Is conda activate similar to module load?
  - yes, very similar in what it does although the tool is different. but the idea is the same (on some machines you first need to module load conda to then activate environments so it can be two layers, but same idea)

- Any difference between "conda install .." and "pip install .." ?
    - Conda install uses conda package manager, where many packages not only python packages are available . pip is only  for python packages. When using conda to install a python package, then all the dependancies including the python environement and system level libraries can be installed. When using pip to install a python package then only python package dependencies are installed and the system python (or the python active at the time of install) is used. You could mix these as well. Create a conda environment, activate it and then use pip. In this case, the python packages installed with will end up in the conda env.
        - Then is a package can be installed using pip, can always be installed by conda?
    - If you install pip from Conda (`conda install pip`), Conda will track any packages installed with this new pip.

- couldn't really understand what a 'dependency' is and how it is different from a package in a specific version
    - dependency is when one package relies on another package. In the python world for example, installing matplotlib also installs numpy because it's a dependency.



### Type-along exercise
https://coderefinery.github.io/reproducible-research/03-dependencies/#exercise-exploring-conda-environments

- still extracting packages...
    - unfortunately conda can be slow to resolve
        - done now. Next time keep this in mind in the timing of the workshop: the type-along  did not quite work
            - thanks, good advice
    - pro-tip is to investigate using Mamba, which is much faster at resolving dependencies


- So, an environment is essentially a folder + a list of package dependencies? Anything else that makes it "an environment"?
  - yes, it is a list of packages which can be made visible or not visible. they are stored in a folder. this can be standard folder location but it can also be a folder of your choice `--prefix` option.
  - the environment also makes the code/dependencies more portable, as it is easy to export the environment between different machines and systems

- Can you explain the "channels"?
  - collections of packages. there is the official one, then `conda-forge` is the de-facto big channel, but you can also create your own where you collect packages.

- Could Johan leave the command history on screen share during the break
  - thanks for good suggestions

- could/should pip and conda be combined?
    - there's a larger risk of running into dependency conflicts if you jump between using pip and conda. Best is to stick to only one, but if you're using conda and need pip for one or a few packages, best is to first conda-install everything, and after that pip-install the rest
    - If you use pip in a Conda environment, always install pip from Conda, `conda install pip`. This way Conda can track packages installed from pip.

- How to check if package is installed with conda or pip? I mean inside env.
    - you can see it in the output of `conda list`, last column!

- how do you do version control of conda environments?
    - Use an environment.yml file, and keep that file in version control.

- Do I need to create a new environment inside any specific folder? I had a "Access is denied." when trying to export the requirements for a txt in my own machine.
    - when you do `conda create -n myenv ...` the environment is by default created into your miniconda (or anaconda) folder, under `envs/`. You can specify explicit path by `conda create -p /path/to/my/env ...`
    - not sure why you got "access denied" from an export... Which command exactly failed?

- Where is the requirements.txt file saved when exported?
  - when you typed `conda list --export > someplace`, you redirected (">") it to "someplace". so you decide. typically `conda list --export > requirements.txt`
    - I mean, which path?
    - if you did not specify the path then it is saved in the current working directory (you may find out what that is by typing `pwd` for unix/git bash)

- requirements.txt and environment.yml are still in the current working directory … if not needed they should be removed. let's be sustainable and clean ;)

- What is the difference between a vitual machine and a container?
    - a virtual machine (VM) is "more virtual" than a container. In a VM everything is virtualised, while a container only virtualises the operating system

Command history for https://coderefinery.github.io/reproducible-research/03-dependencies/#exercise-exploring-conda-environments:
```
conda deactivate
conda create --name myenvironment
conda activate myenvironment
conda install pandas
conda list --export > requirements.txt
conda env export > environment.yml
less requirements.txt
less environment.yml
conda env create -n myenvironment2 -f environment.yml
conda env remove -n myenvironment2
```




## Recording environments

### Containers

https://coderefinery.github.io/reproducible-research/05-environments/

- It needs sudo to run docker, what if we are not a sudo user?
  - Your sysadmin should add you to the "docker" user's group.
  - good point, I would not run docker images as sudo.

- nice single shot, but we cannot do it: we do not have docker in the enviroment
  - we didn't want to require it for this time so this is demo-only. it's a nice way of running a computer inside another computer. but we did not want to require participants to install it

- It would be nice to have a discussion on security when using other peoples software (but this isn't a CR workshop thing)
  - good point. also I would not run a container as sudo. and always verify where the container comes from. I also always want to inspect how the container was built so if I cannot see the container "recipe" (Dockerfile, Singularityfile), I will be very hesitant running it.




## Recording computational steps

(Workflows)

https://coderefinery.github.io/reproducible-research/04-workflow-management/

- any text editor available in the terminal lauched by Binder? (vi/vim not there)
  - is "nano" there? (I will also try this ...)
    - no nano
    - hmm....
  - Worst case you can use the Jupyter text file editor... in the future we can install nano.
  - `conda install nano` (maybe also `vim` can be conda-installed, checking ...)
      - but the Jupyter text editor is quite good!

- Why Snakemake and not a simple (additional) python script?
    - A Python script would be the same as [Solution 3](https://coderefinery.github.io/reproducible-research/04-workflow-management/#solution-3-script)?
    - Snakemake also tracks changes, skipping to re-do things if no changes are made.
    - Snakemake also comes with "parallel support" (the `-j ` flag to run faster on multi-core CPUs).
        - O wow!
    - E.g. I (helper) am running 300 jobs in parallel on the HPC using snakemake. It automatically submits jobs on the HPC using `sbatch`

- I got snakemake-minimal in the coderefinery env. That ok?
    - Yes, should be fine.

- what is the time resolution of snakemake? I mean, does it check the nanosecond of file creation or the second or what?
    - interesting question... Not sure, i'll check

- It probably isn't, but is Snakemake functionality limited to python files only?
    - no it's completely general and can run any programs. Snakemake itself is written in python though and its syntax is a superset of Python

- Any comments on mamba, the package manager that is recommended for use with snakemake? Does it do something that is better than conda?
    - **unanswered**

- Why the time  command gives different real times if i run the same command?
    - other processes running on your computer can affect the time it takes to run your program.


#### Exercise: Snakemake
Link: https://coderefinery.github.io/reproducible-research/04-workflow-management/#exercise-using-snakemake

- suggrstion for instructions: split point 1. into two points.

- `snakemake -j 1` fails saying:
    ```
    Error in rule count_words:
    jobid: 7
    output: processed_data/last.dat
    log: processed_data/last.log (check log file(s) for error message)
    ```
    Am I missing something?
    - difficult to know what's going wrong. Does the log file give any clues?
        - Log is exactly the same as the terminal output, so no additional info is given in the logs.
    - Perhaps an annoying, subtle syntax error?  That's my only guess...
        - Well, the `--delete-output-all`` worked fine. I will have to check what the problem is.
    - my group had one participant with the same problem also :/ mysterious
    - I have also the same problem.
      - was this running in git bash? or in which shell or where? (binder?)
          - Win10, git bash.
          - Same: Win10, git bash
              - note : I was doing the same, on the same settings, and had no issues
  - I would try running the steps manually in terminal (`python word_count.py ...`) and check if you get any errors

- from the time measure it looks like the parallelization performance is terrible (6.7 sec on 1 thread, 4.4 sec on 4 threads). Comments?
    - That's not so bad, not all the tasks are parrallel (see the job counts)
        - I mean: is it ensouragable to use snakemake to partallelize or is it better to rely on proper multithreading strategies?
            - the scaling will be much better if you have time consuming steps that can be performed in parallel (cf. [Amdahl's law](https://en.wikipedia.org/wiki/Amdahl%27s_law))
        - It always depends on the circumstances and code

Follow-up from discussion about Docker:
- https://hub.docker.com/repository/docker/jannetta/tensornotebook




## Sharing code and data

https://coderefinery.github.io/reproducible-research/06-sharing/

- will the sandbox DOI be deleted automatically after I log out?
  - not immediately but eventually they will disappear. but if you are unsure, you can also watch

#### Exercise until XX:03
Link: https://coderefinery.github.io/reproducible-research/06-sharing/#exercise-get-a-doi-by-connecting-your-repository-to-zenodo
Duration: xx:03


- the DOI link generated by Zenodo redirects into a 404 error page from Zenodo
    - I think that's because it's sandboxed mode

- Note instructions in exercise need updating - Github does not have a "released tab" any more.
    - thanks for feedback, i raised an issue on the lesson repo
    - :+1: - (I left that as an exercise for our BR!)
    - it moved to the right hand side on that page
    - https://github.com/coderefinery/reproducible-research/issues/163

- PLEASE, explain why we got error 404 on the zenodo DOI link.
  - because this is only a sandbox and also on the "real" page it can take few minutes until the DOI resolves. so here for the exercise we don't expect the DOI to resolve.

- And the link was supposed to be showed on zenodo?
  - yes, if you visit on zenodo the "swiched-on" project, after release, you should be able to see a DOI there, which you can also add as badge to the readme

- Some learners reported that Zenodo requests access to their organizations while granting GitHub an access to their personal accounts. There is a possibility to disable it using a link that gets sends to the learner's email address but maybe it should be mentioned.
  - in future we should recommend for the EL or expert helper to demonstrate it if participants are worried about enabling permissions


- non-open is FAIR?!
    - Yes, FAIR != open. FAIR describes "quality criteria". Data can be closed (e.g. personal sensitive data if sharable at all, restricted access) but still be FAIR. On the other hand, data can be open but poorly documented and thus useless.
    - But non-open does not seem very "Accessible"?
      - I agree, I also find it a bit strange. But sensitive data can be FAIR if there is a clear mechanism for how to get access to it which may be controlled or embargo-ed.

- What is the main purpose of a DOI link? Why not simpyl cite the link address of the Github repository?
  - because nothing prevents me from deleting the github repo one year later but DOI is "forever" so the main motivation is to preserve code/data/workflow/manuscript
  - in the process of creating a DOI, files got actually copied over to Zenodo (in this case only to the practice service) so that it will work even after deleting github repo/account (when using "real" Zenodo)

- We cannot put DOI badge in readme in the master branch that we archived in the sandbox.zenodo. How can we do that? Do we need to make a new branch? (or is it always so that we need to make a new branch to change readme and merge into master?)
    - You can not do this, in the same way that you can not put the git commit hash identifier inside a git-tracked file, as the hash is generated once you commit the changes. Same goes here, if you modify the readme adding the DOI, then this will be new code, so the DOI would no longer be the same (as it's associated with a certain git commit). Think of the DOI as another way to refer to a certain specific git commit.
        - I see, thanks. Then however, how can we make sure that the DOI which is attached to the archived version is the same as the version on which you get the DOI badge? It almost sounds contradictory.
        - I tried going to "Releases" -> "Edit relase" then I could add the DOI badge there. but not sure if this is the best place.
    - you should only need to copy the markdown text for the badge into your README file (on main/master branch). Does that not work?
        - no, it does not in the master branch. so always making a new branch to do this edit? When I tried clicking editing icon (the pen icon) on GH, then it shows a pop-up message that "You must be on a branch to make or propose changes to this file"
            - hmm, this suggests that the main/master branch is "protected", i.e. can't be pushed directly to. Not sure why that's the case for you - it suggests you're not the owner of the repo but a collaborator
                - I (we) used template of the word-count repo in my GH account. Maybe I should try with another repo?





## Social coding

https://coderefinery.github.io/social-coding/


Questions from https://coderefinery.github.io/social-coding/social_coding/

- Did you ever share your code? If yes, what motivated you?
    - yes, getting credit for it. :+1:
    - yes, motivated by making it used and useful, cited, credited, peer-reviewed :+1: :+1: :+1:
    - Yes, along a paper
    - Yes, hoping somebody else builds upon it.:+1:
    - Yes, hoping for my hard work to make more waves than what I could have achieved alone (Ended up with someone publishing in Nature using my code  :D )
    - YES because I hate when other people don't do it, so I need to do it myself also. To enable reproducility.:+1: :+1: :+1: :+1:
    - yes, usable for others :+1: :+1: :+1:
    - Yes, for openness and transparency :+1: :+1: :+1:
    - getting by more easily when other, more skilled, people give help :+1:
    - Share with students that work with me on research or master thesis :+1:
    - yes, I was inspired by the community that shared so much useful software over the years! :+1:
    - Yes, I had to share my code used in my thesis/article once published :+1:
    - Yes, to get more citations.
    - Yes, so it can used and cited
    - Yes, to make the analysis reproducible for others
    - Yes, to make sure I have access to it after the end of a post-doc :+1:
    - Only smaller codes, but we are in the process of releasing all our projects as open source.

- Come up with reasons for sharing your scripts/code/data
  - Get attribution and recognition for your work when others use it -> build my "reputation"
  - Allow others to "play" with data and functions
  - It will be more easily found next time I need it
  - Further develop your idea among other researchers.++++++++++++++++++++++++++ :+1:
  - Get a peer review/feedback on your work :+1:
  - increase relevance of research outputs
  - Find the bugs/mistakes
  - Get advice on how to improve your code from strangers
  - get good improvement suggestions
  - Have license to use it after moving to another institution
  - It pushes me to have everything recorded and versioned. It will make my life much easier later!
  - reproduciblity, citability: everyone in our field is working with closed source codes, making reproduciblity an issue (especially since many published results are questionable)
  - sharing best practices - it is a huge waste of time that everyone re-invents the same wheels, falling in the same pitfalls/errors that wastes months/years

- Also think about reasons for not sharing
  - cutting-edge technology is strategically important: I might want to keep this advantage for a bit before releasing it to competitors. :+1:
  - WIP which is senstive for a license etc.
  - Not complete/functional yet :+1: :+1: :+1:
  - Fear of not previously found mistakes becoming public
  - Fear of criticism
  - Embarrassment about own code practice and of not following some overlooked standard. :+1: :+1: :+1: :+1: :+1: :+1: :+1: :+1:
  - Fear to someone else get ahead of you.:+1:
  - Sensetive data/thrid party agreaments (with industry for example)
  - Time taken to curate data etc and allow other people to make sense of what was done, recorded etc
  - the expectations of others might be too high (in terms of generality) and this will result in a negative judgment on my research-level code. :+1:
  - competitive field of research
  - Not allowed, employer makes the decision
  - Embarrassment about it being not properly structured etc :+1: :+1:
      - I would also not like to upload crappy code, but at the same time I would rather someone uploaded crappy code than nothing at all...
  - It takes a lot of time to make my code truly useful to others - so I don't share it unless I actually believe someone might use it/find it interesting
  - too simple scripts
  - if there are bug/errors and not completed yet.
  - for those without formal programming education: embarrassing to share working but not elegant scripts
  - not be banned by software companies that bann you if you share the performance data for their software...


- Come up a question, now we know where to share, is there a good/easy way to search for scripts?
    - Try key words such as `python <functionality I need>` on google, pypi or on github
    - Also, looking through Github users' repositories - on Github you can follow users whom might have similar research interests or be working on similar problems - Social Coding!
    - I think there are more and more sort of empty websites about programming issues that only repeat the easiest cases. Someone told these are only made to pump up the CV of the person who made the page. I find it is more difficult to find good sources on the net.
        - Perhaps stick to Stackoverflow and similar sites, the Python reference manual and documentation - often better quality than these shell websites/blogs

- Citing software/packages appropriately: Many journals limit the number of citations. Unfortunately, those are the citations that get kicked out first.
  - This is a very good point, and we should push for citing e.g. the codes we use (anything else is not fair).
  - Indirect "solution": Some journals allow aggregating references under the same number, maybe this could be one solution in some cases.

- I try to cite some packages used in R but should cite ever single one?
  - This is a good question for me to.  Do you cite Python?  Numpy? It goes deep. Or cite scientifically-relevant software?
  - Often, you will add a detailed table with materials etc. At least here you should list all the packages and versions used. However, citations here will likely not show up in citation metrics.
  - Usually citations are practically free (I guess some journals might have limits, depending on the field), so I'd use a low threshold for citing.
  - The packages you use are important information for the reader after all
      - reproducibility
      - what if the package you used had a bug that affects the results?

- As paper peer reviewer, what actions can we take to highlight reproducibility (or lack of)?
    - always reject if equations are not adequate or no code reference given?
    - "we used in-house software" this should always raise more questions on the code
    - Most journals now ask you the question if there is a link to data and software, and if that link and the supllementary material is reachable and usable
    - I have this ready that often paste on reviews as a major point or concern: "Reproducibility. My main concern about the paper is related to reproducibility. The authors do not offer any means to allow for reproducing the results they have observed, nor provide a source for the code or more details of the computational experiments." Often I get a review with at least a link or a zip file of the sorts, which is not great, but a beginning.


- Perhaps CodeRefinery could create a badge for reviewers that want to impose the publication of code?
    - **unanswered**

- What if our code get used, but doesn't get cited?
    - I had this issue before. I contacted the user and informed them of the software license and need for attribution. It was lack of knowledge rather than malicious behaviour (the authors shared their code on Github, so I could search for source code strings and find hits). Make it very very clear how to cite your software! E.g a copy/paste reference in the readme.
        - Do we then have to keep looking out for new publications and see if some might be derivative of ours. Feels a little exhausting. Maybe I am being paranoid
            - In my experience the (small) risk of malicious exploiters are far outweighed by benefits of sharing code.
            - I second that stealing code seems to be rare, kind of analogous to someone stealing the contents of your paper: it *can* happen, but usually doesn't, and one just has to live with the risk as the gain is usually a lot bigger than the risk
            - And not citing someone is real scientific misconduct? :+1:
    - To me same as if someone doesn't cite a paper.  Hopefully making software citeable (later in the lesson) helps some




### Exercise

bottom of https://coderefinery.github.io/social-coding/social_coding/#what-contributes-to-reusability

#### Recommendation - Room 1
- Companies-Universitiy collaborations must include clauses on code reusability and openess of code.
- Promote resusability policies as part of research groups.
- Use permisive licences, but it is difficult given all the options.

#### Recommendations - Room 7
- make the source code public!
- add attribution for authors who didn't use version control (JSON author and software metadata for Zenodo)
- add contribution instructions :+1:
- add environmental file
- add code of conduct :+1:
- add a LICENSE
- improve readme
- use Julia packaging features to add requirements and package the software (for users, not developers)
- make commit messages more descriptive

#### Recommendation - Room 11
- Realised we are doing well on most of our packages/ projects, but some have wrong license or no license.
- Code of conducts are missing so need to consider that.
- We had discussion on how to clarify releases and versions


#### Recommendation - Room 11
- Include a licence
- DOI and tag releases
- Installation instruction and example for some scripts
- Contribution guide

#### Recommendation - Room 15
- Include a licence
- Releases
- Examples

#### Recommendation - Room 17
- Metadata
- License
- ORCID of authors
- Dependencies (environment.yml, requirements.txt
- Readme file
- Version/releases

#### Recommendation - Room 19
- Structure info in README file to facilitate quick understanding of what kind of guacamole this is. Avoind long text.
- tutorial/worked-out example: how fine is "chop onion finely"? Picture.
- FAQ, link to wiki
- feedback section for users

#### Recommendations - Room 20
 - dependencies to install software, installation instructions
 - issue templates, PR templates
 - citation link

#### Recommendations - Room 22
 - We were adding LICENSE & discussing around

#### Recommendations - Room 23
 - Findable: License, use online indexing service, allow crawling, just having a GH repo is not enough, creating a DOI
 - Contribution guidelines (units of measurement etc. for recipes)
 - Accessibility: different (human) languages e.g. DE, ES etc.
 - Reproducibility: note size/weight of the fruit, specific species/variety of the fruit

#### Recommendations - Room 4
- README file with clear instructions, description of files, how to install/run (if applicable).
- Add license
- Add clear contribution guidelines for those who want to contribute (e.g. code style and standards).
  - Add a code of conduct.
- Support section (contact, FAQ, what to do if you find a bug or have suggestions for improvements)

#### Recommendations - Room 5
 - Documentation for users (how to run, examples, etc.) and developers (more internal details about the code - architecture and design details, module and function docstrings for them to be able to contribute features or fix bugs)
 - License
 - Contribution guidelines


#### Q&A:

- Can/should one have difference licenses for different version of the code? Or should one make a fork instead if one wishes to change the license?
  - some projects change license on the way so it is possible having a different license in the same project which changed over history
  - note that not everybody has the right to change license. depending on code ownership and the license itself.
      - I'd love to have some more elaboration of this point, if possible. (_e.g._ the extreme case of all authors agreeing to change away from GPL or another copyleft.)

- Where can we get a "Code of Conduct" - are there standard templates accessible somewhere? Is it OK to just copy-paste this from e.g. [the Carpentries](https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html), [CodeRefinery](https://coderefinery.org/about/code-of-conduct/) or somewhere else?
    - yes you can reuse existing CoCs. One popular CoC is the [Contributor Covenant for open source projects](https://www.contributor-covenant.org/), or the short CoC originating from The TODO Group (which itself does not have it available anymore)


- I think once I found in github a page which had a guide to add "good to have" files (license, readme, contributing guideline etc.) to the repository, but I cannot find that page in my repositories anymore :(
    - It's here: https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-profiles-for-public-repositories (for your repo, it will be `https://github.com/<youraccount>/<yourrepo>/community`)
    - There are templates for repositories/projects which help with this e.g. [cookiecutter](https://cookiecutter.readthedocs.io/en/1.7.2/tutorial1.html#step-1-generate-a-python-package-project) and [PyScaffold](https://pypi.org/project/PyScaffold/)
    - Also, have a look in established projects/repositories e.g. numpy, scipy etc.

- How to choose a licence? Any tips of tools to naviate the see of legal terms?
    - THE best place to start, without complexity, is **https://choosealicense.com**
    - if you want to learn more about the different licenses, without too much effort and without a very steep learning curve, please check out https://cicero.xyz/v3/remark/0.14.0/github.com/coderefinery/social-coding/main/licensing-and-cakes.md 🍰🎂

- if you find some unlicenced code online and incorporate it into your own code, how would/could you licence it?
    - unlicensed code normally means that it can't be reused. If you've already incorporated into your own code maybe you could ask the developer to license the code?

- What is the difference between ORCID and DOI?
    - DOI: digital object identifier (persistent ID, used for articles, datasets, published software,...) - https://www.doi.org/
        - ORCID: persistent ID for authors. https://orcid.org/ Recommended for all of you to create one if you haven't done yet. It's not a "yet another commercial website"😉

- Could you show/link to an example for a code of conduct text? Would you add this as a separate file or as part of the readme document?
    - [Github help: Adding a code of conduct](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-a-code-of-conduct-to-your-project)
    - [Open Source guide on Code of Conduct](https://opensource.guide/code-of-conduct/)

- What is the advantage of using Zenodo's (or other's) DOI to a github repo vs using the github repo link itself and point to a release?
    - A release on Zenodo is permanent, even if you decide to delete your Github repo
        - Is the file (.zip/.tar.gz) copied to Zenodo or is it just a link?
           - the data archive is copied and will persist even if you delete github account/repo
               - Very very important! Good!
    - Awesome about Zenodo: You can edit all the "metadata" (authors, abstract, links, release date) later, which is very handy. You can add ORCIDs and other links! (The archived data|code themselves cannot be updated unless you release|upload a new version)


## Licensing
https://coderefinery.github.io/social-coding/licensing/


- Almost all PhD students have to sign an agreement about "giving up" exclusive rights on the work produced in the project. What a student can actually publish and get exclusive credit for is never clear
  - In Finland it depends on the source of your funding in a very non-intuitive way, basically don't assume anything
  - I think it also depends on the university where you are. In some universities you own your work, in others the university owns.
  - I fand it interesting how there is so much emphasis on open ssscience now but things are as hard as possible to actually make it open. :+1:  Once I asked my supervisor to open something and the response was "just do it, whatever you do don't ask permission since who knows what will happen."
      - Great quote!
      - Similar to my manager's: make it open and we'll deal with it later. It's always easier to ask forgiveness than seek permission.

  - Universities should have a person or a team whose duty it is to help with data management and other licensing concerns. Find out who it is in your university and contact them! It might be called a "Data Steward" or perhaps something entirely else
    - Once I heard a joke "If you want to open something, just do it.  If you don't want to, ask and just wait for the reply..."  Though it is probably much better now since people care, hopefully with policies so that you don't need to ask.
  - Many unis have the policy that code/tools developed as part of education is owned/fully re-usable by the student. The rationale is that a PhD/Postdoc count as education/continuation of education.

- Can licenses work just for part (e.g.) of a repository?
  - yes it is possible to have per-file or per-module license (example: Mozilla Public License allows this)

- Derivative works and dependencies - if I have numpy in my requirements.txt, am I creating a derivative work?
    - Answered in the lesson (same as 7).
    - If those dependencies are under GPL or AGPL, is it a derivative work then? I suppose yes(?)


- the rewriting of a code in a different language is probably close-to-impossible to prove...
  - Like many things, it's not an issue until it is... see some recent court cases, luckily our stuff is probably never so important this is a risk.
      - do you have a link to some of those cases?
         - **unanswered**

- At least for me, I cannot always separate codes I write for work and code I write for hobby. Many times I start something for hobby and then realise I can use it in my research, I guess at least in that case I own my codes. On the other side, it sounds like a loophole to avoid giving up ownership.
  - In this case I say I open everything for work... so it doesn't matter who owns, it will be opened anyway.  Chance of issue then is small (but certainly exists...)
  - Or you are working from home? :laughing:
    - I do use my personal computer and personal internet connection just to be sure :)
  - When you are a researcher the boundry blurs a lot. :+1::+1:

  - Also I heard (but might be wrong), that some companies have a policy/contract that they could claim ownership of whatever open source code you do, even if you do it for yourself "as a hobby" :+1:
      - That can happen. The lesson here is to always read all the papers you sign, and consider if you are ready to sign
      - Depending on the legislation claims like that might not be legal and thus not valid. Contact e.g. a trade union or some other place that offers legal advice.

- Are there formal requirements on a license to be a valid one? Like, I guess I cannot make a license "only lefthanded people can use this code and only on Fridays"
    - **Don't make a license! EVER.  Use an existing OSI approved license only (for code). And an open cultural work license (Creative Commons) for other creative work than software.** A custom license makes your code essentially unusable as the open-source community relies on the standardisation of approved licenses to reuse code. And it is already complicated enough... :+1:
    - I guess  licenses can say anything, but it wouldn't be open source and people would stay away from it.  Or do whatever they do (use but don't tell you)
    - Some countries will not enforce weird licenses, or the weird parts of them. Many start with the declaration that if any part is not enforcable, others should remain in effect.

- Regarding copyright/licenses: let's say I want to include an image from a journal publication in a tweet. Is it enough to add the citation/copyright in the tweet/as a watermark in the image?
    - **unanswered**



- **Learning Bash shell:**
    - [Command line essentials for Bioinformaticians](https://bcc2020cle.bioinformatics.guide/) ([Slides here](https://rpubs.com/iracooke/bcc2020cle), [Video here](https://bcc2020.sched.com/event/c7Sz/command-line-essentials-for-bioinformaticians) or on [Vimeo](https://vimeo.com/441683367), Hands-on exercises linked from the first site) - In fact most of it is not bioinformatics-specific just the the example problem is
    - [Software Carpentry shell tutorial](http://swcarpentry.github.io/shell-novice/)
    - https://scicomp.aalto.fi/scicomp/shell/ (crash course, two videos) :+1:
      - https://scicomp.aalto.fi/training/linux-shell-tutorial/ (long course)


## Feedback

What was particularly good today?
- Good speakers today :+1: :+1:
- Great material too!
- I enjoyed [an instructor] asking questions and making suggestions [in the reproducible research lesson].
- the second part on licensing by [instructors] was an eye opener. Many simple issues were presented in a clear and concise manner.
- Fantastic work by the lecturers today: very smooth with good pacing and time management.
- A lot of interaction :+1:
- Having both [instructors] in the last session was nice, it felt very "dynamic" when they interacted (like, it was easy to keep up interest and not fall asleep) :+1: :+1:
- Good installation instructions for creating the conda env etc. and be ready as we dive into it.
- [Social coding instructors]'s part:+1:


List one thing that we should change/remove/improve
- Went through the material very quickly
- It would have been good to emphasise introductions and context for each section as we jumped around a lot. :+1: :+1: :+1:
- The first part of the training should have been longer today :+1::+1::+1:
- The first part was a bit rushed, I struggled to grasp the utility of Snakemake +2 :+1:
- The first part on Snakemake was fast. Could have been slower; still, very useful. However, the second part on licensing by [instructors] was an eye opener. Many simple issues were presented in a clear and concise manner. (copied this part up)
- First part was a bit moving back and forth.
- Explaining what touch-ing a file is, in snakemake exercise
- More concept explanation over "if you run this command you start a docker instance" would have been more understandable.
