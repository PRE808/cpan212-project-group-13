# BookTrack Proposal

## 1. Problem and Users

BookTrack is designed for students and readers who want an easy way to keep track of the books they want to read, are currently reading, and have finished.

The app gives users one place to organize their personal reading collection and keep information such as the book title, author, reading status, rating, and notes.

## 2. Features

### MVP

- A user can add a book to their personal collection.
- A user can view their books.
- A user can view the details of a book.
- A user can edit their books.
- A user can delete their books.
- A user can search for book information using the Open Library API.

### Later

- Users can share books with other users.
- Users can write public reviews.
- Users can follow other readers.
- Users can receive book recommendations.

## 3. External API

We will use the Open Library API to search for book information.

The API will be called by our Express server and will be used when users search for books.

API name: Open Library API

API key: No API key is required for the planned requests.

Feature using the API: Users can search for books and get information such as the title, author, and publication year.

We will follow the API's usage guidelines and rate limits.

Example request:

```text
https://openlibrary.org/search.json?q=harry+potter


Example response:

{
  "title": "Harry Potter and the Philosopher's Stone",
  "author_name": ["J. K. Rowling"],
  "first_publish_year": 1997
}


## 4. Data Model

### Book

- title: string, required
- author: string, required
- status: string, required
- rating: number, optional
- notes: string, optional
- publishedYear: number, optional
- userId: string, required

### Reading Goal

- name: string, required
- targetBooks: number, required
- year: number, required
- description: string, optional
- userId: string, required

### User

- email: string, required
- passwordHash: string, required

### Relationships

- A user can have many books.
- A user can have many reading goals.
- Each book belongs to one user.
- Each reading goal belongs to one user.

## 5. Endpoint List

| Method | Path | Purpose | Success | Errors |
|---|---|---|---|---|
| GET | /api/books | Get all books | 200 | 500 |
| GET | /api/books/:id | Get one book | 200 | 404 |
| POST | /api/books | Create a book | 201 | 400 |
| PATCH | /api/books/:id | Update a book | 200 | 400, 404 |
| DELETE | /api/books/:id | Delete a book | 204 | 404 |
| GET | /api/goals | Get all reading goals | 200 | 500 |
| GET | /api/goals/:id | Get one reading goal | 200 | 404 |
| POST | /api/goals | Create a reading goal | 201 | 400 |
| PATCH | /api/goals/:id | Update a reading goal | 200 | 400, 404 |
| DELETE | /api/goals/:id | Delete a reading goal | 204 | 404 |
| GET | /api/books/search?q= | Search for books using Open Library | 200 | 502, 504 |

## 6. Wireframes

## 6. Wireframes

### Page 1 - Book List

![Book List](wireframes/page1.png)

### Page 2 - Book Detail

![Book Detail](wireframes/page2.png)

### Page 3 - Add Book

![Add Book](wireframes/page3.png)

### Page 4 - Edit Book

![Edit Book](wireframes/page4.png)



## 7. Team Roles

- API: Pre808
- Frontend: To be decided
- Database: To be decided
- Repository and Pull Requests: Pre808

## 8. Repo Setup

Repository name:

cpan212-project-group-13

Repository URL:

https://github.com/pre808/cpan212-project-group-13

The repository contains the required api, web, and docs folders.

## 9. Commits and Contributions

Each group member will make commits using their own GitHub account.

The work completed by each member will be recorded in CONTRIBUTIONS.md.

