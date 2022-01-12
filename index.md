## Question 1:

Please have a look at this [Jupyter Notebook PDF.](Ester Tsai Shopify Summer 2022 Data Science Intern Challenge Q1.pdf)

## Question 2:

### (a) How many orders were shipped by Speedy Express in total?
ANSWER: 54

```markdown
SELECT COUNT(*) FROM Orders
WHERE ShipperID IN
( SELECT ShipperID FROM Shippers
  WHERE ShipperName = 'Speedy Express');
```

<img src="a1.PNG?raw=true"/>

### (b) What is the last name of the employee with the most orders?
ANSWER: Peacock

```markdown
SELECT LastName FROM Employees
WHERE EmployeeID IN 
( SELECT EmployeeID FROM Orders
  GROUP BY EmployeeID
  ORDER BY COUNT(*) DESC
  LIMIT 1);
```

<img src="b1.PNG?raw=true"/>

### (c) What product was ordered the most by customers in Germany?
ANSWER: Boston Crab Meat

```markdown
SELECT ProductName FROM Products 
WHERE ProductID IN
( SELECT ProductID FROM Orders
  LEFT JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID
  LEFT JOIN Customers ON Orders.CustomerID = Customers.CustomerID
  WHERE Country = 'Germany' 
  GROUP BY ProductID
  ORDER BY SUM(Quantity) DESC 
  LIMIT 1);
```

<img src="c1.PNG?raw=true"/>


