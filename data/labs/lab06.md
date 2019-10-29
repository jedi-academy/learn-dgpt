# Lab #6 - Generated Places
COMP4711 - BCIT/DGPT - Fall 2019

## Lab Goals

The purpose of this lab is to give you a taste of some view generation.

This is an individual lab, with each student ending up with their own repository.


## Lab Submission

Submit a readme *text* file, or a submission comment, to the lab dropbox. 
It should contain your github username. I can find the repositories from
the starter project forks.

Due: this Sunday at 17:30

A marking rubric will be attached to the dropbox.

# The Lab:

This is not a collaborative lab, but an individual one.
You will be working directly with your own repository,
and your branch will be `origin develop`. You can just push to that
branch, without creating a pull request.
We will return to shared repos, and gitflow workflow, with the assignments. 

You are to continue working with the repository that you started last week, namely
the Lab 5 Starter.


## The App

I bet you can see whats coming today :)

You have existing controllers and a model (from last week).
Now we get to ework on the views!
### The Views

Three views are provided, in `app/Views`:

- `home.php` is the homepage, with a link that will not
    work until the model is in place.
- `placeslist` is a page showing all of the travel
    destinations, with substitution fields that your
    controller will provide.
- `oneplace` is a page showing all of the data for a single
    travel destination, with an image link that we will provide
    a controller for.

## Step 1

Split the "placeslist" display into three strips.

## Step 2

Replace the simple list of places from "placeslist" with a generated table.
Do not use the place image name.

## Step 3

Replace the "oneplace" view with a constructed form for editing, for the
chosen place. You may show the place's image aboce the form (not part of it).

For now, the target of a "submit" button should be "#", i.e. "do nothing".
We will add that next.


# And?

Run your app, and get it working as best you can, with our assistance.

## Notes

The `Simple\Models` module is very experimental, and I will likely update it
while the lab is in progress.
Whenever I do that, I will post a "RESYNCH LAB05" message on our wechat channel.

To resynch, make sure that you have the starter lab aliased ("upstream").
If not:

    git remote add upstream https://github.com/jedi-academy/dgpt4711lab05.git

Each resynching:

    # save & commit your current work, and then...
    git checkout master
    git pull upstream master
    git push origin master
    git checkout develop
    git merge master
    git push origin develop

This will merge any changes into your project.

You may need to resolve merge conflicts!
