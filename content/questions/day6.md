+++
template = "page-with-toc.html"
+++

# Questions and notes from workshop day 6


## Icebreaker for day 6

### What do you know now that you wish someone had taught you when you started studies/research/work?

We may tweet some of these answers, of course anonymized.

- Only fools don't ask questions / asking questions is not foolish but essential in research. :+1: :+1: :+1:
- First make your code work, only then make it good or fast (if necessary).
- Making a logical folder/data structure can save a lot of time. :+1:
- Git. :+1: :+1: :+1: 
- Focus more on methods and less on theory. :+1: 
- Save the editable version AND the scripts with the data for the figures.
- Avoiding "clever" code. The simpler the code the better. :+1:
- To not worry so much about code speed. I have a feeling I spend more human time trying to understand code than CPU time running the code.
- Save all results, even the ones that don't seem necessary.
- It is always worth it to spend time on version control, testing and documentation. Start early! :100: 
- Write a paper when you have a result (really, no-one told me...).
- define proper processes to be followed: folder structure, version control, etc.
- To properly document the code. +1 :+1: :+1:
- Spend time on making a good reserach design early on this will save you a lot of time and make things easier along the way.
- Make all the notes! Tomorrow you will not remember anything.:+1: :+1: :+1:
  - Great! I also started doing that. Notes for everything. 
- Don't be autodestructive. Nobody knows everything and it is ok to say you do not have the answer.
- That data management is really important!
- Most old professors are totally biased by obsolete methods: there is much more than what they think to know... :100: 
- Comment, Comment, Comment! There are never too many comments in a code.
- Never forget readme files. :+1: 
- Python, and coding in general, taught by actual computer engineers in dedicated lessons, not merely by physicists with poor programming practices.
- Sharing your knowledge with others via teaching or mentoring is an excellent way to learn yourself and benefits others at the same time.


## Questions on earlier day's topics

- I have difficulties finding the links to the previous HackMD pages (I always need to go to the emails). Perhaps, it should be nice to put links in https://coderefinery.github.io/2021-05-10-workshop/ or any centralized page that could play the role of an index. :100: 
  - Thanks for suggestion. Indeed we should collect all resources in one place and cross-reference them. I have moved this good suggestion to our "lessons learned" (on chat) so that we improve this for the future. We wish we could also put zoom link on the workshop page but we are worried about zoom-bombing.

- We have been using Git Bash and Anaconda Prompt. Some instructions only work on one or the other platform. Why? Can this be fixed? How? In some cases this has been a limitation in following the lections and it slowed us down (surely it slowed me). [Windows question]
    - If the setup is fully correct, everything included in the CodeRefinery materials will work in both Git Bash and Anaconda Prompts on Windows. Please provide more details what didn't work and we can concentrate on it when improving troubleshooting guide 
       - pip for example did not work in Git

## Software testing
https://coderefinery.github.io/testing/

### Motivation

- Direct comparison could also provide different results across different OSes, deployment environments right? 
  - It is an important thing to consider and test for.

- I totally don't get the point of this test. Seems trivial. Why would the function NOT return the expeted result when you feed it the right input?
  - Well, it's a first demonstration.
  - And what happens when it gets more and more complex over time?  We'll see a basic principle is always have more than one place to verify result.
      - OK now I get this, this is interesting, thanks. So if somebody updates / expands the function the test should still return the same result for a specific input. Right!
      - And finally, when I make the function the first time, I want to run it once to verify.  I've learned, why not take that one sample, put it in test instead of console, and let it run over and over again?  Gets a lot more useful with big code
  - Also sometimes one person's trivial is other person's non-trivial. But of course I agree that this is a trivial example. But often a function can be "obviously" correct or wrong for the original developer but it may be a lot less obvious for a contributor or the new person joining a project.

- What is Regression Testing ?
  - Check that new behavior (or results) are same as old (even if you don't exactly verify either are "correct").

- For "when to make tests", one of my philosophies is "if I have to test manually, I may as well make it automatic".  It can also make interface easier, since you can use all the test setups.
  - Also automating it makes it easier to remember how to do the test steps. Great for new people joining project: they can look up the testing scripts and from that can deduce how to install and test (if not documented elsewhere).

- Integration/Regression tests work also as examples of usage.
  - Great point. They can be great "documentation" which is sometimes more up-to-date than the actual documentation :-) :+1:


### Concepts

