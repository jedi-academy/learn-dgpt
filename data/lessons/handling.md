# Seminar - Handling Input
COMP4711 - BCIT/DGPT - Fall 2019

HTML forms are sent to a controller method as a set of key/value pairs.

The target method is identified in the "action" attribute of the HTML form.

The key/value pairs come from the named input fields in the form.

## Getting data

https://codeigniter4.github.io/userguide/incoming/incomingrequest.html#retrieving-input

## Form validation tutorial/basics

https://codeigniter4.github.io/userguide/libraries/validation.html

Phases:

- show what we received
- setup rules for the data
- try to process successfully

## In lab...

Apply the above to our travel places editing form

## Caution

The input values for different input fields are not always intuitive.
For instance, a checkbox is "set" if it is present in the incoming fields,
and "not set" otherwise.

You may need some experimentation to get things right!
