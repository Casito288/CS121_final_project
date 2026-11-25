# CS121 FINAL PROJECT

## Inspired by good reads
```
I am an avid reader and immediatly thought about this as the project I was goind to do when the project came up

This project is a simple CLI based good reads replica.
It will have basic functions such as searching for books, adding and removing books from your TBR's (to be read lists) and already read lists. 
You will also be able to leave star'd and written reviews on the books that you search. 
This project is meant for book lovres if they want to keep a local library of the books they want to read or have already read. 
I will be needing to implement an api to make these searches possible from the CLI to the internet.
```


## mermaid live diagram
```mermaid
classDiagram

class Book {
    - title: String
    - author: String
    - ISBN: String
    - series: String
    - publicationYear: int
    + Book()
    + Book(title, author, ISBN, series, publicationYear)
    + getBookDetails(): String
}

class Review {
    - book: Book
    - rating: int
    - reviewText: String
    + Review()
    + Review(book, rating, reviewText)
    + createReview(): void
    + editReview(): void
    + displayReview(): String
}

class UserLibrary {
    - tbrList: List~Book~
    - readList: List~Book~
    - reviews: List~Review~
    + UserLibrary()
    + addToTBR(book): void
    + removeFromTBR(index): void
    + addToRead(book): void
    + removeFromRead(index): void
    + displayTBR(): void
    + displayRead(): void
    + addReview(review): void
    + displayReviews(): void
}

class BookCatalog {
    - books: List~Book~
    - popularBooks: List~Book~
    + BookCatalog()
    + searchByTitle(title): List~Book~
    + searchByAuthor(author): List~Book~
    + searchByISBN(ISBN): List~Book~
    + searchBySeries(series): List~Book~
    + searchBooks(searchTerm): List~Book~
    + getPopularBooks(): List~Book~
    + displayPopularBooks(): void
}

class Menu {
    - library: UserLibrary
    - catalog: BookCatalog
    + Menu()
    + displayWelcome(): void
    + displayMainMenu(): String
    + searchBookMenu(): void
    + popularBooksMenu(): void
    + tbrMenu(): void
    + readBooksMenu(): void
    + handleUserInput(): void
    + exitProgram(): void
}

Review --> Book
UserLibrary o-- Book
UserLibrary o-- Review
BookCatalog o-- Book
Menu --> UserLibrary
Menu --> BookCatalog
```