- How do we test functions whose output is unknown to us? I.e. we know what they are supposed to do but don't know whether the result is correct or not (as in calculating a high-dimensional gradient).
  - Good question. A general advice is to try to calculate by other means. Perhaps a different algorithm or approach. Of course this is not always possible.
  
  - To me, it's the same philosophical question when making the code in the first place.  I would first test that it runs without failures.  Are there any corner-cases when you know the result ($p=0$ makes empty results)?  Are the results same as your first run?  Can I implement the same thing in a simpler way to compare (even if I don't know if either are scientifically correct)?
  - I like to approach it like this: how do you verify yourself whether it does what you expect? Then try to express this in writing, then try to express this in script/code. Now you have a test.
  - Ammm, tests are not supposed to be super complicated. They are suppsed to check the basic functionality. Thus computing a high dimensional gradient of a constant and some other (analytically known simple results) would be sufficient. If it works for the simple tractable cases, it should work for the more complex too.

  - If you cannot predict the output exactly (numerical issue, randomness) you could also at least test some general sanity checks, e.g. that the dimension of the gradient is correct or that the returned type matched the expected type.
  - For numerical algorithms, I would also get the result with a computer algebra system (Mathematica, Maple) and check that the output of my code matches that.

- For C++ for example, do I need to include the test tools to my package? What if others use different test tool?
    - Tests are supposed to test your own package and are independent on how your package is used by others.


- No example for each one?!
  - "each one" refers to what precisely? 
      - Different tests, like Unite Tests, Integration Tests and etc.
  - examples for each type of test maybe?
    - Good suggestion. We should add examples for each of these concepts. Also pull requests and suggestions very welcome (there is always room for improvement and it's a process ...)


- Any way to test the response to time-dependent results? Time is difficult to reproduce on different platforms.
  - In this case I would test functionality on many platforms but the timing only on one or few, where it's somehow well defined, and I would test with some tolerance. but inded it is tricky.
  - "fake time" for your tests. Here we discuss unit testing (mostly).
      - Actually I meant "run time" rather than time as input/argument.
          - Can you elaborate? I still usually make my code believe there are specific run time conditions.
              - True, but if you want to test a function that does something in a given time, then the time has to be actual run time. The fake time will by-pass the function that I want to test. I guess a better design would remove this need, somehow.
    - Hmm! I would like to hear more about this. How does this work?

- If you cannot test everything, it's always good to test the part(s) of the code you just changed.
- I'd always recommend testing before merging to the main/master branch.
- Can we use ```pytest``` in jupyter notebook?
    - Yes.
    - You can also run shell commands in the notebook if you add `!` before the command, e.g. `!pytest -v example.py`

## Exercise: Testing locally ##
https://coderefinery.github.io/testing/pytest/

- Interestingly, we found out that assert add(0.2,0.3) == 0.5 passes the test, but add(0.1,0.2) == 0.3 fails :D
  - Numerical accuracy problems!  Floating point numbers have many of these things :+1: 
  - that's because 0.5 is exactly representable as floating point number. 
  - This (and the lower "accuracy problems" section may be good starting points: <https://en.wikipedia.org/wiki/Floating-point_arithmetic#Representable_numbers,_conversion_and_rounding>
  - addition is still a nice operation in floating point arithmetic, because you can actually exactly represent the rounding error as a floating point number (you can google error-free transformations if you are interested in knowing more) 
  - https://docs.python.org/3/tutorial/floatingpoint.html `round(0.1 + 0.2, 10) == round(0.3, 10)` (should help)

- But add(0.2,0.3) == 0.5 passes
    - I would say you were lucky not to have floating-point rounding errors (or rather python took care of them for you in the background). For larger floats, and for multiple addition operators, the error can easily build up, making it a good practice to have tests that allow for the error.
    - I know ;) And 0.1+0.2 does fail, just surprising ;)
       - yes, some combinations work fortunately/unfortunately. This exercise has been carefully designed to fail with 0.1+0.2
       - :D
    - more info and workaround: https://docs.pytest.org/en/6.2.x/reference.html#pytest-approx

- Why do we need pytest (or similar testing frameworks) if I can achieve the same by inserting asserts/isinstance into the code?
  - Inline testing is good for safety, but not really enough to run full models on test data with known outputs.
  - Also this would then test at runtime and runtime may take many minutes or even hours but with a testing framework we have the chance to test functions in isolation which often only takes seconds. plus we get the flexibility to run some tests selectively. but still good idea to also use assertions.

- We were having fun with `approx` and were trying out e.g. approx(add(0.2+0.3)) == approx(0.5), and my question is basically stated below by the next person...
  - Great! I think it's very useful for future to see this.

