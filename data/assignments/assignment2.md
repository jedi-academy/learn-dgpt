# Assignment #2 - Heroes: the Awakening
COMP4711 - BCIT/DGPT - Fall 2019


## Assignments Overview

The purpose of the assignments, collectively, is to have you apply the techniques 
from the lessons and tutorials, in a context that will be helpful to you
in the future. 

Based on our earlier experience with team work, this will be individual
contributions to a shared webapp.

## Categories

You have your categories:

- Zhenhua - (video game) creators
- Weida - hiphop
- Mingxi - Crossfire players
- Bincong - movie stars
- Li - Asian historical heroes
- Wozhao - Chinese TV stars
- Chengyue - football
- Hao Gong - Chinese anime stars
- Yingzheng -  basketball
- Zixi Zhang - comic stars


## Goals for This Assignment

Each student, for their category, will create a real "simple"  model for their heores
data; and a ResourcePresenter controller to present the model data as a table, or to show
the data for a designated hero; and the view templates to support these.

This should sound **very similar** to labs 5 & 6!

## Recipe

Here is a checklist for completing the assignment:

- This assignment will build on the previoius one, i.e. it will  use the same repo,
You need real data for your resources (eg MySQL database), with non-trivial data 
    (4-8 fields per record, 6-12 records in all)
- For each resource, have a presenter routing to a resource presenter...

You dont need all of the presenter methods implemented,
just those to support the first few views...

- index(), producing a generated table, with each row containing a link to
    that row's hero...
- show(id), producing a non-editable view of the designated hero, with somewhere 
    an obvious link to ...
- edit(id), producing an editable view of the designated hero; instead of 
    planning a file uload ability, provide a dropdown of the hero image
    names found in "your" area

- Follow good gitflow workflow
- Cleanup
    - readme, commented code!, cruft gone, all synched

User guide reference: https://codeigniter4.github.io/userguide/incoming/restful.html

## Late Addition

Per class discussion, we will add the editing ability to your heroes app!

We left off before with the individual heros presented using an HTML form.
After the last lab, we can take that through to validation and updating.

Add validation rules for your hero data, and add the form handling like we 
did in lab.

## Assignment submission

Submit a note to the assignment dropbox, with your github username and
assigned category.

Due date: Sunday, Dec 1, 17:30
