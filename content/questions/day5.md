+++
template = "page-with-toc.html"
+++

# Questions and notes from workshop day 5


## Icebreaker for the day 5

Are you using Jupyter notebooks?
- yes: ooooooooooooooooooooooooooooooooooooo
-  no: oooooooooo0oooooo

Are you using nbdime to diff and merge notebooks?
- yes: o
-  no: ooooooooooooooooooooooooooooooooooooooooooooooooooooo

Are you using https://mybinder.org/?
- yes: oooo
-  no: oooooooooooooooooooooooooooOoooooooooooooooooooooo

Are you using R Markdown and/or R Studio?
- yes: oooooooooooo
-  no: ooonoooooooooooooooooooooooooooooooooooo


## Jupyter notebooks

Material: https://coderefinery.github.io/jupyter/

You need to activate the Conda environment: https://coderefinery.github.io/installation/conda-environment/#activating-the-coderefinery-environment

- https://colab.research.google.com/ is also a good place to use jupyter with others

## Questions

- Can I share a notbook I created using CR conda env with someone who do not have it ?
    - yes you could add your notebook to a GitHub repository and include the environment.yml file in the same repo. Anyone else can then launch your notebook on mybinder.org with the same software environment!

- A problem I have with using Jupyter notebook for plots is the quality of the exported figure. It takes an extra line to print a journal-quality figure, rather than displaying it in the notebook. Any better way to avoid the extra line?
    - What extra line are you reffering to?
        - I don't have it in mind now, but is about writing to file rather than to screen. So it is either one or the other.
    - What I use is `plt.savefig('../../paper/figs/radiuses.pdf', dpi=300, transparent=False, bbox_inches='tight')` and I am happy with it, but would be interesting to see what others have to say about this.
        - yes, plt.savefig()

- What is linear/non-linear programming?
    - it's not a formal term, RB was just referring to how one writes code in different contexts. With a large codebase you might be editing many different files in many different locations, while in a data analysis project it's more "linear" in the sense that you first load data, then process data, then plot results etc

- Where would the data need to be for the notebooks available to the public (the ones I open with binder)?
    - the data could in principle be anywhere where it's downloadable (from the notebook with e.g. `wget` or `curl`). But as we've discussed it can be a good idea to put datasets on e.g. Zenodo (or Figshare or other platforms)
    - This is mainly a question of where the notebook is running and what data it accesses.  Which leads to the answer above.

- I feel notebook is slower than running python script, right? and is limited by notebook storage?
  - Under the hood it is the same as typing commands in to IPython from the terminal.  Of course slight overhead with the web stuff, but if you run long stuff it's the same.
  - As an additional note, we have setup notebooks on HPC system with GPUs, so code could be run on GPUs. So it is not correct to say Notebooks are slow, but to consider the overhead as explain above.

- The Jupyter notebook can be interactive and possible to edit code, but this edit is not saved in the notebook and just a temporal thing, correct?
    - you are right: in binder it is not saved; it does not replace version control.
        - :+1:


- What is the right way to close a Jupyter notebook? I always end up having to do ctrl+c in the terminal  :D
    - I do that too, but instead of doing it repeatedly like Radovan I answer "y" when it asks if I want to shut down the server... Never had any problems.
    - Shutdown your notebook is the preferred way (but I often use ctrl+c...)

- When you add a image to a jupyter notebook, does it need to be hosted online somewhere (other than plots, of course)? Or can you "attach" the image to the notebook to be distributed somehow?
    - You can add small images to the repository (big images are a problem for git, not really for Jupyter)
    - For larger images, especially graphs and other scientifically relevant things, consider hosting on Zenodo or similar

- Can I use the notebook to run a piece of code which consists of different function calls? These functions are modules which are developed in individual notebooks. Is this an example of non linear code flow?
    - Yes. It is still what we call "linear code flow" e.g. in the notebook itself each cell is executed one after the other