- We discussed a bit the approx funciton. What is exactly its output? We are now realying on an external funciton for our test but we don't understand exactly what the function does.
  - OK. Let's maybe first think how we would do this if we didn't have the approx function: then you could check `assert abs(result - expected_result) < 1.0e-14` (adjusting the tolerance). Also the approx function from pytest has an in-built tolerance which can be changed.

- the HTML code below has messed up code highlighting, anyone have a solution? fixed with `:::`
    - Fix by adding 'julia' after \\```"
:::spoiler Julia implementation of `isapprox`
```julia
function isapprox(x::Number, y::Number;
                  atol::Real=0, rtol::Real=rtoldefault(x,y,atol),
                  nans::Bool=false, norm::Function=abs)
    x == y || (isfinite(x) && isfinite(y) && norm(x-y) <= max(atol, rtol*max(norm(x), norm(y)))) || (nans && isnan(x) && isnan(y))
end
```
:::




## Automated testing 
https://coderefinery.github.io/testing/continuous-integration/

- If you need external data to test the code, i.e. downloading a ML set, do you have to set something specific for Github actions?
  - gh-actions is like a normal system, it could download data (will it use too much bandwidth?).  Or for small data, include it in the repo?
     - Inside the gh-actions "workflow" you can download data or use data from the same repo. There is a limit on data amount (which I don't remember how much it is).

- Should we included a license for the new repo not? :)? 
  - Great suggestion!
  - Which one would be nice for this example? MIT? 
     - Yes, MIT or BSD are permissive and only thing they require is attribution.

- How do we *a priori* know which one is the correct GH action to pick?
  - Good question! It requires some investigation (or asking someone).  Usually there is a popular or official one, but since anyone can make one, there are many options.
  - Also it can be good to check how similar projects on GitHub do it and look for inspiration (provided license allows, but it often does).

- Can I use the testing also when I have one python file including all my functions, while I have a main python file where I call the functions?
  - Yes, they can all be in one file and later, once the file grows too big, you can always split it up.
      - So the testing doesn't really care where the functions are?
          - You first `import` the functions you want to test. Regard the python file in which you write the `test_bla()` functions as a regular python script. It has access only to the stuff that you `import`.

- I guess this Github actions allows to run some custom scripts too, right? Like a custom script checking the code style, for example?
  - Yes, anything you want.
  - Many of these have already been packaged into actions, but I am often creating my own stuff, too.

- The actions are performed at every "commit" or "push"? If we commit on local, nothing should happen in the GitHub repo, I guess, until we push. 
  - Typically at every push. But you can also define them to only run on merge or only on release. You can even define to run them every hour or every week.
  - you can also add an option to run the action manually on demand. This will create a button on GitHub which you can press whenever you want, e.g. after a commit.

- What is the "__pycache__" folder created by pytest? I guess it should go into .gitignore
  - Yes, it should be ignored. Generated folder where Python stores some compiled bytecode intermediates. I think this is what used to be `*.pyc` files (which should also be ignored).
      - How do I add that to the .gitignore? Can you comment on that, pls?
         - create a new file called `.gitignore`, then in that file add a line `__pycache__`
                 - example: https://github.com/bast/huge/blob/master/.gitignore 
             - Thanks!

- Wouldn't Github run the test upon pushing the new branch? Do we need to necessarily run pytest locally?
  - Not necessarily, we could also let GitHub test the new branch and then later we can decide whether we want to create a pull request or adjust before we create a pull request. Depends on definition on when GH actions are run. Many projects make them run on pull request or any push to default branch.
  - Thanks. Can the instructor briefly highlight where to configure running tests on other branches?
     - example: https://github.com/bast/runtest/blob/ee520544c80b24a3f13dd255ba896e262c75f68a/.github/workflows/test.yml#L3-L7
    - Thanks
    
- Github sends an email in case of action failure: so cool! And useful!
  - Up to the moment when you debug some problem with 50 "debug" commits :-) but I agree this is useful.
  - I think you can also turn email notifications off if you want.

- This type along exercise on the tests on GitHub was really great as we have seen the entire workflow of using git with remote, branches, etc, all the things learnt so far. Really great exercise to show how in practice things work. :+1: :+1: :+1: :+1: :+1: :+1:

- Why is it called a workflow? 
  - Excellent question :-) not to be confused with workflows we talked about. I like to think of it as "recipe".

- Now I `git checkout main` in my local repo and I `git pull` from remote. If I `git branch` I can still see the bugfix branch in the local repo, even though we have deleted it in the remote. Why's that?
    - Good point. What happens when you remove a branch is that the pointer to the commit is removed. The whole set of commits remain.
        - What is suggested behaviour then, should I delete the local branch (how)? Thanks.
           - Yes, you can do that as you do not need it anymore.
           - Yes, after you have merged a branch, you can delete it both on GitHub and locally. It's actulaly good practice, since you may have hundreds of stale branches otherwise.

- What if my function GETS/PUTS/POSTS data to database? Is reasonable to attack the database on every push?
  - You could set up and later "tear down" a small test database as part of the testing. So it does not have to use the "real" database for automated testing.
      - Are there advantages to this over the mockup files?

- Deleting the branch where the bugfixing is done doesn't delete the local branch on pulling. Is there a reason for that?
    - You need to: `git fetch -p`. The `-p` or `--prune` argument will update the local repo of remote branches.
    - The reason for this is that GitHub doesn't know anything about your local branch. This is by design ("distributed" version control).

## Exercise in breakout rooms
https://coderefinery.github.io/testing/test-design/

- Example for pytest fixtures (useful to avoid code dupication when you need to do similar setup in many tests)
  - https://docs.pytest.org/en/6.2.x/fixture.html#quick-example


## Modular code development
https://coderefinery.github.io/modular-type-along/

Questions: https://coderefinery.github.io/modular-type-along/questions/


**What does “modular code development” mean for you?**

- Separate long codes into modules, make it more clear and structured, especially for those repeated ones, write it into functions and modules. :+1: :+1: :+1:
- Not sure. I would appreciate an explanation. :+1: :+1:
- One code for one function: when anybody needs that functionality, is there and transferable to a different context.
- Better overview, more structured.
- Each module defined during design is developed separately and builds separately from the other modules. Then modules have to be "connected" to build together.
- What does it mean modular since I do not know how it will turn out in the end? or who will use it? or what kind of questions will be answered in the future?
- Write functions that do one thing well. :+1: :+1:
- Collecting standalone parts of codes together that are meaningful. Not too short, not too long.
- Divide the code into smaller units.

- I have no idea honeslty, but sounds like you shuold make smaller pieces of code (modules) and then put them together. Like when you play with LEGO and have many bricks and then you build something with those bricks... 
- Copy-paste-ability: if I take a function/module/library and put it into my other project, it will still work.
- Is there an end-life for the code?


**What best practices can you recommend to arrive at well structured, modular code in your favourite programming language?**

- Name methods with understandable names (no "myFunction()"). :+1:
- (Python) Have environments for each project working on, one .py file for functions, imports, analysis. Descriptive names in files, functions. :+1: 
- (Julia) Use environments and develop methods and procedures as packages that are called in scripts that 'uses' the package. Also test frequently and make sure new parts are as pure as they can be.  

- (General) Make your functions as atomic as possible, i.e., make them do a single specific thing
    - Doesn't it make the code slow?!
    - It is a trade off between code sustainability vs performance at the end of the day, also dependes on the programming language. It is conveninent to split a function named calculate() into three functions named add(), suctract() and multiply() that explicitly explains the different operations within calculate() function.

- Max 1 or 2 input arguments for functions as much as posisble, the less input arguments the better. Then the functions are easier to test.
-  (Julia) use multiple dispatch to write generic code.


**Do you design a new code project on paper before coding? Discuss pros and cons.**

- We try to see which parts of the project are usable in general and do those parts well an so that they are not too project specific.
- Yes, I do. Start with concept, sketches, algebraic formulation. Not sure one can start coding right away? :+1: :+1: 
- Depends, to get a better overview what needs to be done, but I don't do it always. 
- No, I usually directly write and test codes on computer. Or write anything on computer from the very begining. Save time, no need to move it from paper to computer, but maybe not that good for thinking and structure.
- Usually I implement some algebraic algorithms since I come from Mathematics, so I just start coding and I adjust it. If I didn't have an algorithm sketch though, I would write it down before.
- I sometimes make a sketch in the paper. But I do not have a structured practice.
- Always in my own mind!
- Yes, there is always a model "on paper", be it already a set of equations or a sketch/drawing of how it should be. :+1:



**Do you build your code top-down or bottom-up? Discuss pros and cons.**
- What does top-down and  bottom-up means here? :+1: 
- Top-down, which is very useful when using JupyterLab, new things can be tested below things which already work. :+1:
- Not clear what this means in this context :+1:
- I would describe my approach as top-down, I commonly try to sketch the problem and the approach on paper and think about the major steps before filling them with life/code.
- Not sure this is about bottom-up or top-down but usually writing it linear (compile one line after another), and then splitting it into functions and calling the functions instead (don't know if this makes sense, can't really explain - I think this is actually what you have done with the final exercise on plotting temperatures, you started on a single piece of code (many lines ) and then you splitted it into functions).
- Starting usually to first have a look how the data looks like (get a big picture), then go into more details, use more variables.
- I usually do it top-down: first the general things (that will not work) and then fill the gaps to make the whole thing work. :+1: 
- A mix of both! I fill every part that is more intuitive for me, first; then I try to design the other parts. Sometimes it is not very intuitive to me to do, completely, desing in top-down fashion or bottom-up fashion.


**Would you prefer your code to be 2x slower if it was easier to read it?**
- Ideally it would be nice to have different versions, depending on the audiences. Even in different languages (e.g. low efficiency but very readable code in GNU MathProg for readability by non-experts and high efficiency code in Python, for more experts). Problem with this is how one keeps the versions up to date with each others??? Or whether one should anyway?
    - I think it would be better to have on fast version well documented and commented :+1: 
        - Are you suggesting then that non-experts with ideas could contribute to the algebraic formulation and the coders then implement? Cause it's important for outreach to empower also non-coders to contribute (in some way).
            - Yes, I'd say so. Would say the algebraic formulation shold be part of the above mentioned good documentation. Then also non-coders can think and develope new ideas for equations. If using github one could submit such ideas as issues. And if the algebraic idea is there it is probably rather easy for experienced coders to implemnt it. Otherwise you need to implement it two, three, or more times.
- Not really.. I mean, I would like to have it a fast as I can, and document each step on what's going on in order to make it more readable. :+1: :+1:
- For research-purpose code it is probably best to have it undestandable rather than spare a line of code :+1:
- In my utopia the code is fast (not necessarily easy to read) but well documented so that you understand what some complex parts does.  

- Sometimes faster is also easier to read. This is what I try to persue.

- Why having to choose? The idea of Julia is exactly to fix this so-called  "two languages problem" :+1: 

- In most projects speed is really not an issue. If you are doing high performance computing, you may need to improve _some_ parts of the code for performance.

- Readability is very subjective. Expert coders think what their write is very readable but... to less expert ones it is often not. And they don't write comments to things they think are trivial (but are not to others). So readable code is ALSO code that is readable to those less expert than you... I think. So my preference is for code with more comments and simpler functions and simple structure rather than something completely nested and relying on a lot of alien functions (that are not explained). 


### Additional questions
- How do we go about modular code development if we are starting somewhere fresh, but there exists some previous code version which serves as a base (and this is not modular)?
    - In an ideal world, you would be able to improve the existing code. But that's often a fantasy 🦄🌈
    - Been there... and the old code was not editable (license). I threated it as a big single module.
    - When you touch some part of the code, perhaps separate it as a module/function/method and add tests for it.

- Environment help to pack dependencies. But how do environments help with modulatity if (for what I understand) modularity is in the code I type, and not on the dependencies?
     
- Some people like to collect functions in a script at the beginning/in the end of a script, others split them into several files that are then called from a master script (commonly done e.g. in R projects). What do you recommend? Should functions in external files come with a test?

- Are there any recommendations/tips to **test for modularity**?
    - if you can extract modules from the code without things breaking (testing useful)
        - reusability achieved: modular*
    - while reading: what knowledge is assumed you have of states outside of the function / class / module?
        - none: modular*
        - none, even of how contained functions are implemented: polite code. Very readable.
    - while testing: mock functions can be used to test functional dependence of preceding code.
        - (*) Dependencies can be hidden. Asynchronous code (API calls, raised events, child processes, external requests) may mutate a global state invisible to your code. When code depends on calling functions in a certain sequence, exceptions may occurr when you replace individual functions with mock functions (a function reproducing the same effects (output / mutations / events) by other means than a mimicked function). Mock functions may reveal implicit dependencies by causing exceptions when they replace the function they mimick. It may also be informative to test with variations of effects.
    - while writing: a nice way to get started is to design code in abstraction layers. If the lowest layer is the source code in function bodies and the highest layer is the API of your module layers inbetween could gradually reflect the layers' specific knowledge. Higher layers represent use case knowledge, while lower layers introduce specific knowledge to the software engineering (algorithms, design patterns) used. This concept is often referred to as polite code. Polite function- and variable naming does not force readers to read lower level code first to understand what is happening in the current layer. 
    - above works best when: 
        - every function implements only a single functionality
        - functions are packaged into object-oriented programming structures like modules and classes
     
- What is the importance of the distinction between pure and impure functions?
  - Both have their place, but it tends that the more pure functions you have,  easier it is to understand/test your code → better long-term.
  - But obviously sometimes you need side-effects.

- Actually a Jupyter question: can I see the values assigned to a variable somewhere?
  - Yes, search "variable inspector".  Maybe it is built-in to the latest version?


## Our example that we will try to improve together
https://coderefinery.github.io/modular-type-along/lesson/

We also have one possible solution (but there are so many different improvements possible) here: https://coderefinery.github.io/modular-type-along/instructor-guide/

Please give us tips!

- How did you get the file?!
    - https://github.com/coderefinery/modular-type-along/blob/master/data/temperatures.csv
        - Yes, but was it like with ```wget link```?
          - click on "raw", then you land at https://raw.githubusercontent.com/coderefinery/modular-type-along/master/data/temperatures.csv, then `wget https://raw.githubusercontent.com/coderefinery/modular-type-along/master/data/temperatures.csv`

