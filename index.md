## Question 1:

Please have a look at this [Jupyter Notebook PDF.](Ester Tsai Shopify Summer 2022 Data Science Intern Challenge Q1.pdf)

--------

## Question 2:


### (a) How many orders were shipped by Speedy Express in total?
ANSWER: 54

Logic: Speedy Express has a ShipperID of 1, so I will calculate the total number of orders from the shipper with a ShipperID of 1.

```markdown
SELECT COUNT(*) FROM Orders
WHERE ShipperID IN
( SELECT ShipperID FROM Shippers
  WHERE ShipperName = 'Speedy Express');
```

<img src="a1.PNG?raw=true"/>


### (b) What is the last name of the employee with the most orders?
ANSWER: Peacock

Logic: The employee with the most orders has an EmployeeID of 4, so I will identify the last name of the employee with an EmployeeID of 4.

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

Logic: The product that was ordered the most by customers in Germany has a ProductID of 40, so I will identify the product with a ProductID of 40.

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

--------

Applicant: Ester Tsai

Email: tsaiester@gmail.com