- when I copied the same markdown and hit shift+ enter I got a error message, syntax error
  - Was the cell in Markdown mode?

- Is it also possible to use Mablab for the notebook?
  - For the kernel that runs code, yes.  I have done it before
  - here's one way: https://am111.readthedocs.io/en/latest/jmatlab_use.html
  - you can also use octave kernel (but it is not fully matlab).

- does the noteook also work offline?
    - Yes. when you use the procedure for the exercises you will be starting Jupyter on your local computer, althogh you access it on a webbrowser.

- When I run jupyter lab on anaconda prompt i receive a message "Jupyter' is not recognized as an internal or external command, operable program or batch file."
    - maybe try conda install jupyter to make sure it is installed?
      - Yes, indeed. It is because I am on a new environment, I guess (coderefinery).
    - So this happens when you try to use the command `jupyter-lab --no-browser`? (or just plain `jupyter-lab`)
       - just jupyter lab
    - Did you do it lower case?
      - yes but it still does not work. Strange. It worked in the  past...


- what does jupyter-lab give you as extra to opening jupyter by the command jupyter notebook in the terminal? Is it just a slightly different interface?
  - Different interface to the same way to run Python code (IPython, or whatever, kernel).  But it is a much nicer interface

- Just a note that the pi calculation is actually explained (with a nice GIF) in the Monte Carlo method page on wikipedia. https://en.wikipedia.org/wiki/Monte_Carlo_method

- Maybe it is a good place to discuss handling the randomness for reproducibility.
  - That would be a great thing to discuss, but likely there won't be sufficient time to do it properly.

- Why is the conda environment not automatically activated when you log-in on Windows? I had to do `conda activate coderefinery`to see the environment in the terminal.
    - I think it is good thing that it is not automatically activated.Otherwise it will be always be activated without your explicit knowledge.
    - That's true, but why is it always activated on Linux then :P?
        - This may be a setting in tha .bashrc file and should be commented out. Haveing conda active when loggin is one thing and having an specific env activated is not good.
        - specific conda environment such as "coderefinery" should no be activated by default (this is not good practice)
    - At least I don't recommend it automatically activated! But it's a trade-off between easy and safe.

- What about working with big files in a notebook? Is that recommended? Or how to avoid the kernel from "hanging"?
  - Under the hood it's the same as running a Python process with whatever code, many same strategies still apply.
  - Since the kernel stays open for a long time even when you aren't using it, it is good to be careful about un-loading files or restarting, to not hold all the data in memory.

- I tried using the `%debug` magic and successfully entered debug mode. However, I cannot run any notebook cells thereafter. It seems this particular notebook cell is stuck in debug mode. How can I exit?
  - You need to run 'q' or 'quit' in the debug thing that appears, otherwise it doesn't know to return to jupyter control.
  - Nice, this worked. Thank you!
  - I think you can easily lose this, then you need to restart kernel

- There was some confusion when learners open jupyter-lab from their base conda environment versus coderefinery one. In the former case, it asks to choose the environment while in the latter it does not.

- Can you run Python and R in the same notebook (or in different notebooks but so that they can "share" variables)?
    - Yes it can be done. I think there is an example
    - here's an example: https://coderefinery.github.io/jupyter/examples/#mixing-python-and-r

- How to delete a particular cell?
    - You can right-click a cell and it will show you option to delete
    - Or click on the cell and press 'D' twice. It is faster when working with many cells
    - Thanks. Pressing D twice works perfect. But the right click did not work for me.

- what is JSON?
    - it's a data format used for many different things, including notebooks. Stands for "JavaScript Object Notation". Advantage is that it's both human and machine-readable

- How do I make sure my kernel is connected to the environment I have active? It seems that the button "Python 3" when I start my notebook is using a different env (one without matplotlib so it seems).
    - to check which python executable your notebook uses you can do
      ```python
      import sys
      print(sys.executable)
      ```
      - I get an error even with `import sys`
          - hmm, maybe there's no running kernel at all. Do you see something about kernel in the top right corner?
          - Sorry. Typo.. so, as I suspected, is firing up the wrong env. It is not starting the coderefinery env executable, but my local `/opt/miniconda3/bin/python` even though I am calling jupyter-lab from the correct conda env.