- Make it generic for the number of measurements. It should work for any number of measurements.

- Please use `f'{num_measurements}.png'` instead of `str(...)+'.png'`
  - Yes, indeed this is nicer but I didn't want to derail the demonstration but f-strings are a very nice and compact way to print with variables.

- Use `kwargs` to let the user pass arbitrary options to `pd.read_csv`
  - Hmm! Yes! This could make it very flexible and we could unpack the keyword arguments inside or pass them on.

- Three functions: read_data (with the above-mentioned reading of the number of entries), compute_mean, plot. :+1:
  - Great suggestion to split it up so that functions themselves become reusable and also we abstract ("hide") internals away.

- Names on the axes of the plot please. 
  - and title!
    - thanks! working on it :+1: 

- I guess "if ain't broken, don't fix it" is not a good answer here, right :) (just kidding)

- I would definitely stay on this notebook until I don't get a plot I am happy with. How do you plot from terminal? To me the idea of a notebook is that you can experiment a lot so I would stay there as long as possible and then "clean up" and move some of the stuff to a .py file (if needed at all).
    - In this example, you could use `plt.show()` to give you a window with the plot to just quickly look at, or `plt.savefig("my_awesome_plot.png")` to save the plot to a file (for embedding in a paper etc)
        - Now that I read the code, the example code already saves the plot... So you could just open the file "25.png" in the directory you ran the program in.
        - They actually have done just as I suggested. They stayed on the notebook until they got a nice plot and then went to the .py file. So I think we agree.

