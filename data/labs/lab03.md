# Lab #3 - Framework Introduction
COMP4711 - BCIT/DGPT - Fall 2019

## Lab Goals

This week, you will meet CodeIgniter4.

This is an individual lab, with each student ending up with their own repository.


## Lab Submission

Submit a readme *text* file, or a submission comment, to the lab dropbox. 
It should contain your github username. I can find the repositories from
the starter project forks.

Due: this Sunday at 17:30

A marking rubric will be attached to the lab 3 dropboxes.


# The Lab

This is not a collaborative lab, but an individual one.
You will be working directly with your own repository,
and your branch will be `origin master`. You can just push to that
branch, without creating a pull request.
We will return to shared repos, and gitflow workflow, with the assignments. 

On github, fork the [lab 3 starter project](https://github.com/jedi-academy/dgpt4711lab03).

You will need to use your XAMPP setup from week 1, or else install [PHP7.2](https://www.php.net/) on your system.

Additionally, you will need the [Composer](https://getcomposer.org/) program.

The starter project has CodeIgniter 4 installed, but you will need to update
the dependencies once you clone it locally:

    composer update

You can "run" your webapp by mapping `comp4711.local` to have `comp4711lab03/public` as its document root,
and then viewing `comp4711.local` in your browser, using the port you configured Apache to run on.

Alternately, once the framework has been installed, you can run the webapp from the command line, inside
the project folder, with 

    php spark serve --port=XXXX

where XXXX is the port you want to use. 
You would then access the in your browser with `localhost:XXXX`.

Test that you have successfully set the projet up by "running" it. 
You should see the CodeIgniter 4 default app welcome page.

**Remember to add,commit and push your local changes at the end of each of the three pages in the tutorial.**

Complete the [CodeIgniter4 Tutorial](https://codeigniter4.github.io/userguide/tutorial/index.html) in the user guide.

Once you have completed the tutorial, modify the news view so that the 
title shows your name, eg "Jim's News archive" instead of just "News archive".

Add, commit & push the completed project.

**Note**: there is a Chinese translation of the user guide, but the 
[tutorial section](https://codeigniter-chinese.github.io/codeigniter4-user-guide/tutorial/index.html#) looks like
an earlier version of the tutorial, and it isn't exactly the same as the "official" one in English.