- Can you explain how you build environments, such as the coderefinery environment? I assume this is recommended to create reproducible workflows when using python/jupyter notebooks?
    - do you mean how to create the environment.yml file which specifies the packages? If so, i normally create an empty environment and then add the necessary packages to environment.yml until the project runs.
    - How to export conda environment : https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html

- Comment: before sharing a notebook, it's good to not only run all cells, but also restart the kernel and run all cells. It has happened to me for example that I have accidentally removed the definition of a variable, and then when I ran it another time I got an error, while it worked when I ran it the first time because the variable was saved.
  - :+1:

- Do we have anything like "workspace" in Jupyter where you can access de variables defined?
    - Not sure about the JupyterLab but I know VSC supports jupyter and there you can also find the workspace with all the defined variables and their values.
    - Search "Variable inspector", they exist for jupyter.  Maybe JupyterLab comes with one built-in these days?
    - there's a jupyter-lab extension for this: https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/varInspector/README.html

- Could please explain the workflow of using jupyter notebook? in my case i have folders with large result data. i do the postprossing using python scripts. should i create a notebook in folder results where i already keep the codes that i use for postprossing.
  - There are many options, it depends on what you would like.  If you already have Python scripts, then keeping notebooks with that is a good idea.

- Where is the notebook saved so it can be shared?
  - When running yourself, on your disk somewhere.  Default, look in the same directory you were in when you started the notebook.
  - You can choose the place to store notebooks when you make them, it's basically a file browser included.

- Do we have these version control things on triton (jupyter hub)?
  - Yes, and if they don't work, submit an issue and I will figure out what is wrong and fix it.

- Can you write here what's in the .gitignore regarding jupyter?
---------------------------------  - ".ipynb_checkpoints" (seen via `git status`)
      - Thanks!

- What are the settings in the terminal of Radovan? Like showing if things in the repo have changed or not? Which basrc settings does he use?
  - He might be using the "fish shell" which has some predictivie stuff. I'll look more closely and see