- In the function maybe have another input in the functions like variable to make it more generic, instead of temperature. 
   - Thanks! Hopefully we implemented this.

- Can we at all have pytest in Jupyter notebook? I mean, running these pytests from outside Jupyter, like in github CI
    - `!pytest -v example.py` (running a shell command inside the notebook)
        - True, but can this be done in a github workflow?
            - Yes: https://nbdev.fast.ai/.

- Maybe define a more generic start point. As in not necessarily from the 1st entry to nth. We could start from qth entry and say we want to plot n temperatures.
  - Good point! Sorry I missed this during lesson but this could be a nice generalization.

- "We would assume to have Pandas dataframe": should usability be increased by specifying the data type that is expected by a function? Otherwise the function would be assuming a datatype that is not declared, so another user will have to look inside the function to understand what are the assumptions. Declaring data types allows encapsulation, I think.
  - Great question, will come back to it -> type annotation

- In the compute_statistics function body 'temperatures' should be replaced by 'data'. :+1:
  - Thanks!

- Test: prevent the num_measurements being higher than 721 (max number of measurements). Even though, if we put a num_measurements higher than 721, it works .... can you briefly explain how's that so?
  - Thanks, I will bring it up.

- Clear plot
  - Good catch!

- For better readability, specify the type of inputs and output (e.g., `def read_data (filename: str, number_of_measurements: int) -> float`)
  - Thanks! also connects to suggestion about how to specify that this is a pandas Dataframe or not.

