Exercise #1:

	CREATE TABLE Products (
		ProductID int,
		ProductName text,
		Price float,
		Category text
	);

	INSERT INTO Products (ProductID, ProductName, Price, Category)
	VALUES (1, 'Laptop', 1200.00, 'Electronics');

	INSERT INTO Products (ProductID, ProductName, Price, Category)
	VALUES (2, 'Desk Chair', 250.50, 'Furniture');

	Select * from Products;

=================================================================

Exercise #2:

	CREATE TABLE Employees (
		EmployeeID int,
		FirstName text,
		LastName text,
		Department text
	);

	INSERT INTO Employees (EmployeeID, FirstName, LastName, Department)
	VALUES (1, 'Alice', 'Johnson', 'HR');

	INSERT INTO Employees (EmployeeID, FirstName, LastName, Department)
	VALUES (2, 'Bob', 'Smith', 'IT');

	SELECT FirstName, LastName FROM Employees;

=================================================================

Exercise #3:

	CREATE TABLE Inventory (
		ItemID int, 
		ItemName text, 
		UnitsInStock int
	);

	INSERT INTO Inventory (ItemID, ItemName, UnitsInStock)
	VALUES (1, 'Printer Paper', 15);

	INSERT INTO Inventory (ItemID, ItemName, UnitsInStock)
	VALUES (2, 'Staples', 30);


	SELECT ItemID, ItemName, UnitsInStock FROM Inventory WHERE UnitsInStock < 20;

=================================================================

Exercise #4: 

	CREATE TABLE Books (
		BookID int, 
		Title text, 
		Author text, 
		Price float
	);

	INSERT INTO Books (BookID, Title, Author, Price)
	VALUES (1, 'The Great Gatsby', 'F. Scott Fitzgerald', 10.99);

	INSERT INTO Books (BookID, Title, Author, Price)
	VALUES (2, '1984', 'George Orwell', 8.99);

	INSERT INTO Books (BookID, Title, Author, Price)
	VALUES (3, 'The Catcher in the Rye', 'J. D. Salinger', 7.99);


	SELECT BookID, Title, Author, Price FROM Books;


=================================================================

Exercise #5: 

	CREATE TABLE Courses (
		CourseID int, 
		CourseName text, 
		Department text, 
		Credits int
	);

	INSERT INTO Courses (CourseID, CourseName, Department, Credits)
	VALUES (101, 'Introduction to Psychology', 'Psychology', 3);

	INSERT INTO Courses (CourseID, CourseName, Department, Credits)
	VALUES (102, 'Principles of Economics', 'Economics', 4);

	INSERT INTO Courses (CourseID, CourseName, Department, Credits)
	VALUES (103, 'Introduction to Computer Science', 'Computer Science', 3);


	SELECT CourseName, Department FROM Courses;

=================================================================

Exercise #6: 

	CREATE TABLE RestaurantReviews (
		ReviewID int, 
		RestaurantName text, 
		Rating text, 
		Reviewer text, 
		ReviewDate date
	);

	INSERT INTO RestaurantReviews (ReviewID, RestaurantName, Rating, Reviewer, ReviewDate)
	VALUES (1, 'Cafe Mocha', 'Excellent', 'John Doe', '2022-01-15');

	INSERT INTO RestaurantReviews (ReviewID, RestaurantName, Rating, Reviewer, ReviewDate)
	VALUES (2, 'Burger Corner', 'Good', 'Jane Smith', '2022-02-20');

	INSERT INTO RestaurantReviews (ReviewID, RestaurantName, Rating, Reviewer, ReviewDate)
	VALUES (3, 'Pasta Place', 'Excellent', 'Alice Jones', '2022-02-22');


	SELECT RestaurantName FROM RestaurantReviews WHERE Rating = 'Excellent';


=================================================================

Exercise #7: 

	CREATE TABLE Sales (
		SaleID int, 
		ProductID int, 
		SaleAmount float
	);

	INSERT INTO Sales (SaleID, ProductID, SaleAmount)
	VALUES (1, 1, 1200.00);

	INSERT INTO Sales (SaleID, ProductID, SaleAmount)
	VALUES (2, 2, 250.50);


	SELECT SUM(SaleAmount) AS CompleteSalesAmount FROM Sales;

=================================================================

Exercise #8: 

	CREATE TABLE Products (
	  ProductID int, 
	  ProductName text, 
	  Price float, 
	  Category text
	);

	INSERT INTO Products (ProductID, ProductName, Price, Category)
	VALUES (1, 'Apple', 0.50, 'Fruit');

	INSERT INTO Products (ProductID, ProductName, Price, Category)
	VALUES (2, 'Bread', 1.50, 'Bakery');


	SELECT AVG(Price) AS CompleteSalesAmount FROM Products;


=================================================================

Exercise #9: 

	CREATE TABLE Sales (
	  SaleID int, 
	  ProductID int, 
	  QuantitySold int, 
	  SaleDate date
	);

	INSERT INTO Sales (SaleID, ProductID, QuantitySold, SaleDate)
	VALUES (101, 1, 50, '2022-01-01');

	INSERT INTO Sales (SaleID, ProductID, QuantitySold, SaleDate)
	VALUES (102, 2, 30, '2022-01-02');

	INSERT INTO Sales (SaleID, ProductID, QuantitySold, SaleDate)
	VALUES (103, 1, 20, '2022-01-03');


	SELECT SUM(QuantitySold) AS CompleteSalesAmount FROM Sales WHERE ProductID = 1;


=================================================================

Exercise #10: 

	CREATE TABLE WeatherData (
	  RecordID int, 
	  Date date, 
	  Temperature float, 
	  City text
	);

	INSERT INTO WeatherData (RecordID, Date, Temperature, City)
	VALUES (1, '2022-01-01', 35.2, 'Springfield');

	INSERT INTO WeatherData (RecordID, Date, Temperature, City)
	VALUES (2, '2022-01-01', 28.4, 'Shelbyville');


	SELECT RecordID, Date, MAX(Temperature) AS MaxTemperature, City FROM WeatherData;
	SELECT RecordID, Date, MIN(Temperature) AS MinTemperature, City FROM WeatherData;

=================================================================

Exercise #11: 

	CREATE TABLE Orders (
			OrderID int, 
			ProductID int, 
			OrderDate date
		);
		
		
	CREATE TABLE Products (
		ProductID int, 
		ProductName text
		);
		

		INSERT INTO Orders (OrderID, ProductID, OrderDate)
		VALUES (1, 1, '2023-01-01'), (2, 2, '2023-01-02');

		INSERT INTO Products (ProductID, ProductName)
		VALUES (1, 'Laptop'), (2, 'Desk Chair');


	SELECT Products.ProductName, Orders.OrderDate FROM Orders INNER JOIN Products ON Orders.ProductID = Products.ProductID;

=================================================================

Exercise #12: 

	
CREATE TABLE Employees (
    EmployeeID int, 
    FirstName text, 
    LastName text, 
    DepartmentID int
	);
	
	
CREATE TABLE Departments (
    DepartmentID int, 
    DepartmentName text
    );
	

	INSERT INTO Employees (EmployeeID, FirstName, LastName, DepartmentID)
	VALUES (1, 'Alice', 'Johnson', 1), (2, 'Bob', 'Smith', 2);

	INSERT INTO Departments (DepartmentID, DepartmentName)
	VALUES (1, 'HR'), (2, 'IT');


SELECT Employees.FirstName, Employees.LastName, Departments.DepartmentName
FROM Employees INNER JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;

=================================================================
