# Books

Project1 (Books) Submission for Harvard's CS50 (2018 Version): Web Programming with Python and JavaScript Course.

## Motivation
 Combined with an internal drive to learn more about front end development as well as a required component to the CS50 course, this project is a deeper example of leveraging python and html for front-end development.The goal of this project is to build a website that is a book review that allows a user to register an account, login, leave reviews as well as retrieve other reviews from a third-party API called GoodReads.

## Build Status
[![Build Status](https://travis-ci.com/username/projectname.svg?branch=master)](https://travis-ci.com/username/projectname)

## Features
This website contains the following features:
  * Registration: Users will be able to create an account and register by providing a username and password.
  * Login: Once registered, Users can login with a username and password
  * Logout: Logged in users can logout of the website
  * Import: There is a file called import.py that imported all of the 5000 books that should be included in the "books" SQL database
    * To avoid manually inserting each book into the table, the import.py script handles it in an ad-hoc instance.
  * Search: Once a user is logged in, they will be taken to a page where they can search for a book by either ISBN, title, or author.
    * After performing the search,  a list of possible matching results, or some sort of message if there were no matches will be returned
    * If the user typed in only part of a title, ISBN, or author name, the search page will find matches for those as well
  * Book Page: When users click on a book from the results of the search page, they will be taken to a book page, with outlines significant details about the book such as:
    * title
    * author
    * publication year
    * ISBN number
    * any reviews that users have left for the book
  * Review Submission: On the book page, users will be able to submit a review: consisting of a rating on a scale of 1 to 5, as well as a text component to the review where the user can write their opinion about a book
    * Users will not be able to submit multiple reviews for the same book
* Goodreads Review Data: Displays the average rating and number of ratings the work has received from Goodreads.

This project creates 3 SQL Databases with 3 tables:
  * Users
  * Books
  * Reviews

There is a file called create.py that is a script that creates these SQL databases and models.py that outlines the table name and columns in a Python class.


## Installation
This project requires flask. Once flask is installed, you will also need a database to store your table values. For this project, I used a Heroku database.

## API Reference
Since this project refers to the API on GoodReads, here is the documentation that was used:
  https://www.goodreads.com/api

I used the get book.review_counts API method to get the statistics I needed.

This website also returns JSON data if accessed. When users make a `GET` request to the website’s `/api/<isbn> route`, where `<isbn>` is an ISBN number, the website will return a JSON response containing the book’s title, author, publication date, ISBN number, review count, and average score. Below is an example of the resulting JSON:

```
{
    "title": "Memory",
    "author": "Doug Lloyd",
    "year": 2015,
    "isbn": "1632168146",
    "review_count": 28,
    "average_score": 5.0
}
```

## How to Use?
This is to be run using flask with the following parameters:

```
$ export FLASK_APP=application.py
```
```
$ export FLASK_ENV=development
```
```
$ export DATABASE_URL= <Heroku Database Credentials>
```
```
$ Flask Run
```

## Credits
Source Code provided by Harvard's CS50 curriculum and professor Brian Yu.
