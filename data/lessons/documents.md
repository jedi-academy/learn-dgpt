# Seminar #7 - Document Models
COMP4711 - BCIT/DGPT - Fall 2019

## Databases

<img src="/pix/lessons/x/slide_23.jpg"/>

## Relational vs Document

Relational: database < table < rows (records) < columns

Document: database < collection < document < properties

RDB has schema & DDL to define structure

DDB can have schema to constrain structure

## Contrast

<img src="/pix/lessons/x/i5.png"/>

<img src="/pix/lessons/x/i6.png"/>


## Simple Models

We have a Simple Model  for you to work with from this point forward.

- uses a document for persistent storage,
- provides a subset of the Model/RDB interface
- doesn't need a database server

This approach has drawbacks:

- can only handle small collections (1000 documents?)
- meant for simplicity, not speed
- no data typing (everything is strings)

There are some good things too:

- data files can be edited with a text editor
- using the API will help you with CodeIgniter's Model in future

# Jedi- Academy / Simple-Models

Let's take a look ... https://github.com/jedi-academy/simple-models

1. Choose a data persistence format: CSV, JSON or XML

2. Your model will then extend Simple\Models\CSVModel etc

3. You need three properties:
    
-    $origin - Persistent path & filename for this model
-    $keyField - Name of the primary key property
-    $validationRules - Rules used to validate data

## SimpleModel API

### Retrieve documents

- **find($id)** to get one
- **findAll($limit,$offset)** to get some or all

### CRUD

- **save($data)** to add or update a document
- **insert($data,$returnID)** to add a document, and optionally gets its ID
- **update($id,$data)** to update a document
- **delete($id)** to delete a document
- **exists($id)** to see if a document exists

### Miscellaneous

- **getValidationRules()** to get the rules used for validation
- **count()** to get the size of the collection