- How to run nbdime from CLI?
  - I think it is `jupyter nbdime`
      - Exception: Jupyter command `jupyter-nbdime` not found.
  - OK, is it `nbdiff` ?  (I'm checking now...)
      - better, yes
      - Could you add this to the instrictions page? It was not obvious...
          - `nbdime` and `nbdiff` are the correct commands
              - `nbdime diff-web` opens a nice-looking view

- How did you open terminal in Jupiter notebook?
  - New -> Terminal (something like that)
  - ![](https://i.imgur.com/MTKeDcS.png)


- Can we restore the deleted image?!
  - In a Jupyter notebook?  I'm really not sure, other than undo...


- (just for fun comment) what is the hamburger cat at the bottom of the terminal of the instructor? :smile_cat:
  - is it "Nyan Cat" ? (update: no, but probably based on it)
      - OMG (https://www.youtube.com/watch?v=QH2-TGUlwu4) :rolling_on_the_floor_laughing:
  - You can get it by clicking the wrench icon on the lower right of the HackMD editor and ticking the box "what does the red panda say", how cool is that =O
      - Which editor is it??
      - HackMD
          - :100:

- In the notebook, after initializing the git repository and committing, I tried to change the code in jupyter notebooks, and tried to commit from jupyter notebooks the new changes, but the commit button in the notebooks does not work. Why? Should I somehow add it before committing in the jupyter notebook?
    - Yes, you need to add it (stage)
      - I found it, I couldn't find the stage command, now it works, thanks :D
    - Sometimes, it still fails because git is not initialized properly in your jupyterlab terminal
      - Git was initialized properly, I just couldn't find the stage button :)

- Regarding: Add `.ipynb_checkpoints/` to `.gitignore`. I phased out for a few seconds and missed what was going on. Is .ipynb_checkpoints a blank file? I am still not totally sure what .gitignore is.
  - It's an auto-created directory that stores autosave files of the notebooks.  .gitignore is a Git file that says "Never track or warn me about these files"
     - Thanks, so how do I add .ipynb_checkpoints to .gitignore?
     - Edit .gitignore like in last weeks lessons, for example `nano .gitignore` from within the directory.
     - Create a file called .gitignore, then add the text `.ipynb_checkpoints/` to the file, then save it.

- My history of commands when creating the Git repository:
```bash
git init
git status
vi .gitignore  # here vi is my editor, I added .ipynb_checkpoints/ to be ignored
git status
git add .gitignore darts.ipynb
git status
git commit -m "saving my notebook"
jupyter-lab --no-browser
```

- Is there a way to convert .ipynb to .py?
  - You can export it, also `nbconvert` has good tools for converting formats (and export probably uses nbconvert).


## Sharing notebooks and Binder
https://coderefinery.github.io/jupyter/sharing/

- Interesting: the requirements file made with conda (`conda list -e`) has '=' instead of '=='
  - :+1:

- How we can ask inside the jupyter notebook to tell us all the versions of libs we have used?
  - Of everything installed?  You can run a shell command with '!', and for example `!pip list` to list everything installed.

- Does binder require the requirements.txt?
  - It doesn't require anything, but you'll start with just the basics.
  - Or you can use equivalent files for other languages: https://repo2docker.readthedocs.io/en/latest/config_files.html
  - here are demos for using mybinder for python, R and Julia: https://github.com/alan-turing-institute/the-turing-way/tree/master/workshops/boost-research-reproducibility-binder/workshop-presentations


- What is the "proper" way of exiting the binder notebook?
  - Hm, good question.  I've never thought of this, I have always closed and it gets automatically cleaned up after 10 minutes.
  - Same as locally. Shutdown (for jupyterlab) and "Close and halt" for "classical jupyter notebook"
- Amm, is it usual to have multiple binders for multiple branches (so one binder per branch) or do you usually only use it on the master branch only since this is the branch that is expected to be used by others?
    - Yes. you can have multiple binders for multiple branches. Typically I have a binder for the default branch and one for my development branch (so one can test it)
        - But if you create a new branch from the master (this includes the badge from the readme), doesn't this mean that the binder link will be the same on both branches? - How does it than know which branch I actually want to open? Or perhaps binder is smarter than I think it is. I guess merging is not problematic, but I believe creating branches is? I guess new binder needs to be created and Readme fixed on the new branch? I am getting this right? Confusing.

- Not sure I understand the usefulness or expected use of a Binder. You pack all the dependencies and the projet code in one place and share with others. But can the others then run this on their local drive (like cloning a repo) and having all the materials, or is this just a sort of "online simulator" of your environment? In which situations is it then useful to create a Binder?


- Any feeling about how long is the estimated life of tools like Binder/Jupyter? To illustrate, we can access hard-copy documents written in the 50-ies, will we be able to run Jupyter notebooks 50 years from now?
  - They care a lot about future reprocubility (that is one of the points of repo2docker), but to be honest I really am not too confident about this.  My hope is that the effort required to port them is not too long.
    - Example: what if computer processors change (like Mac has done several times) and the pinned version of numpy is no longer runnable because complied code doesn't work anymore?
  - If you would save a Binder to e.g. Zenodo - is it executed there or still making use of the Binder webserver?
    - zenodo doesn't run anything, so it wolud have to be binder or locally
        - Can binder projects be run locally, given everything is installed?
        - Yes, in theory it's just a repo with standard environment file formats in it.
  - Jupyter notebooks are not considered a safe format in digital preservation context, and there has been relatively little talk about them too.
    - Some stuff, e.g. https://www.dcc.ac.uk/blog/managing-computational-notebooks-overview-%E2%80%98chopportunities%E2%80%99 does exist though
  - Having software be runnable in 50 years is in general very unlikely unless active preservation work is carried out during all those years, no matter what the technology/platform is.

- What are the build logs printed at the top when binder is launched? Is this the output of the commands run to setup the computational environment that binder is trying to generate using Docker containers?
  - Yes, exactly.  Most probably come from the "repo2docker" project which is used internally.

- The binder webpage is stuck on "pushing image", keeps writing that into the logs, while starting the repository. What's happening?
  - Hm, maybe the image could be too large.  Or it got stuck somewhere.  I have noticed that sometimes yes, it can take a long time.
    - It took something like 10 mins, but now it works, although the code was so little.. I thought it would take a minute since I had 5 files in total


- Uhm, after more than 10 minutes waiting for Binder to load the simple Jupyter notebook, I got 'Failed to connect to event stream'. So, I wonder if it will manage to work on a heavier, realistic example...
  - I know it can work on larger things, sometimes there are not enough resources at a certain time.  It's a project that is still developing and basically run by volunteers (but usually works well)
        - I wish there was a way to run it on local resources.
        - It's an open-source project so you could host it yourself.
        - Or, use repo2docker as a local tool to make the Docker image, then start that on your own computer to run it (so repo2docker makes the installation step easier)

## Documentation
https://coderefinery.github.io/documentation/

Is project documentation important? Why?

- ...
- reproducibility
- yes, to be able to understand the process in the future and by others
- yes, not everything can be explain by commenting the codeain by commenting the code
- yes! so you can understand and remember the process in the future :+1:
- yes. I want to understand how a code that I wrote works later in time. :+1:
- Yes, to understand my own code later since I am forgetful
- makes code reusable by others, also can help you understand what you did and why you did it so you dreinvent the wheel" for every new project :+1:
- one tends to forget what one has done
- Yes. No matter what your comfort level is with code someone else's might be completely different and no matter how comfortable you are with it code is not actually self-documenting



How would you describe a useful documentation?
- clearly explain what the code is going to do, be simple and clear and straightforward. I like comments and to comment code in such a way that someone who has NEVER seen that line of code before could understand what it will do
- it needs to be simple enough, usually when coding, everything is clear and I concentrate on details, er even the basic environment is forgotten and the documentation is too specific and not general enough
- descriptive enough for others to understand
- short, simple, clear, complete
- Needs examples of usage for all cases( like in matlab documentation) and what the code actually does and how it does it?
- change history, what's it about, where to run and how to run it, examples
- Installation instructions, what do you need to do to get the code up and running
- Background info, step by step, indication of potential issues
- well explained, clear
- easy to find where what you wonder is explained (well structured)



How can you motivate your colleagues to contribute to the documentation?
- share code, and documentation - do others understand what I have been doing? :+1:
- I wish I knew... :+1: :+1: :+1:
- maybe having it added to the code of conduct is a good idea
    - documentation-dependent pay?
- starting template
- Maybe if you have a group you could assign each other to review code and feedback... Difficult to find time and get people engaged
- to be able to cooperate with proramming and save each others' time, also benefit to new comers to the group :+1:
- the answers to the questions they had when picking up the code will safe their future selves and others time


## Creating a checklist

https://coderefinery.github.io/documentation/wishlist/#creating-a-checklist

Let us create a wishlist for how we would like documentation to be

- Show examples with "code formatation". I feel that a word document is not enough.
- if something needs to be installed: installation instructions
- if changes are made to commonly used packages, I would like to easily find the change and reason why it was made
- Installation usage (include depenn which it was testedas testedas testedas testedas testedas testedas testedas testedas testedas testedas tested)
- code to analyze data, where to get the data, a example to run the code
- all different features have at least one example included :+1:+1
- Short, to the point, and searchable. Thought, it should be complete (do not leave important issues behind)
- Thought process in plain language :+1:
- contact option or link to references (articles, blogs, etc)
- up-to-date
- Some comments on the workflow
- versions/release; what were updated, fixed, etc. and back link to any publication if it was used in an article or more.
- a simple demo from installation to running the code
- ease of search in the document
- hyperlinks to different parts of the document, particularly important if large doc
- always plain English description and algebraic formulation, besides the code
- Information about the source (research papers/ reports) from where the code is inspired
- make documentation of arguments and options dependent on source code. E.g., like API doc
    - agree, and preferrably with a link to the corresponding source code!
        - in JAVA this doc would be exactly inside the source code
        - yeah I think read the docs and doxygen does this automatically (any language)
- 1 document only for users/non-progammers:) / not split accross several docs
    - though documenting in the code is very helpful
    - I hate if it's like a single pdf, but a single website with links in a sidebar is good

- Sadly I experience that Academia often do not take the time to write proper docs. It is only the papers that are important for next career steps.
    - i completely agree. Even software that researchers share with the world, for others to use, is often very poorly documented!



## Popular tools and solutions

https://coderefinery.github.io/documentation/tools/

- Is RST also automatically shown in github?
    - yes! You can have either README.md or README.rst
        - Without the generated style and table of contets I assume?
- Sometimes I see latest commit message in github readme, is this some automatic thing?
  - Do you have an example?  This is a good question.


# Documentation- Sphinx
https://coderefinery.github.io/documentation/sphinx/
type along first and then 15 min in breakoutrooms to play around

- How to follow an organization on github?
  - not sure it's possible. I only know how to "watch" individual repositories (which can be great learning to see how they collaborate and how they write and review code). Anybody else knows how to?
        - how to “watch” individual repositories?

- Can we use LaTex with sphinx?
  - There is a math mode that uses latex format for inline math/display equations within ReST (and thus likely MyST too).
  - It can build to a LaTeX document (I think)
     - yes it can generate latex
  - I don't know of a way to write the master documents in LaTeX

- Why sphinx is slow?! It takes some time!
  - the sphinx-quickstart? yes!
    - that is a bit surprising. Sorry, haven't seen this problem yet. If this becomes unusable, I recommend to watch it as demo.
    - What parts takes a while?  Also surprising to me.
  - For me, for small projects, it builds fast.  When it builds, it extensively cross-links documents and so on.

- How do you have nano display colors?
    - Use vim :D
    - Not a nano expert, but [stack exchange](https://askubuntu.com/questions/90013/how-do-i-enable-syntax-highlighting-in-nano) provides an answer
    - Also [askubuntu](https://askubuntu.com/questions/90013/how-do-i-enable-syntax-highlighting-in-nano#90026) (same answer actually)

- I find this hard to follow, personally, I would benefit more if we had a git project and would add documentation to that.
  - I think this is supposed to be an initial demo, and then you have more time with the exercise.  Don't worry too much.


- are the empty lines relevant in rst?
  - They separate paragraphs/sections, and are more important than in markdown.
  - One place they are important (and unexpected): before and after bullet list indention levels, like shown here
  - After section headings they are not so important

- is there any autoindentation feature that we could use?
  - My emacs has one by default, probably other editors
  - Since you will probably never write documentation from the terminal: I suggest using VS Code and RST plugin. Or Atom etc.


- why ```feature-a.rst``` is not among my files?
  - Did you make it?  We make it as part of the exercise
      - No! I though it would be there after typing it in the index.rst! Sorry!

- What does the `_` in `_<foldername>` mean ?
  - here we chose to call the target folder `_build` but we could have also chosen `build` or `target` or anything else. So there is nothing special about the `_`
  - But `_build` is a default (but you can do whatever you would like).
  - `_` is sometimes used for "ignore this/special file but don't make it a hidden file"

- Is Sphinx like Jekyll? I use Jekyll for my blog and looks very similar.
  - Same idea (static site generator), different implementation
  - Sphinx tends to be more structured and interlinked, and looks more at the semantics of the ReST more than Jekyll.

- Can I mix Sphinx construction with manual editing of html files? In other words, can I edit the html files or wil lthose changes be overweritten by Sphinx.
   - the html is considered generated so they would get overwritten. but you can insert html into rst if there is something that html can do but rst is limited at.

- Ouch too fast I lost how do you render the page???
  - `sphinx-build . _build`
  - Below is how you view it

- I get an error message "command not found: xdg-open"
    - Go to your folder (with explorer), navigate to _build and double click to open the index.html :)
        - Oh yes, of course. Thanks. Worked :) :+1:


- The error message for the too short line was:
```
    - C:\Users\..\CodeRefinery workshop\doc-example\feature-a.rst:5: WARNING: Title underline too short.

Subsection
---------

...

The HTML pages are in _build.
```
  - Thanks!


- Could we make a workflow with snakemake to automatically bpage?
  - you mean like a GitHub Action workflow to auto-build upon every push?
    - yes! Exactly :) How to best do this?
       - yes, this is how we build our lessons, example: https://github.com/coderefinery/documentation/tree/main/.github/workflows (this lesson)
       - our example is a bit more involved because we build html for each branch
       - Fancy! Thank you for the example:)
          - but you can copy paste it and it will work (we copy-paste it to new lesson projects)

