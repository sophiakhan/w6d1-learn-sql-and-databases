### Explorer Mode

__1. How many users are there?__ <br>
_select * from users;_<br>
50<br>

__2. What are the 5 most expensive items?__<br>
_select * from items order by items.price asc limit 5;_<br>
60|Ergonomic Steel Car|Books & Outdoors|Enterprise-wide secondary firmware|9341<br>
40|Sleek Wooden Hat|Music & Baby|Quality-focused heuristic info-mediaries|9390<br>
100|Awesome Granite Pants|Toys & Books|Upgradable 24/7 access|9790<br>
83|Small Wooden Computer|Health|Re-engineered fault-tolerant adapter|9859<br>
25|Small Cotton Gloves|Automotive, Shoes & Beauty|Multi-layered modular service-desk|9984<br>

__3. What's the cheapest book?__<br>
_select * from items where category like '%book%' order by items.price asc limit 1;_<br>
76|Ergonomic Granite Chair|Books|De-engineered bi-directional portal|1496<br>

_select * from items where category = 'Books' order by price asc limit 1;_<br>
No, it does not change. <br>

__4. Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?__<br>
_select user_id from addresses where street like '%6439 Zetta Hills%';_<br>
40<br>

_select * from addresses where user_id like '%40%'_<br>
43|40|6439 Zetta Hills|Willmouth|WY|15029<br>
44|40|54369 Wolff Forges|Lake Bryon|CA|31587<br>

__5. Correct Virginie Mitchell's address to "New York, NY, 10108"__<br>
_select id, first_name from users where first_name like '%Virginie%';_ > 39<br>
_update addresses set city = 'New York', state = 'NY', zip = '10108' where id = 41;_<br>

__6. How much would it cost to buy one of each tool?__<br>
_select sum(price) from items where category like '%tools%';_<br>
46477<br>

__7. How many total items did we sell?__<br>
_select sum(quantity) from orders;_<br>
2125<br>

__8. How much was spent on books?__<br>
_select sum(price) from items where category like '%books%';_<br>
59241<br>

__9. Simulate buying an item by inserting a User for yourself and an Order for that User.__<br>
_insert into users (first_name, last_name, email) values ('Sophie', 'Khan', 'sophiaxkhan@gmail.com');_<br>
_insert into addresses (user_id, street, city, state, zip) values ('51', '2730 Timberly Dr', 'Indianapolis', 'IN', '46220');_
_insert into orders (user_id, item_id, quantity, created_at) values ('51', '99', '100', '00:50:30.000999');_<br>