- Please make a list for all temperatures above a certain threshold 
  - That would be interesting. especially for Nordics :-)

- Instead of nbconvert you could use the `jupytext` extension for Jupyter then you can connect .ipynb with a plain script .py Then it also updates automatically either if you make changes to the ipynb or the py file.
    - Nice! One can also just export to .py file from JupyterLab interface, I think that runs nbconvert under the hood.

- pytest only finds files called `test_`, and then only the functions in those files beginning with `test`
   - But one can call it together with a file name and also configure testing to gather all functions in a package.

- Perhaps we could seperate the test function from our source code; I mean perhaps we could create another file `test_temprature.py` and put the test function in it.
  - Indeed many project prefer to collect all test functions in a separate file or even separate folder. This has pros and cons (as everything).

- This is a good example how code is developped. Also, please point out that the flexivility and modularity takes time. It is always a trade between requirements, time and resources. It is nice to have vs. It is needed.
  - Great point which I sadly overlooked. It's a trade-off and it's good to stop somewhere and not make it too perfect. Also avoiding https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it

- Questions (rather than suggestions): Maybe misunderstanding, but making codes modular sounds/looks a bit contradictory to making code pure. Is it so? Or is it in one sense better to keep it pure and testable?
  - Great point. All code cannot be pure because at some place we need to read input and generate some output. But when modularizing code we try to move the I/O "upwards" in the code, to the "outside" of the code if that makes sense. To keep internal functions pure if we can and to deal with I/O on the "outer" shell of the code. In this sense modularization does not make the code impure but it can indeed increase the "surface area" of the code.
 - Thanks, I think this explanation is very good. Probably it is a good idea to summarize the whole workshop in the sense of the ideal whole workflow to connect all the lessons together? Like reproducibility with the entire environment as condition to make it reproducible vs. modularize/generalize code as function to make it work in a robust situation for reusability?

