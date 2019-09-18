#Exercise 2

##SQL queries

1. Invoices issued after their due date. Return all attributes.
```sql
SELECT * FROM invoice
    WHERE issued > due;
```

2. Invoices that were issued before the date in which the order they refer to was placed.
Return the ID of the invoice, the date it was issued, the ID of the order associated with it
and the date the order was placed.
```sql
SELECT i.id, i.issued, i.order_id, o.date 'order_date'
FROM 'invoice' i
    LEFT JOIN 'order' o ON o.id=i.order_id
    WHERE i.issued < o.date
```

3. Orders that do not have a detail and were placed before 6 September 2016. Return all
attributes.
```sql
SELECT * FROM 'order' o
    OUTER JOIN 'order_has_product' op ON o.id=op.order_id
    WHERE o.date < '2016-09-06'
```

4. Customers who have not placed any orders in 2016. Return all attributes.
```sql
SELECT * FROM 'customer' c
    WHERE c.id NOT IN (
		SELECT o.customer_id FROM 'order' o
		    WHERE YEAR(o.date) = 2016
    )
```

5. ID and name of customers and the date of their last order. For customers who did not
place any orders, no rows must be returned. For each customer who placed more than
one order on the date of their most recent order, only one row must be returned.
```sql

```

6. Invoices that have been overpaid. Observe that there may be more than one payment
referring to the same invoice. Return the invoice number and the amount that should be
reimbursed.
```sql

```

7. Products that were ordered more than 10 times in total, by taking into account the
quantities in which they appear in the order details. Return the product code and the
total number of times it was ordered.
```sql

```

8. Products that are usually ordered in bulk: whenever one of these products is ordered, it
is ordered in a quantity that on average is equal to or greater than 8. For each such
product, return product code and price.
```sql

```

9. Total number of orders placed in 2016 by customers of each country. If all customers
from a specific country did not place any orders in 2016, the country will not appear in
the output.
```sql

```

10. For each order without invoice, list its ID, the date it was placed and the total price of the
products in its detail, taking into account the quantity of each ordered product and its unit
price. Orders without detail must not be included in the answers.
```sql

```
