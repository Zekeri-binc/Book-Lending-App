Object oriented programing is a style of programing that is centred around objects instead of functions.
An object is a group of related variables and functions. The variables are called properties and the function called methods
OOP has four key concepts which include ecapsulation, abstraction, inheritance and polymophysim,
Encasulation: grouping related variables and functions together in an object. this reduces complexity.
Abstraction is the ability to hide some properties and methoths in an object and show only the ensentials
inheritance help us eliminate redundant code and repections of functions. if we have some common variables and functions we can define them once in a parent object, and make other object to inherit these.
Polymophisim helps us refactor if/else or switch/cases statement

A BOOK LENDING SYSTEM

USER STORY

1. As a user i want to be able to select the task to be performed on the App. A drop down
   field to select any of "Register Book", "Borrow Book", "Return Book"
2. I want, if Register book is selected to be able to enter authors name, book name, ISBN, Quantity then Submit.
3. At submision, I want if any of the above fields is empty, the form to not sumbit but throw an error "Input FIeld Cannot Be Blank"
4. If all fields are inputed, and form submited i want a success message "Submition Sucessful".
5. At successful submision, I want data to be saved to local storage and the fields cleared.
6. I want, if Borrow book is selected, two new input field to pop up for selecting the book title
   to borrow and inputing the borrowers registration Id respectively. Also i want the authors name field, book name field, ISBN field and Quantity field to be disabled.
7. I want, the select book field in 6 above to display all the names of the books registered in local storage
8. I want if i select a book, the book details (authors name, book name, ISBN, Quantity) to be populated
9. I want the two new field to be manadatory and if not filled there should be a validation error at click of Submit.
10. At successful submition, i want the data on the form to be saved to local storage with a borrowed quantity of 1 and I want 1 to be subtracted from the quantity of the books in the library.
11. I want, if Return book is selected, two new fields in 6 above to pop up for selecting the book
    to return and the borrowers registration Id respectively. Also i want the authors name field, book name field, ISBN field and Quantity field to be disabled.
12. I want, the select book field in 11 above to display all athe names of the books registered in local storage
13. I want if i select a book, the book details (authors name, book name, ISBN, Quantity) to
    be populated
14. I want the two new field to be manadatory and if not filled there should be a validation error at click of Submit.
15. I want if all fields are filled and submit is click, the system to check if there is such a book borrowed by the user with respective user registration id. This checks if the borrowed book array has a record of such book isnb against user registration ID and quantity is 1.
16. If it finds the book borrowed against the user, it will update the quanty by subtracting 1 and it will update the book quantity in the library books to plus 1.
17. I want if user is borrowing a book he has borrowed before, a validation error to display You have already borrowed this book. Users are only allowed to borrow 1 quantity of same book

TO REGISTER A BOOK
    Select Register book on the form
    input Author name, Book name, isbn, quantity
    Get the values using document.getElementById respectively and assign to the variables
    create an object to contain all input as property
            function Book(authorName, bookName, isbn) {  
            this.authorName = authorName
            this.bookName = bookName
            this.isbn = isbn
            this.quantity = quantity
            }
