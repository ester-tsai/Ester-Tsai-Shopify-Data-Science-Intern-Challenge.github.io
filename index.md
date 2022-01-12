## Question 1:

Please have a look at this [Jupyter Notebook PDF.](https://drive.google.com/file/d/162sqjfWvnPuxHzr4VQpuCmFcwgcoxBQF/view?usp=sharing)

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

## Question 2:

### (a) How many orders were shipped by Speedy Express in total?
ANSWER: 54


```markdown


```

### (b) What is the last name of the employee with the most orders?
ANSWER: Peacock



### (c) What product was ordered the most by customers in Germany?
ANSWER: Boston Crab Meat

```markdown
SELECT ProductName FROM Products 
WHERE ProductID IN
(SELECT ProductID FROM Orders
LEFT JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID
LEFT JOIN Customers ON Orders.CustomerID = Customers.CustomerID
WHERE Country = 'Germany' 
GROUP BY ProductID
ORDER BY SUM(Quantity) DESC 
LIMIT 1);
```









```markdown



Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ester-tsai/Ester-Tsai-Shopify-Data-Science-Intern-Challenge.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