- Add some #comments on the .py file? To explain others what each function does, what is happening in each block of code, etc. E.g. before `@click.`... you can add something like `# Here a function to do blablabal...`. 
  - Great suggestion which I sadly missed. Either that or adding docstrings.

- Any specific reasons behind using `click` for receiving command line arguments instead of using something like `argparser`?
   - Just personal preference.
   - Ok, I just wondered if it provides any other functionality.
   - `Click` does have some nice features though: it for example handles files nicely (it will alert the user if they give a non-existing file etc), but these might or might not be of use to your project.
       - More info at https://click.palletsprojects.com/en/7.x/why/
   - Thanks.
   - Any other library would be fine, too (optparse, argparse, doctopt, ...). One nice thing about `click` is that it is good at composable command line interfaces when you want to combine several tools which each has their own CLI.
   
- Use `if __name__ == "__main__":` before calling the `main()`
  - :+1:
  - This would be the standard way of wrapping the call to `main()` - Thanks! Good suggestion.

- Will you make this script (temperature_analysis.py) available somewhere, pls?
  - one solution is here: https://coderefinery.github.io/modular-type-along/instructor-guide/


## Concluding remarks
https://github.com/coderefinery/workshop-outro/blob/master/README.md


## Feedback for the workshop

*One aspect that was particularly good today which we should keep:*
- :+1: for the half-day schedule. :+1: :+1: :+1:
- The break every hour is very nice and useful for us to fresh our mind and always be able to follow it.
- Co-teaching :+1: :+1: :+1: :+1: :+1: :+1::+1::+1:
    - and **pair live coding**, wow! Respect Anne & Radovan :+1: :+1: :+1: :+1: :+1: :+1: :+1: :+1::+1: :+1:
    - I could watch this all day! :+1: Scope for a CodeRefinery live coding streaming channel?
        - this exists! https://researchsoftwarehour.github.io/ :+1:
- Nice that the workshop was distributed over several days.
- Possibility to use Twitch recording in case one couldn't join the lesson during the set up time. (nice to catch-up)
  - These videos will also become available on YouTube, once we have had time to edit the broadcasts: https://www.youtube.com/channel/UC47aupE7HKGduAjXKt1Gwrg :+1: :+1: :+1:
- Daily summary email with the necessary link will make it nice to go back in a couple of weeks. :+1: :+1:
- the last part from Anne and Radovan is probably the best possible ending: I loved it! :+1: :+1: :+1: :+1:
- The format of the workshop is excellent with lots of interactions through HackMD and breakout rooms, freedom to ask questions :+1:
- Clearly the most enjoyable multiday online-event I have attended in a long time. You did an excellent job trying to avoid Zoom fatigue. :+1:
- Learnt so many new things here, life changing!!
- "Please don't prepare too much" - that makes it slower and easier to follow.
- Thanks for facilitating participation of teams with their own learners. The scaling up of the workshop was very helpful in creating more impact.


*One thing we should improve/change/remove in future:*
- Spacing the workshop as M/W/F so that there is time to absorb the material afterwards. Half-day schedule is excellent but sometimes one needs more time. Also, because the workshop(s) are announced early, one can block the calendar accordingly.
- Explain the connection between the modules more clearly (week 2). State explicitely what expert level is the main target audience and what you can gain if this does not include you (often it is still useful to get a demo and be aware of the existence of a tool, even if you are not going to actively use it). :+1: 
- The confirmation of participation was sent super late to me and it was difficult to clear the schedule at such a short notice. 
    - Thank you for joining in the workshop despite the late confirmation email! We really appreciate. We had so much problems with no-shows before and struggle with making it possible to offer seats to those who need as much as possible. Still doing try and error, so it is really great if you could suggest any way to improve the situation as well. But we will try to send the confirmation as reasonable time as possible.
