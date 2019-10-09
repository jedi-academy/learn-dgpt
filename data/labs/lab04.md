# Lab #4 - Working With Controllers & Routing
COMP4711 - BCIT/DGPT - Fall 2019

**Update: I have corrected Step 3, and added a note to it.

## Lab Goals

The purpose of this lab is to help you explore and practice some of the controller 
strategies and routing techniques for CodeIgniter. 

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

On github, fork the [lab 4 starter project](https://github.com/jedi-academy/dgpt4711lab04).

You will need to use your XAMPP setup from week 1, or else install [PHP7.2](https://www.php.net/) on your system.
If you have XAMPP, you can run the app outside of the Apache server by opening
a command prompt, giving it the command "C;\Bitnami\wampstack-7.2.16-0\use_wampstack.bat".
That will open yet another command prompt, but one which is aware of PHP.

## The App

The starter project is a super simple travel destinations webapp,
with a ready-made model and ready-made views. It even has a homepage.

It is missing three controllers, that you will provide, and some
routing configuration to glue everything together.

### Mock models

A mock model is one with data provided internally as an array.
It is used for testing only.

Our mock model, `app/Models/Places.php`, provides a few
"records" for some travel destinations, and two methods to retrieve all
of the records or just a specific one.

The mock data includes the names of some image files, which you 
will find inside the `writable/data` folder.

### The Views

Three views are provided, in `app/Views`:

- `home.php` is the homepage, with two links that will not
    work until you supply the apporpriate controllers.
- `placeslist` is a page showing all of the travel
    destinations, with substitution fields that your
    controller will provide.
- `oneplace` is a page showing all of the data for a single
    travel destination, with an image link that we will provide
    a controller for.

## Step 0

Run the app, either inside Apache or from the command line if that is
easier: `php spark server --port=4711` from your project root.

You should see the homepage, but both links on it will be broken.

## Step 1

The first link, to the list of destinations, is for `/travel`.
This suggests a controller, `app/Controllers/Travel.php`,
which will have an `index()` method to handle that request.

    <?php
    namespace App\Controllers;

    class Travel extends BaseController
    {
        public function index()
        {
        }
    }

The body of the `index()` method needs to connect to our model,
retrieve the complete set of records, and then pass them on to the appropriate view.

    // connect to the model
    $places = new \App\Models\Places();
    // retrieve all the records
    $records = $places->findAll();

If you examine the `placeslist` view, you can see that it expects a
substitution field `records`, which holds nested arrays of data with
the "column" names as keys.

Let's try it. Add to the `index()` body:

    // get a template parser
    $parser = \Config\Services::parser();
    // tell it about the substitions
    return $parser->setData(['records' => $records])
        // and have it render the template with those
        ->render('placeslist');

Note that the parser-processed result is returned - the framework
will take that and forward it to the browser.

Clicking on the travel destinations link on the homepage should 
invoke the above controller and show the list.

## Step 2

The list of travel destinations is presented in the same order as the mock data.

If you mouse over any of the names, you will notice that the link for it is "/travel/showme/X",
where "X" is the ID of the destination. Clicking those will result in a 404, because we need to add them.

With segment-based naming, "travel" is the  controller name, "showme" is the method name,
and "X" is the first parameter to "showme".

We need to add the `showme()` method to our `Travel` controller.

    public function showme($id)
    {
    }

The first part of its body is similar to that of `index()`, except for getting a single record.

    // connect to the model
    $places = new \App\Models\Places();
    // retrieve all the records
    $record = $places->find($id);

We will use the template parser again, but with the `oneplace` template.
The substitution fields are those from the data record.

    // get a template parser
    $parser = \Config\Services::parser();
    // tell it about the substitions
    return $parser->setData($record)
        // and have it render the template with those
        ->render('oneplace');

## Step 3

On the single travel destination page, the image is not showing up.
Looking at the template, the image link is "/image/xxx".

This is a good excuse for a utility controller, `Media`, which could serve
different kinds of content from private storage on the server. 
We'll need to add a route mapping for it, in `app/Config/Routes.php`,
in the routes definitions section about line 75.

    $routes->get('/image/(:any)', 'Media::image/$1');

We can then make `app/Controllers/Media`, with a suitable `image()` method:

    <?php
    namespace App\Controllers;

    class Media extends BaseController
    {
        public function image($filename)
        {
            readfile(WRITEPATH . 'data/' . $filename);
        }
    }

**Note: I had problems with this step. A workaround, which I will
go along with, is to copy the `writable/data/images` folder inside
your `public` folder, and to remove the routing rule we added to
`Routes.php` above. This bypasses the `Media` controller.**

## Step 4

The last it is a service controller. This is not a REST endpoint, but
the `Places` controller can give you a taste of what it is like to return
data instead of a formatted page.

We only have a default method, and it needs to retrieve our model data
and then return the JSON-encoded string version of it.

    <?php
    namespace App\Controllers;

    class Places extends \CodeIgniter\Controller
    {
        public function index()
        {
           // connect to the model
           $places = new \App\Models\Places();
           // retrieve all the records
           $records = $places->findAll();
           // JSON encode and return the result
           return json_encode($records);
        }
    }

Note that it only needs to extend Controller and not BaseController.

## Notes

If the lab starter is updated, you can refresh yours with

    git remote add upstream https://github.com/jedi-academy/dgpt4711lab04.git
    git pull upstream master

This will merge any changes into your project.

You only need to define the remote alias once,