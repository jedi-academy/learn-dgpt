# Seminar #8 - Views
COMP4711 - BCIT/DGPT - Fall 2019

I'm going to share a few tips and strategies with you, and then get you to
apply those to the lab we did last week.

## What's in a View?

A "view" file is source for presentation as a webpage or part of one.
It contains HTML, and then some way to use or substitute data parameters
that have been passed to it.

## How is it used?

CodeIgniter has several tools to process view files and generate the corresponding
HTML.The most common are the View Renderer and the View Parser.

The [View Renderer](https://codeigniter4.github.io/userguide/outgoing/view_renderer.html),
which lets you embed snippets of PHP code to access variables

    <p class="version">version <?= CodeIgniter\CodeIgniter::CI_VERSION ?></p>
    
The [View Parser](https://codeigniter4.github.io/userguide/outgoing/view_parser.html),
which lets you embed special substitution fields 

    {menudata}
    <li class="nav-item {active}"><a class="nav-link" href="{link}">{! name !}</a></li>
    {/menudata}

Choose the one you want to use, and tell it to process view files and return
the result as the return value of a call to your controller.

    public index() {
        $view = \Config\Services::renderer();
        return $view->render('myview');
    }

OR

    public index() {
        $parser = \Config\Services::parser();
        return $parser->render('adifferentview');
    }

## View Building Strategies

There are many possible strategies you could use to assemble a view, and here are
three common ones:

### All-in-one

The view source for a given page is contained in just one source file.

    public index() {
        $view = \Config\Services::renderer();
        return $view->render('myview');
    }

### Slices

Reduce repetition on multiple pages by splitting the view into slices:

    public index() {
        $view = \Config\Services::renderer();
        $output = $view->render('top') .
            $view->render('content') .
            $view->render('bottom');
        return $output;
    }

### Wireframe 

I setup a "wireframe layout" (or several) for a site, and name
each panel in it.

<img src="/pix/lessons/5/5-10.png"/>

I then build each panel independently, and pull them together with a `render`
method in my base controller.

    $this->data['titling'] = $this->parser->setData($this->data, 'raw')
                    ->render('theme/' . $layout);

    // finally, assemble the browser page!
    $output = $this->parser->setData($this->data, 'raw')
                    ->render('theme/template');

    // Sends the output to the browser
    $this->response->setBody($output);
    $this->response->send();

I set the response's body explicitly here, as this could be nested awkwardly to
provide a "return" value for the controller's routed method.


## Build an HTML Table Easily

CodeIgniter provides some other convenience classes to make your life
easier, for instance the [HTML Table Class](https://codeigniter4.github.io/userguide/outgoing/table.html).

    $table = new \CodeIgniter\View\Table();
    $table->setHeading('Name', 'Color', 'Size');

    $table->addRow(['Fred', 'Blue', 'Small']);
    $table->addRow(['Mary', 'Red', 'Large']);
    $table->addRow(['John', 'Green', 'Medium']);

    $content =  $table->generate(); //??

## Build an HTML Form Easily

CodeIgniter has a [form helper](https://codeigniter4.github.io/userguide/helpers/form_helper.html)
for building forms.

Start with a `form_open` at the one end, finish with a `form_close` at the other,
and add an element for each of the fields you would like, between those.

If this is a form that corresponds to a database table, make sure that the
**name** atributes of each form field match the **property** names
in the table.
