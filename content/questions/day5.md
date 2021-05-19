+++
template = "page-with-toc.html"
+++

# Questions and notes from workshop day 5


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



