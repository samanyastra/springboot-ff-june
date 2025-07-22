# Project102 - library management System
- ## Create spring boot application **Library manager** with below APIs
    - ### /getallbooks (Get Request)
         - **Scenario 1**
            - ***Params*** - none
            - ***Business Logic*** - Should fetch all the avlb books with the relevant information from the database (Services, JPA, Model)
            - ***Validation*** - If database not contain any books, send empty list with the response code  **200** (ResponseEntity)
            - ***Response*** - Upon successful operation return the response with an array or list of the books with the status code of **200**.
        
        ---
         - **Scenario 2**
            - ***Params*** - filter(optional parameter)
            - ***Business Logic*** - Should fetch all the avlb books ***that contains value passed in the filter in the book_name field*** with the relevant information from the database (Services, JPA, Model)
            - ***Validation*** - If database not contain any books with provided filter value, send empty list with the response code of **200** (ResponseEntity). In case user send weird payload to try something fancy with the api, return **400**
            - ***Response*** - Upon successful operation return the response with an array or list of the books


    - ### /detailbook/{bookId} (Get Request)
        - ***Params*** - bookId - a unique ID to identify each book  (Path variable)
        - ***Business Logic*** - Should fetch all the avlb detail based on the bookId (Services, JPA, Model)
        - ***Validation*** - If database not contain any book with this id, send not found error with response code  **404** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the JSON(HashMap) of the required details with the status code of **200**.

    - ### /createbook (Post Request)
        - ***Params*** (Request Body)
            - **book_name** - name for a given book
            - **writer** - person who wrote this book
            - **added_on** - date on which this book was added to library
            - **published_on** - date on which book was published
            - **description** - A small description about the book
            - **copies** - count of this book avlb in library
        

        - ***Business Logic*** - Should create a new book emtry, assign a unique bookId and store the data in Database (Services, JPA, Model)

        - ***Validation*** - If any of the field is null or invalid return message saying "Invalid Data"  **400** (ResponseEntity)

        - ***Response*** - Upon successful operation return the response with the JSON(HashMap) of the required details with the status code of **200**.
        
    - ### /removebook/{bookId} (delete Request)
        - ***Params*** - bookId - a unique ID to identify each book  (Path variable)
        - ***Business Logic*** - Should delete the book based on the bookId (Services, JPA, Model)
        - ***Validation*** - If database not contain any book with this id, send not found error with response code  **404** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the message **Book {book_name} deleted** with the status code of **200**.

    - ### /issuebook/{bookId} (get Request)
        - ***Params*** - bookId - a unique ID to identify each book  (Path variable)
        - ***Business Logic*** - Should reduce avlb count of the book based on the bookId (Services, JPA, Model)
        - ***Validation*** - If database not contain any book with this id, send not found error with response code  **404** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the JSON(HashMap) of the required details with the status code of **200**.