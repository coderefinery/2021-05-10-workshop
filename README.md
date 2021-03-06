# CodeRefinery workshop webpage

This repository is a template to set up webpages for CodeRefinery
workshops, and has coordination of roles.



## Quick reference

- Workshop dates: 2021 May 10-12 (Mon-Wed), 18-20 (Tue-Thu), 9:00-12:30 CEST
- Installation help and helper onboarding: 2021 May 5th and 6th, 12:00-14:00 CEST
- [Workshop website](https://coderefinery.github.io/2021-05-10-workshop/)
- [Workshop repository](https://github.com/coderefinery/2021-05-10-workshop)
- [Indico page](https://indico.neic.no/event/178) 
### List of HackMD
- [Coordination HackMD](https://hackmd.io/@coderefinery/coordination-2021-05-10-crws): Coordination works happen here. Please visit it and write your name for the roles etc. of your interest and availability for this workshop!
- [CR 2021 Exercise overview](https://hackmd.io/@coderefinery/CR_May21_Exercises): Please update your plan for exercise, approximate time to run the exercise sessions and how long they will be, as well as plan for breaks here.
- [Exercise leader hackmd May '21](https://hackmd.io/@coderefinery/exerciseleader_may21/edit)
- [Exercise leader onboarding](https://hackmd.io/@coderefinery/exerciseleaderonboarding)
### Expert Helper/Exercise Leader coordination sheet
- [Helper availability overview and exercise plan](https://docs.google.com/spreadsheets/d/1NeIRs7c8br0xjcxxETNd__19JtfEERe-KFd9JUjP0wU/edit#gid=0)


## How to generate your workshop repository

To use it, follow these instructions:
- Click the green "Use this template" button.
- Select owner of the new repository and repository name. The name should be
  "year-month-date-place", e.g. `2019-10-16-stockholm` or `2019-10-16-online`.
- Click "Create repository from template".
- You will now be redirected to the new repository.
- On "Settings" enable "GitHub Pages" from `gh-pages` as "Source".


### How to customize this template after you have created the repository

- Adapt `config.toml`:
  - adapt `base_url` (it should contain a trailing slash)
  - adapt `title`
  - adapt settings below `[extra]`
- Adapt schedule in `content/_index.md`


### How this template works

This template is based on the [Zola](https://www.getzola.org/) static site engine.

To install Zola, follow:
- https://www.getzola.org/documentation/getting-started/installation/
- https://snapcraft.io/zola can be used for system that are not supported by default
- But you can also download the binary directly from [here](https://github.com/getzola/zola/releases)

Check that Zola is installed with `$ zola --version`.


#### Local preview

```
$ zola serve --open
```
This will open in your default browser a rendered version of the template.