- I get this error "xdg-open -build/index.html
  'xdg-open' is not recognized as an internal or external command,
  operable program or batch file.", any idea why? I have windows.
  - Yeah, it's a Linux/Mac(?) command
  - if you know where the build folder is, you can also point your browser directly to the folder (paste the folder path to the address bar) and then open `index.html` - does this work?
  - It works now, I should have used `start index.html` instead of `xdg-open index.html`.

- Can Sphinx work with Markdown?
  - Yes, there are various extensions that read it as a format.  The one `myst-parser` is most recent and unlike most others, supports Sphinx directives (forcing them into a markdown-compatible format).
  - Example: this lesson: https://github.com/coderefinery/documentation (we use MyST to parse markdown)
  - See also https://myst-parser.readthedocs.io/

- Are the recommendations for docstrings so that they get auto-rendered by sphinx into readable .rst files? E.g. I have a docstring with dictionary keys (given as 'key': description, 'key2': description with each key on a different line) but when it renders everything is on the same line
  - sphinx-apidoc converts a module into .rst tree which uses the docstrings, like other api doc tools (https://www.sphinx-doc.org/en/master/man/sphinx-apidoc.html).  Then it uses sphinx-autodoc (also built-in) to automatically import and render the docs.
      - thanks I will check this out and experiment a little

- can we use relative paths, for example to an image?
  - Yes, it basically does what you expect.

- I got the following error while trying to add the code in c: ~/GitHub/doc-example/feature-b.rst:50: WARNING: Unexpected indentation. ; the line is the one of "      printf("Hello, World!");", I just copy-pasted the code from the exercise
  - Probably needs some blank lines before/after things, or maybe some indention
    - adding a blank line before the indented line worked! Thanks!

- is there faster way to modify sphinx documentation in a kind of real-time maybe with a GUI? I meant without having to recompile and reload the html pages manually
  - sphinx-autobuild is quite nice, local webserver to preview every time you save.
  - I don't know of any WYSIWYG GUIs (but maybe it's best to see the text anyway)

