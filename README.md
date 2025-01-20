Exploring SQL queries with SELECT, WHERE clauses, and constraints using Country and Persons tables.
A hands-on project to explore SQL queries, focusing on SELECT statements, WHERE clauses, and constraints. Includes tasks like filtering data, handling NULL values, and working with multiple tables (Country and Persons) to practice real-world database operations.

1. Create two tables
   
   Country and Persons
   Country:
     create table Country 
      (
	      Id INT primary key,
   
        Country_name varchar(50),

        Population INT,
   
        Area varchar(50)   
      );
   
   Persons:
   
      create table Persons
         (
	      Id INT primary key,
     
        Fname varchar(50),
      
        Lname  varchar(50),
   
        Population INT,
   
        Rating  FLOAT CHECK (Rating between 0.0 and 5.0),
   
        Country_Id INT,
   
        Country_name varchar(50),
   
        foreign key (country_Id) references Country(Id)
      );
   
2. INSERT Records
   
    Country:
   
    INSERT INTO Country (Id, Country_name, Population, Area) VALUES
   
        (1, 'USA', 331002651, 'Texas'),
   
        (2, 'India', 1380004385, 'New Delhi'),
   
   	(3, 'China', 1439323776, 'Beijing'),
   
	(4, 'Canada', 37742154, 'Ottawa'),
   
	(5, 'Australia', 25499884, 'Canberra'),

	(6, 'UK', 67886011, 'London'),

	(7, 'Germany', 83783942, 'Berlin'),
   
	(8, 'France', 65273511, 'Paris'),
   
	(9, 'Japan', 126476461, 'Tokyo'),
   
	(10, 'Brazil', 212559417, 'Brasília');
   
   Persons
   
    INSERT INTO Persons (Id, Fname, Lname, Population, Rating, Country_Id, Country_name) VALUES
   
			(1, 'John', 'Doe', 331002651 , 4.5, 1, 'USA'),
     
			(2, 'Alice', 'Smith', 1380004385, 4.8, 2, 'India'),
   
			(3, 'Bob', 'Brown', 1439323776, 3.9, 3, 'China'),
     
			(4, 'Emma', 'Jones', 37742154, 4.7, 4, 'Canada'),   
   
			(5, 'Liam', 'Wilson', 25499884, 4.2, 5, 'Australia'),
   
			(6, 'Sophia', 'Taylor', 67886011, 3.8, 6, 'UK'),
   
			(7, 'Mia', 'Anderson', 83783942, 4.0, 7, 'Germany'),
   
			(8, 'Oliver', 'Thomas', 65273511, 4.6, 8, 'France'),
   
			(9, 'Ava', 'White', 126476461, 4.1, 9, 'Japan'),
   
			(10, 'James', 'Martin', 212559417, 3.5, 10, 'Brazil'),
   
			(11, 'Jacob', 'Clark', 331002651, 4.3, 1, 'USA'),
   
			(12, 'Isabella', 'Lopez', 1380004385, 4.4, 2, 'India'),
   
			(13, 'William', 'King', 1439323776, 3.7, 3, 'China'),
   
			(14, 'Charlotte', 'Lewis', 37742154, 4.6, 4, 'Canada'),
   
			(15, 'Amelia', 'Walker', 25499884, 4.2, 5, 'Australia'),
   
			(16, 'Ethan', 'Harris', NULL, 3.9, NULL, NULL),
   
			(17, 'Benjamin', 'Young', NULL, 4.8, NULL, NULL),
   
			(18, 'Harper', 'Allen', 83783942, 4.1, 7, 'Germany'),
   
			(19, 'Lucas', 'Scott', 65273511, 4.7, 8, 'France'),
   
			(20, 'Mason', 'Adams', 212559417, 3.6, 10, 'Brazil');   


3. List the distinct country names from the Persons table.
   
    select distinct Country_name  from Persons;
   
4. Select first names and last names from the Persons table with aliases.
   
    select Fname  'FirstName',Lname 'Lastname'  from Persons;

5. Find all persons with a rating greater than 4.0.
    
    select * from Persons where Rating >4.0;

6. Find countries with a population greater than 10 lakhs.
    
    select Country_name from country where population >1000000;
    
    select * from country where population >1000000;
    
   
7. Find persons who are from 'USA' or have a rating greater than 4.5.
    
     select *  from Persons where country_name='USA' or rating >4.5;
    
   
8. Find all persons where the country name is NULL.
    
    select * from persons where country_name is null;
     
9. Find all persons from the countries 'USA', 'Canada', and 'UK'.
    
     select * from persons where country_name in ('USA','Canada','UK');
    
10. Find all persons not from the countries 'India' and 'Australia'.
    
      select * from persons where country_name not in ('India','Australia');
    
11. Find all countries with a population between 5 lakhs and 20 lakhs.
    
      select * from country where population between 500000 and 1000000;
    
12. Find all countries whose names do not start with 'C'.
    
     select * from country where country_name not like 'c%';

   
