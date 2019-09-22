# Lab #3 - Framework Introduction
COMP4711 - BCIT/DGPT - Fall 2019

## Lab Goals

This week, you will meet CodeIgniter4.

This is an individual lab, with each student ending up with their own repository.


## Lab Submission

Submit a readme *text* file, or a submission comment, to the lab dropbox. 
It should contain a link to your github repository. 

Due: this Sunday at 17:30

A marking rubric will be attached to the lab 3 dropboxes.


# The Lab

Make a github repository to use for this lab, `comp4711lab03`, in your account.  
This won't be a shared repository, but one used exclusively by you.
We will return to shared repos, and gitflow workflow, with the assignments. 
Because it is not shared, you can work on the `master` branch.

You will need to use your XAMPP setup from week 1, or else install [PHP7.2](https://www.php.net/) on your system.

Additionally, you will need the [Composer](https://getcomposer.org/) program.

Install CodeIgniter4 on your system using the [appstarter](https://codeigniter4.github.io/userguide/installation/installing_composer.html#app-starter).
I suggest the following command, inside the `htdocs` folder of your XAMPP/apache2:

    composer create-project codeigniter4/appstarter comp4711lab03 -s rc

You can "run" your webapp by mapping `comp4711.local` to have `comp4711lab03/public` as its document root,
and then viewing `comp4711.local` in your browser, using the port you configured Apache to run on.

Alternately, once the framework has been installed, you can run the webapp from the command line, inside
the project folder, with 

    php spark serve --port=XXXX

where XXXX is the port you want to use. 
You would then access the in your browser with `localhost:XXXX`.

Associate this project folder with your github repository:

    cd comp4711lab03
    git init
    git remote add origin YOUR-GITHUB-PROJECT-CLONING-URL
    git add .
    git commit -S -m "Setup project"
    git push origin master

**Remember to add & commit your local changes at the end of each of the three pages in the tutorial.**

Complete the [CodeIgniter4 Tutorial](https://codeigniter4.github.io/userguide/tutorial/index.html) in the user guide.

Modify the news view so that the title shows your name, eg "Jim's News archive" instead of just "News archive".

Add, commit & push the completed project.

**Note**: there is a Chinese translation of the user guide, but the 
[tutorial section](https://codeigniter-chinese.github.io/codeigniter4-user-guide/tutorial/index.html#) looks like
an earlier version of the tutorial, and it isn't exactly the same as the "official" one in English.