- We could navigate from `feature-a` page to `index` or `feature-b` directly in the html, but not from feature-b content to feature-a content. Both were accessible from the index.
  - Some themes (like the documentation lesson one) have a sidebar table of contents.
      - sidebar was present, full options for feature-a... but not for feature-b (which was missing feature-a)
  - Hm, I guess we need to play with the themes some.  I've been able to do a lot, but it's up to the theme what is possible.

- I never got the items to show...
    - DId it show any error messages during build?

- Where is the conf.py file? (Final paragraph in Exercise 1: https://coderefinery.github.io/documentation/sphinx/)
    - in the base directory (doc-example in the exercise case)
        - :+1:

- Are github pages GDPR compliant?
    - The answer naturally depends on what you write there. Just hosting a basic site with documentation doesn't sound like GDPR relevant stuff (but I'm no lawyer)
    - As with anything in GitHub, the web UI (and cloning the repo) shows who has edited the repository. You'll need legal help to know if that's a register though.
    - https://docs.github.com/en/github/site-policy/github-privacy-statement shares GDPR-relevant stuff about GitHub account data etc
    - For free accounts they are public, so... what does GDPR compliant mean? (since that question usually means "is it confidential")  I wouldn't use them for anything that you don't intend to share with the whole world.  For visitors to the page, see above

