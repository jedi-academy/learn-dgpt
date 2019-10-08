# Assignment #1 - Heroes: the Beginning
COMP4711 - BCIT/DGPT - Fall 2019

## Assignments Overview

The purpose of the assignments, collectively, is to have you apply the techniques 
from the lessons and tutorials.Each will add more capabilities to the previous.

Based on our earlier experience with team work, this will be individual
contributions to a shared webapp.

Each student will have a category (a competitive sport or performing art),
in which they profile six of their heroes. Choose a category that you
are familiar with, and have some personal heroes for. Everyone will
have a unique category.

## Goals for This Assignment

Each student, for their category, will create a mock model for their heores
data; a controller to present the model data as a table, or to show
the data for a designated hero; and the view templates to support these.

This should sound **very similar** to lab 4!

## Workflow

We will use collaborative gitflow for this.

I will provide a [team repository](https://github.com/jedi-academy/dgptheroes), with master and develop branches.
At the moment, it is only a shell, and I will update it as we go. You can fork it,
and then synchronize with it while working on the assignment.

You will fork that, and prepare your work locally with feature branches
based on develop. Your work will get integrated through pull requests,
to merge one of your feature branches with the team's develop branch.
All of your commits are to be GPG-signed.

## Allowed Folders to Use

Each of you will have subfolders in `App/Controllers`, `App/Models` and `App/Views`; named
after your category. That is where your work should go.
For instance, the "baking" category would have its models inside `app/Models/baking/`.

There will be some common configuration data in `app/Config/App.php`,
and you may need to add a configuration file for subsequent assignments;
we shall see.

Additionally, and public files, such as images, should go into
`public/images/xxx`, where xxx is your category name.
You should also put there a 100x100 PNG icon, named after your category.

## Your Category Data

Your mock data should include at least eight fields:

- an identifier
- the name of your hero
- the city or country your hero lives in
- the name of a 240x360 image of them

and then four additional fields that are relevant to your category
and different from other categories (eg team, position, specialty,
favorite food, ???). At least two of these fields must be different
from everyone else's.

## Assignment submission

Submit a note to the assignment dropbox, with your github username and
assigned category.

Due date: Sunday, Oct 20, 17:30