- Is this session's recording going to be available? (modular code development). It'd be good to be able to re-watch all this reasoning, it's very useful. :+1: 
    - Yes, for 14 days on Twitch, later on YouTube.
    - Website has open PR that will link to the playlist.
- It would maybe be nice to use Jupyter for a bit longer in the Modular Dev session, with `!pytest -v *`, and a workflow using the (!)`jupyter nbconvert --to python <filename.ipynb>`. Even better with commits of working versions & seeing diff (ideally also with CI testing, maybe local hook). This would amalgamate all the topics together and demo the Jupyter Lab plugins in real life.
    - Then the only bonus to add would be running it in a snakemake workflow 😮
    - And generate doc website from python docstrings 😁

- There was some disappointment from the stream watchers of not having a place to ask questions. I suppose this would be quite hard to implement, but maybe not impossible? (e.g. HackMD for logged-in accounts only that could be blocked if abused, if hackMD supports that...)
  - HackMD is available for registered stream viewers: I occassionally linked it there and it should have also been in the channel description.  I guess we need to emphasize this more!
    - But also for those who watch later!
      - Ah.	If you would like to ask questions later, our CodeRefinery chat is probably the best option (we have been wanting to develop this more...)

- Global dominance plan: 2 workshops per year, one mornings UTC, one afternoons UTC. But would it technically work with BORs for 300-400 live participants? 😮 Main problem perhaps with HackMD, it was already so-so now.
  - We don't actually need everyone in one meeting: one idea we have is a pure-livestream workshop, then there are multiple Zoom meetings each with their own breakout rooms arrangement.  HackMD may still limit, though.

- I would maybe add a bit more hands-on time, something like half-half maybe (at the end of the day, what we really remember, is what we did on our own).


*Anything we're missing in our material? Ideas for a new lesson?*
- Some tips for smart setup of terminals and editors. I understand why you use Nano for examples, but "real" coders would usally tweek their set-up a bit. Emacs and vim is not easy to start with if you are a beginner. What about recommending some functionalities for modern editors? Like autocompletion and automatic indentation, ssh-log in, etc.
- Usage of IDE's to have a more smooth workflow and not so many different programs are needed, but that could just mean to have the entire course with one IDE. -> better workflow 
    - And will avoid the usage of different editor set-up.
- Update the git lessons with the more descriptive new git commands.
  - Great idea. Does this refer to the `git switch` and `git checkout` part, or do you have additional suggestions?
  - I only saw it with `git switch` and `git checkout`, but there might be some more hidden. :+1:
    - thanks!

- If possible, please announce the workshop dates early on, very difficult to find 6 days in a schedule with such short notice.
  - Good suggestion. We need to plan this long in advance to give learners and exercise leads the chance to attend.

- Suggestion for more robust time managment and organization: the schedule seems to be a bit too volatile and the instructors are often not sure what comes next and leaving some silence here and there (waiting from an answer from somebody that does not seem to be defined). Maybe an assigned "chair" in charge of keeping the dialogue active might be useful. :+1: :+1:

- Is there a link to the `README.md` with *"where to go from here"*, which is shown now?
    - https://github.com/coderefinery/workshop-outro#readme 
          - :+1: 

- A compiled version of all the material discussed in the last 6 days. Something that is easy to navigate using the browser.
    - You can find all lesson material from the workshops page schedule: https://coderefinery.github.io/2021-05-10-workshop/

- Thanks very much to all! It was a great learning experience. I was almost completely illiterate in Git and collaborative coding and I was able to follow along very easily (most times) and understand all the key principles. Will need to go back to all the steps for applying the concepts, hard to remember all if you do not apply every day. But the key steps and ideas are very clear. :100: :+1:
  - While reading this comment being written, I felt like somebody was writing things out of my mind :D :+1: 
  - :+1:

- Can we download all material from the workshop? 
  - it's currently not easy to download as PDF but we plan to 1) make lessons citable and 2) put them on Zenodo with a DOI to have a PDF-package of lessons. right now the best way to visit them is via web. they won't disappear but they may evolve. all of that is here: https://github.com/coderefinery/
  - What format would you want to use to download them?
      - I'm not the author of this question, but I'd like hyperlinked HTML download, for each release==workshop. Not so easy to recreate hyperlinked HTMLs locally from checkedout commits.
  
