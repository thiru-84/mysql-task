#OUTPUT IMAGES ARE ATTACHED AS A WORD DOCUMENT WITH THEIR QUESTIONS.#

-------------------------------------------------------------------------------------------------------
Qs 1: Retrieve all customers who have placed an order in the last 30 days.

•	select * from orders where order_date >= curdate() - interval 30 day;

-------------------------------------------------------------------------------------------------------
Qs 2: Get the total amount of all orders placed by each customer.

•	select customers.name, sum(orders.total_amount) as total_spent
from customers 
join orders on customers.customer_id = orders.customer_id
group by customers.customer_id;

-------------------------------------------------------------------------------------------------------
Qs 3: Update the price of Product C to 45.00.

•	update products set price = 45.00 where name = 'Product C';

-------------------------------------------------------------------------------------------------------
Qs 4: Add a new column discount to the products table.

•	alter table products add column discount decimal(10,2) default 0.00;

-------------------------------------------------------------------------------------------------------	
Qs 5: Retrieve the top 3 products with the highest price.

•	select * from products order by price desc limit 3;

-------------------------------------------------------------------------------------------------------
Qs 6: Get the names of customers who have ordered Product A.
•	select distinct customers.name  
from customers  
join orders on customers.customer_id = orders.customer_id  
join order_items on orders.id = order_items.order_id  
join products on order_items.product_id = products.id  
where products.name = 'Product A';

-------------------------------------------------------------------------------------------------------  
Qs 7: Join the orders and customers tables to retrieve the customer's name and order date for each order.
•	select customers.name, orders.order_date  
from customers  
join orders on customers.customer_id = orders.customer_id;

------------------------------------------------------------------------------------------------------- 
Qs 8: Retrieve the orders with a total amount greater than 150.00.
•	select * from orders  where total_amount > 150.00;
 
-------------------------------------------------------------------------------------------------------	
Qs 9: Normalize the database by creating a separate table for order items and updating the orders table to reference the order_items table.
•	select * from orders  where total_amount > 150.00;
 
-------------------------------------------------------------------------------------------------------
Qs 10: Retrieve the average total of all orders.
•	select avg(total_amount) as average from orders;

 
