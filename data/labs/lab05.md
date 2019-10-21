# Lab #5 - Working With Models
COMP4711 - BCIT/DGPT - Fall 2019

## Lab Goals

The purpose of this lab is to help you explore and practice some of the 
model aspects of CodeIgniter. 

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
and your branch will be `origin master`. You can just push to that
branch, without creating a pull request.
We will return to shared repos, and gitflow workflow, with the assignments. 

On github, fork the [lab 5 starter project](https://github.com/jedi-academy/dgpt4711lab05).


## The App

The starter project is a super simple travel destinations webapp,
with some pre-made controllers and ready-made views. It even has a homepage.

It is missing a model to work with. Last week, you used a model with mock data,
while this week you will build the model "properly".

### Our Model

We will be building this during lab, using the same data as last week (but not mocked).

The mock data includes the names of some image files, which you 
will find inside the `public/images` folder.

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

## Step 0

Fork and then clone the lab starter. Everything you do will be done in your fork,
and you won't need any pull requests to the starter repo.

Locally, inside your project, `git status` should show  on you "develop"
branch, with nothing new.

`git remote -v` should show "origin" aliased to your fork.

Run the app, either inside Apache or from the command line if that is
easier: `php spark server` from your project root.

You should see the homepage, but both links on it will be broken.

## Step 1

Build your model data file, in `writable/data`, with an appropriate file extension

## Step 2

Build your model, eg. `app/Models/Places.php`

Remember:

- namespace the class
- "use" the simple model class appropriate for your type of data
- your class "extends" that one

## Step 3

Add  model properties:

- `$origin` - the path to your data file, `WRITEPATH . '/data/xxx'`, where "xxx"
    is your data filename
- `$keyField` - the "column" name of your key or identifier, case-sensitive
- `$validationRules` - empty array for now; we will be adding those next week.

## Step 4

Run your app, and get it working, with our assistance.

## Notes

The `Simple\Models` module is very experimental, and I will likely update it
while the lab is in progress.
Whenever I do that, I will post a "RESYNCH LAB05" message on our wechat channel.

To resynch, make sure that you have the starter lab aliased ("upstream").
If not:

    git remote add upstream https://github.com/jedi-academy/dgpt4711lab05.git

Each resynching:

    # save & commit your current work
    git checkout master
    git pull upstream master
    git push origin master
    git checkout develop
    git merge master
    git push origin develop

This will merge any changes into your project.

You may need to resolve merge conflicts!
