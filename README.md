__1. How many users are there?__
_select * from users;_
50

__2. What are the 5 most expensive items?__
_select * from items order by items.price asc;_
60|Ergonomic Steel Car|Books & Outdoors|Enterprise-wide secondary firmware|9341
40|Sleek Wooden Hat|Music & Baby|Quality-focused heuristic info-mediaries|9390
100|Awesome Granite Pants|Toys & Books|Upgradable 24/7 access|9790
83|Small Wooden Computer|Health|Re-engineered fault-tolerant adapter|9859
25|Small Cotton Gloves|Automotive, Shoes & Beauty|Multi-layered modular service-desk|9984

__3. What's the cheapest book?__
_select * from items where category like '%book%' order by items.price asc;_
76|Ergonomic Granite Chair|Books|De-engineered bi-directional portal|1496

HOLD PLACE FOR EXACTLY BOOKS.

__4. Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?__
_select user_id from addresses where street like '%6439 Zetta Hills%';_
40

_select * from addresses where user_id like '%40%'_
43|40|6439 Zetta Hills|Willmouth|WY|15029
44|40|54369 Wolff Forges|Lake Bryon|CA|31587

__5. Correct Virginie Mitchell's address to "New York, NY, 10108"__
_select id, first_name from users where first_name like '%Virginie%';_ 39
_update addresses set city = 'New York' where id = 39;_
_update addresses set state = 'NY' where id = 39;_
_update addresses set zip = '10108' where id = 39;_

__6. How much would it cost to buy one of each tool?__
_select sum(price) from items where category like '%tools%';_
46477

__7. How many total items did we sell?__
_select sum(quantity) from orders;_
2125

__8. How much was spent on books?__
_select sum(price) from items where category like '%books%';_
59241

__9. Simulate buying an item by inserting a User for yourself and an Order for that User.__
_insert into users (first_name, last_name, email) values ('Sophie', 'Khan', 'sophiaxkhan@gmail.com');_
_insert into addresses (user_id, street, city, state, zip) values ('51', '2730 Timberly Dr', 'Indianapolis', 'IN', '46220');_
_insert into orders (user_id, item_id, quantity, created_at) values ('51', '99', '100', '00:50:30.000999');_