- If the Sphinx page is deployed in GitHub, then it does not show versions at the left bottom (of the menu)?
  - The version/format selector is basically a ReadTheDocs thing (but you could re-create this yourself somehow if you wanted)
      - Wow, thanks! ... so is it always better to have a version information somewhere in a separate file or as a part of headers etc.?
      - Depends on your needs, but for many of my projects I would have readme say basic info, and if I need an old version I can get it/ build it with git as I need.  Bigger projects need more.
          - :+1:

## Feedback

One aspect that was particularly good today which we should keep:
- The interactions kept the course very dynamic and interesting.
    - +1, the co-teaching is great! +1 +1 +1
- The pace of Samantha was very good +1 +1
- The type alongs are very helpful for getting key points together and then doing more complex building in the breakout rooms. Plus it it more fun to be interactive in the main session as well. It felt very smooth today that way.
- Breakroom discussion not only exercise
- Breakout room discussions were very interesting
- Good pace and good material
- Nice with the back and forth between the teachers - interactive +1 +1
- The documentation for this session was very good, with lots of external examples and alternatives.
- the dialogue between instructors is a good thing
- The speakers were very clear
- The last part from Radovan should find room in the main lesson: it's cool and useful!
    - it originally was, but the typealong took a bit more time than expected
    - Yes but we also use more and more github actions for similar results (and with no ads).

