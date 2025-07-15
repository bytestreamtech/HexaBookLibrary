# BookApi

## Overview
This project is a .NET 8 Web API that performs CRUD operations on a Book model. The application uses Entity Framework with SQLite as the database provider and implements the repository pattern for data access.

## Project Structure
The project is organized into the following directories and files:

- **Controllers**
  - `BooksController.cs`: Contains methods for handling HTTP requests related to the Book model, including Create, Read, Update, and Delete operations.
  
- **Models**
  - `Book.cs`: Defines the properties of the Book model: ID, Title, Author, PublishedYear, Language, and Genre.
  
- **Repositories**
  - `IBookRepository.cs`: An interface that defines the contract for the repository pattern, including method signatures for CRUD operations.
  - `BookRepository.cs`: Implements the `IBookRepository` interface and contains the logic for interacting with the database using Entity Framework.
  
- **Data**
  - `BookContext.cs`: Inherits from `DbContext` and defines the `DbSet<Book>` property for the Book model, configuring the database context for Entity Framework.
  
- **Configuration**
  - `appsettings.json`: Contains configuration settings for the application, including the connection string for the SQLite database.
  
- **Project File**
  - `BookApi.csproj`: The project file for the .NET application, including references to the required packages for Entity Framework and SQLite.
  
- **Entry Point**
  - `Program.cs`: The entry point of the application, setting up the web host, configuring services, and mapping the controllers.

## Getting Started

### Prerequisites
- .NET 8 SDK
- SQLite

### Setup
1. Clone the repository or download the project files.
2. Navigate to the project directory.
3. Restore the project dependencies by running:
   ```
   dotnet restore
   ```
4. Update the connection string in `appsettings.json` if necessary.

### Running the Application
To run the application, use the following command:
```
dotnet run
```
The API will be available at `http://localhost:5000`.

### API Endpoints
- **GET** `/api/books`: Retrieve all books.
- **GET** `/api/books/{id}`: Retrieve a book by ID.
- **POST** `/api/books`: Create a new book.
- **PUT** `/api/books/{id}`: Update an existing book.
- **DELETE** `/api/books/{id}`: Delete a book by ID.

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License
This project is licensed under the MIT License.