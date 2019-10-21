# Assignment #1 Notes - Heroes: the Beginning
COMP4711 - BCIT/DGPT - Fall 2019

## Introduction

I thought my directions were clear, but we can see that many of you are having trouble following them.

This note to the assignment is an attempt to be as clear as possible about the components you need to make, 
and about the process I intended you to use,

## Categories

The list below shows the category names that the heroes webapp uses:

- Zhenhua - creators
- Weida - hiphop
- Mingxi - crossfire 
- Bincong - movies
- Li - history
- Wozhao - tvstars
- Chengyue - football
- Hao Gong - anime
- Yingzheng -  basketball
- Zixi Zhang - comics


## Branching!

You should use a different branch for each component or group of them, so that
you can deal with smaller problems at a time.

## Starting point

You have forked the [team repository](https://github.com/jedi-academy/dgptheroes)
into your account, and cloned it locally.

Remember to add a remote for it:

    git remote add upstream https://github.com/jedi-academy/dgpt4711heroes.git

Once you have done this, `origin` will refer to your repo on github, and
`upstream` will refer to the team one.

*In the writeup following, I will use the category **fruit**.
You should subsitute that with your category name.*

## Part 1 - icon

At your git bash shell, make sure you are in "develop" and then
create a new branch to work with for your icon.

    git checkout develop
    git checkout -b icon

Make a new folder for your images: `public/images/fruit`.

Find or make a 100x100 PNG file, named the same as your category, eg.
`fruit,png`.  This should go inside the folder you made just above.

Add & commit the changes.

    git add .
    git commmit -S -m "Add my icon"

Push this branch to your repo.

    git push origin icon

On github, create a pull request from your "icon" branch to the
team "develop branch.

There may be problems ... I will note them in comments to your pull request.

Once you have fixed them, then re-add & commit the changes.

    git add .
    git commit -S -m "appropriate message here"

and

    git push origin icon

You don't have to create a new branch to fix things. Pushing another
commit to the branch has github go through all of its checks again,
and send me an email.

Once your "icon" branch has been merged, you should sqitch to your "develop" branch and synchronize:

    git checkout develop
    git pull upstream develop
    git push origin develop

## Important branching notes

If we can;t get to your PR in a timely fashion, and you want to work on another part,
then make sure you switch back to "develop" before creating a branch for the other
part.

**DO NOT** start working on a new part while you are still in your "develop" branch.

## Part 2 - controller

Your controller is go go inside `app/Controllers/fruit`, **BUT** CodeiIgniter's
routing is going to want to capitalize that, so should we.
Being the only controller in that folder, it should be the default one, namely Home.php.

So, your controller will be `app/Controllers/Fruit/Home.php`.

You need to get the namespace stuff correct for CI to find the controller properly,
and your should start with something like...

    <?php
    namespace App\Controllers\Fruit;
    use App\Controllers\BaseController;

    class Home extends BaseController
    {...}


Follow the same process as for part 1.

## Part 3 - Model

Follow the same process, with your model going into
`app/Models/Fruit/xxx.php`, where :xxx: is the name of your controller.


## Part 4 - Views

Same process as above, except with the
view folders inside `app/Views/fruit`;


## Part 5 - Get it Working

You may have problems debugging this, once it is all together.
It will be hard to test at all until it is.

If you get stuck, message me on wechat, and I will take a look at
your repo and advise you on how best to proceed!

Jim
