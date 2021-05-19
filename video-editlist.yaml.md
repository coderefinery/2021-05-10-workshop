# 2021 may videos

Help us edit videos!
- Find the link to the video archive (in zulip)
- Look below to see what is unfinished
- Watch the video, and use the examples to fill out new segments
- Make sure the input file is what you expect
- Using the Twitch input file is in principle better right now
- **Make sure audience video is not in stream (anything besides (CR) people**.  Voice is OK.  **If people are visible and you can't cut it out, make a clear note of it.**
- Special cases
  - Need to combine muliple different files into one?  Ask for the syntax
  - Does the syntax not express something you need?  Make it up and we will adjust syntax to match what you need.
- If you can record key points for the table of contents, e.g. "45:10: 02 Basics", write it down somehow and we can turn it into a table of contents.
- Related Git issue: https://github.com/coderefinery/2021-05-10-workshop/issues/45

## Day 1

```yaml

# This input will be used for all segments until redefined
- input: cr-2021may-day1-obs.mov

# welcome
- output: day1-welcome.mp4
  time:
    - 12:20, 31:14

# Git-intro day 1
- output: day1-git-intro-1.mp4
  time:
    - 31:14, 38:13      # Lesson (Sabry)
    # cut to remove YouTube video
    - 41:28, 1:04:45    # Lesson (Sabry)
    # going to breakout rooms
    - 1:18:22, 1:28:27  # Exercise for breakout room (Sabry)
    # break
    - 1:41:40, 2:24:07  # Lesson (Sabry and Diana)
    # going to breakout rooms
    - 2:28:44, 2:36:38  # Exercise for breakout room (Diana)
    # break
    - 2:53:20, 3:20:53  # Lesson (Sabry)
    - 31:14: Overview of the day
    - 33:25: Motivation to version control
    - 41:28: Real-life repository examples
    - 48:35: Basics of version control
    - 1:18:22: "Exercise: record changes"
    - 1:51:13: "Summary so far: basic git commands"
    - 1:52:02: Using the staging area
    - 1:58:45: Interactive committing
    - 2:28:44: "Exercise: Using the staging area"
    - 2:53:56: Ignoring things with .gitignore
    - 2:57:54: Undoing things
    - 3:13:32: Summary of the day
    - 3:20:01: What to expect in the next lesson
```


## Day 2

TODO: all, note the new format

```yaml

# Use Twitch for day 2
- input: cr-2021may-day2-twitch.mp4

- output: day2-intro.mp4
  time:
    - start: 11:30
    - end: 24:40

# Git-intro day 2
#- output: day2-git-intro-2.mp4
#  time:
#    - start: ??:??      # Lesson (Sabry)
#    - 1:45: Title of section
#    - 5:45: Title of Section
#    - : Branching and Merging
#    - : Conflict resolution
#    - : Sharing repositories online
#    - : Inspecting history
#    - end: XX:??
```

## Day 3
TODO: all

```yaml

- input: cr-2021may-day3-git-collab-twitch.mp4
- output: day3-intro.mp4
  time:
    - start: ???
    - end: ???
    - start: ???
    - end: ???

- output: day3-git-collab.mp4
  time:
    - start: ???
    - end: ???
    - start: ???
    - end: ???

```

## Day 4

TODO: reproducible research

```yaml
- input: cr-2021may-day4-obs.mkv

- output: day4-intro.mp4
  time:
    - ????: Intro

#- output: day4-reproducible-research.mp4
#  time:
#    - ?, 1:05:10   # first session before break, exclude meta
#    - X: "Introduction"
#    - ?: "Motivation"
#    - before 30:00: "Organizing your projects"
#    - 32:??: "Begin an example"
#    - 39:20: "Dependencies"
#    - 51:40: "Type-along: Conda environment"
#    - 1:16:30, 1:35:45?
#    - 1:18:05: "Containers"
#    - 1:23:00: "Recording computational steps"
#    - 1:25:00: "Exercise preparation: Snakemake"
#
#    - 1:38:40*, ?
#    - 1:38:40*: "Snakemake exercise demo"
#
#    - 1:55:25, 2:00:40
#    - 1:55:25: "Sharing research data"
#
#    - 2:06:00*, 2:08:08
#    - 2:06:00*: Instructor discussion
#
#    - 2:13:00, 15:16:30*
#    - 2:13:00: Fair principles

- output: day4-social-coding.mp4
  time:
    - 2:26:55, 2:31:15
    - 2:26:55: Intro
    - 2:27:50: Social Coding
    # Break for answering questions
    - 2:34:55, 3:01:00
    - 2:58:10: "Exercise: how to make a repository more reusable?"
    - 3:07:45, 3:12:20
    #- 3:16:14-17??  Learner in video
    - cover: {start: "3:16:14", end: "3:16:17", w: 840, h: 300, x: 360}
    - 3:14:25, 3:17:20
    - 3:22:05, 3:38:30
    - 3:22:05: Licensing
    - 3:35:30: Practical recommendations
    - 3:37:05: Software citation

- output: day4-outro.mp4
  time:
    - 3:38:30, 3:39:42
```

## day 5

All done!

```yaml

- input: cr-2021may-day5-obs.mkv

- output: day5-intro.mp4
  time:
    - 5:00, 6:10 # talking about icebreaker
    - 8:25, 9:05
    - 13:15, 20:50     #
    - 15:00: Jupyter getting started
- output: day5-jupyter.mp4
  time:
    - cover: {begin: "41:29", end: "41:35", w: 840, h: 300, x: 360}
    - 20:50, 1:00:30   # episode, Exercise as a demo
    - 1:01:20, 1:18:24         # After exercise
    - 1:32:50, 1:49:50
                          # 1:15:45 Thor in video
    - 1:53:25, 1:55:20
    - 20:50: Motivation, pitfalls, best practices
    # 32:50 Sabry appears
    - 37:41: Interface
    # Diana name at 44:30
    - 42:10: "Exercise: Darts and the interface"
    - 50:00: "Demo: Darts exercise plus explanation"
    - 1:01:20: Post-exercise discussion
    - 1:11:20: Git and notebooks
    - 1:32:50: Binder and sharing notebooks

- output: day5-documentation.mp4
  time:
    - 1:59:55, 2:26:25
    - 2:27:00, 2:40:05
    - 2:40:55, 2:44:00
    # 2:30:00 Stefan in video
    # 2:38:00 - 29:31 Johan in stream
    - 2:53:50, 3:21:15
    - 3:22:25, 3:45:00
    - 3:47:13, 4:02:54

    - 2:00:00: Intro
    - 2:01:00: Motivation
    - 2:14:20: Popular tools
    - 2:21:20: Readme files
    - 2:23:55: "Exercise: Readme files"
    - 2:53:50: Sphinx documentation
    - 2:57:30: Sphinx type-along
    - 3:19:40: Sphinx exercise
    - 3:22:25: Sphinx exercise demo
    - 3:36:45: What comes next
    - 3:39:00: ReadTheDocs summary
    - 3:40:50: Github Pages summary
    - 3:42:40: Summary, end of day
    - 4:47:13: ReadTheDocs demo

```

## Day 6