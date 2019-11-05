# Resource Presenters

Welcome to the world of REST, or more properly RESTful philosohies.

REST provides guidance for working with or managing "resources".

- using HTTP verbs as originally intended (POST, PATCH, DELETE, etc)
- exchange of object state
- ... in several representations
- ultimately with links for discovery

## CodeIgniter\RESTful\ResourceController

HTTP verbs are mapped to methods here, which
throw a "not implemented" exception until fixed.

## CodeIgniter\RESTful\ResourcePresenter

HTTP verbs are mapped to methods here, which
return a "not implemented" message until fixed.

## Client/Server?

A ResourceController is the "server" end of a client-server request

A ResourcePresenter is a normal MVC controller

The presenter "shadows" the controller.

Want to know more? https://codeigniter4.github.io/userguide/incoming/restful.html