One thing we should improve/change/remove in future:
- gentler intro to sphinx?
    - do you have specific suggestion on how to make the intro more gentle?
        - start with a nice example of documentation on read-the-docs (that exceeds Github readme), then show how you get there? However, I feel that documentation with sphinx is overkill for many "researcher script to analyze data" projects.
        - thanks for the suggestion, that would indeed have helped. Will note for next time. And agree that it is very often overkill, but some funding bodies and journals start requiring 'more than readme'. The point was to show that there is tools around to do these in case you ever have to :)
        - that's a good point and it surely was useful to get a demo! I was aware of read-the-docs before but not sphinx. Perhaps a comparison of different markdown tools for documentation and their applications could be useful? Is there any online resource that guides you to suitable documentation options for different complexity levels?
        - good suggestion, please make an issue here: https://github.com/coderefinery/documentation/issues (or I will later if you dont want to ;) ) with these suggestions, before every worshop (at latest) we work through the issues to update the material, so things do not get forgotten
            - I need to move on to the next meeting now but can try to remember tomorrow
            - :+1:
        - I do not know about such website, but would be great if it existed
- The jupyter notebook use with nbdime for version control was partly rushed
- after so many already knew jupyter we could have reduced the time on this and maybe spent more time on Sphinx. I feel the last part was 'yea and there you have this as well'
    - For the ones not familiar with Jupyter yet, that part was very useful. That's the issue with different levels/backgrounds. +1
        - I agree ^ also liked that they gave the advanced users other examples to work with
- Compared with last week content, where we build on the topic of VC, this week has many tools and topics that feel a bit disconnected.
  - Yes, very true.  Week 1 is more of a deep dive, week 2 is more a summary of many tools.  We could clarify this more.
  - However, tools are not disconnected. It is related to Open Science but I agree that we do not make it very obvious. Definitely something to improve.



