```python
---Creating a database called Superstore and importing the well known superstore data into it---
create database Superstore
use Superstore
```


```python
---SQL distinct statement---
select distinct [Category]
from Orders

select distinct [Sub-Category]
from Orders
```


```python
---SQL AND statement: both statement must true to produce the output---
select *
from Orders
where city='Los Angeles' and State='California'
```


```python
---SQL OR statement: one must true to produce the output---
select *
from Orders
where city='Los Angeles' OR State='California'
```


```python
---SQL IN statement ---
select *
from Orders
where city IN ('Los Angeles','Seattle','Chicago')
```


```python
--SQL NOT statement---
select *
from Orders
where not city='Los Angeles'
```


```python
--SQL BETWEEN statement---
select [Customer Name],[Order ID], [Quantity]
from Orders
where [Quantity] between 5 and 9
```


```python
---Selecting Specific Colums---
select [Customer Name],[City],[Sales],[Quantity],[Profit]
from Orders
```


```python
---Computing Total Sales Per Customer before discount----
select [Customer Name], ([Sales]*[Quantity]) AS Total_Sales
from Orders

```


```python
---Computing Total Sales after discount Per Customer---
select [Customer Name],
([Sales]*[Quantity]-([Discount]*([Sales]*[Quantity]))) AS Discount_Sales
from Orders
```


```python
---Computing Cost Price Per Customer---
select [Customer ID],
(([Sales]*[Quantity]-([Discount]*([Sales]*[Quantity])))-[Profit]) AS Cost_Price
from Orders
```


```python
---Computing Profit Margin Per Customer---
select [Customer Name],
([Profit] / ([Sales]*[Quantity]-([Discount]*([Sales]*[Quantity])))) AS Profit_Margin
from Orders
```


```python
---Generating the TOP 10 customer with the most sales---
select TOP 10 [Customer Name], max(sales*quantity) AS Total_Sales
from Orders
group by [Customer Name]
Order by Total_Sales DESC
```


```python
---Generating TOP 5 customers with the most profit---
select TOP 5 [Customer Name],[Profit]
from Orders
group by [Customer Name],[Profit]
Order by [Profit] DESC
```


```python
---Generating TOP 5 customers with the most loss---
select TOP 5 [Customer Name],[Profit]
from Orders
group by [Customer Name],[Profit]
Order by [Profit] ASC
```


```python
---Generating all customers with no profit or loss---
select [Customer Name],[Profit]
from Orders
where profit=0
```
