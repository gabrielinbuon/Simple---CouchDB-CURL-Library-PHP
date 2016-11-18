# CouchDBLibrary-PHP
Simple CouchDB CURL Library : PHP

This is just a simple library for basic use. Can be extended as it goes.
I will try improving the library if i have time in future.

Please feel free to comment and write your suggestion.


### How to create database
Do not forget to include the library ```sh require "./lib.php"; ```

You have to provide your database name in the parameter.
NOTE - replace ```sh$dbname``` with your database name to be
```sh
$obj->createDatabase($dbname);
```

### How to create document
The best way to create new document is using template (at least to my experience)
You can store your template in different file inside tpl folder and call when necessary, 
but for now we will not go deep into that. Anyway, let's look the code below :

First: we create array that holds the data of our document structure
```sh
$create_tpl = array(
		'_id' => 'uid',
		'title' => '123',
		'description' => '0',
		'author' => '0',
		'isbn' => ''
);
```
NOTE : Do not change the code ``` '_id' => 'uid'``` the template method will generate UNIQUE ID and will change it automatically. It is mandatory to have this code in your document structure.

Second: we pass the template to template handler (this is mandatory or else create method will not know the document structure)
```sh
$obj->templates($create_tpl);
```
Third: just call create method to create new document
```sh
$obj->createNewDocument();
```
