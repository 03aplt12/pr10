# Создание SQL-запросов


1. База данных: Customers
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Customers;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Customers WHERE Country = 'Germany';
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
   FROM Customers
   JOIN Orders ON Customers.CustomerID = Orders.CustomerID
   WHERE Country = 'Germany' AND Orders.OrderDate > '1997-01-01';
   ```

2. База данных: Employees
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Employees;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Employees WHERE BirthDate > '1965-01-01';
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Employees.LastName, Orders.OrderID, Orders.OrderDate
   FROM Employees
   JOIN Orders ON Employees.EmployeeID = Orders.EmployeeID
   AND Orders.OrderDate > '2022-01-01';
   ```

3. База данных: Products
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Products;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Products WHERE Price > 50;
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Products.ProductName, Orders.OrderID, OrderDetails.Quantity
   FROM Products
   JOIN OrderDetails ON Products.ProductID = OrderDetails.ProductID
   JOIN Orders ON OrderDetails.OrderID = Orders.OrderID
   WHERE Orders.OrderDate BETWEEN '1997-01-01' AND '2022-12-31'
   ORDER BY OrderDetails.Quantity DESC;
   ```

4. База данных: Suppliers
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Suppliers;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Suppliers WHERE Country = 'USA';
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Suppliers.SupplierName, Products.ProductName, Suppliers.Country
   FROM Suppliers
   JOIN Products ON Suppliers.SupplierID = Products.SupplierID
   WHERE Suppliers.Country = 'Canada' AND Products.Price < 50;
   ```

5. База данных: Categories
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Categories;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Categories WHERE CategoryName LIKE '%Beverages%';
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Categories.CategoryName, Products.ProductName, Products.Price
   FROM Categories
   JOIN Products ON Categories.CategoryID = Products.CategoryID
   WHERE Categories.CategoryName LIKE 'Seafood' AND Products.Price > 15;
   ```

6. База данных: Shippers
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Shippers;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Shippers WHERE ShipperName LIKE '%Speedy%';
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Shippers.ShipperName, Orders.OrderID, Customers.CustomerName
   FROM Shippers
   JOIN Orders ON Shippers.ShipperID = Orders.ShipperID
   JOIN Customers ON Orders.CustomerID = Customers.CustomerID
   WHERE Shippers.ShipperName LIKE '%Speedy%' AND Orders.OrderDate < '1997-01-01';
   ```

7. База данных: Orders
   Запрос 1 (простой):
   ```sql
   SELECT * FROM Orders;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM Orders WHERE ShipCountry = 'USA';
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT Orders.OrderID, Customers.CustomerName, Products.ProductName, OrderDetails.Quantity, Orders.ShipperID
   FROM Orders
   JOIN Customers ON Orders.CustomerID = Customers.CustomerID
   JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID
   JOIN Products ON OrderDetails.ProductID = Products.ProductID
   WHERE Orders.ShipperID = '1' AND OrderDetails.Quantity > 10;

   ```

8. База данных: OrderDetails
   Запрос 1 (простой):
   ```sql
   SELECT * FROM OrderDetails;
   ```

   Запрос 2 (простой):
   ```sql
   SELECT * FROM OrderDetails WHERE Quantity > 50;
   ```

   Запрос 3 (сложный):
   ```sql
   SELECT OrderDetails.OrderID, Products.ProductName, Suppliers.SupplierName, Orders.OrderDate 
   FROM OrderDetails
   JOIN Products ON OrderDetails.ProductID = Products.ProductID
   JOIN Suppliers ON Products.SupplierID = Suppliers.SupplierID
   JOIN Orders
   WHERE OrderDetails.Quantity > 50 AND Suppliers.Country = 'USA';
   ```
