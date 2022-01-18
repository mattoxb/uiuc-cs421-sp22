---
title: Setting up Your Git Repository
linktitle: Setting up Git
date: 2021-06-25
draft: false
menu: getting-started
type: book
weight: 3
---

We will use `git` throughout this semester as the version control system for MPs
and labs. Specifically, we will be using git for two functions:

- Distribution of provided code.
- Distribution of grades.

You will not use `git` for turning things in; you will use Prairielearn for that.

While we do not require that you learn and use good version control practices,
we cannot stress enough how useful a good version control system can be when
you follow good practices. For example:

- Always use a good commit message which describes the changes in the commit.
- Never check in broken code. (This is more important when working in groups,
  but still good practice.)
- Commit regularly and frequently. For example, commit when you're done writing
  a function. This allows both simpler commit messages and greater confidence in
  the repository.

We will assume that you know how to use the basic `git` commands, but we don't expect
you to be an expert.

## Setting up git

There are two repositories that you'll be interacting with as part of this course:

1. Your personal course repository
2. The release repository (`_release`)

In general, we will release code to `_release` and you will merge it into your
repository to get the initial code.  You'll then complete the MP or lab in your
personal repository.  While we won't use the repository for grading, it does
make it easy for us to look at your files if you are trying to get help on
something, and it also makes a good backup of your work.

To get everything set up, there are certain things you will need to setup once
the entire time you're in the course, things you need to setup once per computer
you use, and things you need to do once per MP.

## Course Setup (necessary only once for the entire semester)

The first time you're accessing the CS 421 repository this semester, you will need to have a CS 421 repository set up for you.  This process is simple:

1. If you don't have one already, create an account at [github.com](https://github.com).
2. Visit this [magic repository creator](https://edu.cs.illinois.edu/create-ghe-repo/sp22-cs421/)
3. It will ask you to join the `illinois-cs-coursework` group.
4. You will get a repository with a URL like `https://github.com/illinois-cs-coursework/sp22_cs421_NETID`, where
   `NETID` is your actual netid.

## Workspace Setup (necessary only once per computer/directory you use)

### Create a clone of your repository

To setup your computer to work on an MP or a lab, you will need to clone your
repository onto your computer.

To clone your repository, run `git clone`:

``` bash
git clone https://github.com/illios-cs-coursework/sp22_cs421_NETID.git cs421git
```

you can replace **cs421git** with whatever folder you want created.  For example, you may want to call your folder just "cs421" or "cs421work" or anything else.

{{< callout note >}}
 On some systems, git (and other command line programs) will not display anything when you type your password. This is expected: type your password as normal, and then hit enter.
{{< /callout >}}

Finally, move into the directory you just cloned:
``` bash
cd cs421git
```

### Add the `_release` repository as a remote

To connect to the release repository, you need to add a remote:

``` bash
git remote add release https://github-dev.cs.illinois.edu/sp22_cs421_release.git
```

You're now all set to begin to work on an assignment! :)

## Assignment Setup (necessary only once per assignment)

To retrieve the latest assignments for CS 421, you need to `fetch` and `merge`
the `_release` repository into your repository.  You can do this with two
commands:

``` bash
git fetch release
git merge release/MP_NAME -m "Merging release repository"
```

Don't type `MP_NAME` literally here; on each lab we will provide the proper name to use.

If `git` happens to complain about unrelated histories, use this command:

``` bash
git merge release/MP_NAME --allow-unrelated-histories
```

## Assignment Submission (do this often!)

Well.. you aren't actually submitting anything.  But a remote `git` repository
serves as a wonderful backup tool.  If something goes wrong and you delete your
local copy, you can always restore it from the remote repository.

Every time you reach a milestone and want to checkpoint your work, you will need
to `add`, `commit`, and `push` your work to your git repository. 
Here are the commands to do that, assuming you are in your CS 421 repository:

``` bash
git add -u
git commit -m "file submission"
git push origin master
```

Sites like [GitHub](https://github.com) are migrating away from naming the main
branch `master`, preferring instead to call it `main` instead.  In that case, type
`git push origin main`.

### Verify your Submission

You can always verify your "submission" by visiting
https://github.com/ and viewing the files in your repository.

## Grades

To submit grade reports to you, we will create a branch in your repository
called `grades`.  In that branch will be a directory called, you guessed it,
`grades`, and usually a file `grade-report.txt`.  It will be a few weeks before
the first one shows up, so don't worry if it's not there yet.  We will post to
campuswire when that happens.

It is better if you do *not* try to switch into that branch.  It sometimes happens
that a student does this and then modifies the grade report file.  This will break 
the script that sends out grade reports, and you will no longer get updates until
the course staff can fix it.

To view your grades, do a `git fetch` followed by a `git merge grades` to merge
the files into your main branch.
