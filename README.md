# Book-Lending-App
Management of library books

object oriented programing is a style of programing that is centred around objects instead of functions.
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
to borrow and inputing the borrowers registration Id respectively.  Also i want the authors name field, book name field, ISBN field and Quantity field to be disabled.
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
check if value of any propety is empty
       flag an error
else call the saveToLocalStorage function and pass the object as parameter

In saveToLocalStorage function which takes two parameter - book object and the local storage key
    Set a variable enterBook = []
 Check if there is no item in Local storage for parameter "local storage key"
    push the book object to the enterBook  array
 else assign the local storage array to the enterBook array. 
      ensure to convert this to object from string using JSON.parse
      push the book object into the enterBook array
call the Save to Local storage method

TO BORROW A BOOK
select Borrow a book
This call the displayCard function that adds two fields to the UI; Select Book Title to borrow and enter User Registration ID
All book Title are prepopulated in the select dropdown
The prepopulate function;
 Check if library books are stored in Local storage
    Get The books, asign to an array and map the option field of the select element, then assign to the id.INNERHTML of the select book element

Instatiat a new Book Obj from the previous book Object
  Set the quantity to 1 because users are oly allowed to borrow 1 book of same type
  borrowBookObj.quantity = 1
assign the userRegistraionId to the new object
  borrowBookObj.userRegistraionId = get this using getElementById
On Select of book title to borrow, 
  Fetch the book data from Local storage and populate the form fields which have been disable / made read only
  Enter the registration id of user borrowing the book
On Submit of Form
       
 Call the Update local storage function and pass the bookObj and newBookObj parameter
    
   Check if user borrowed that book, if Yes
      throw an error, You have already borrowed this book
   else,  Get the library book in Local storage
          Find the index of the bookObj in the library book
          Update the quanty by subtracting 1
          save the book object to local storage
	  save the borrowed book object to local storage

          
To Return a book

On Select of book title to return, 
  Fetch the book data from Local storage and populate the form fields 
  enter registration id of user returning the book
On Submit of Form
	get the borrowed book array from local storage
  	Check if user borrowed that book by filtering borrowed books array were borrowBookObj isbn = isbn in borrowerd book array and 		borrowBookObj registration id = registration id in borrowd book array and quantity in borrowed book array = 1
   	if no value is returned throw an error - "No match for borrowed book"
   else    
     	Call the Update local storage function and pass the bookObj and newBookObj parameter
 
          Get the library book in Local storage
          Find the index of the bookObj in the library book
          Update the quanty by adding 1
          update the quantity in borrowed book array by subracting 1
          save the book object to local storage
	  save the borrowed book object to local storage
    



 
