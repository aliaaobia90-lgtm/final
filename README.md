# final
Back-Of-The-Envelope Estimation
DUA = 
The Approach

Requirements
Functional
users can create & update an account
users can login 
Users can search product 
USER can add && remove product from the cart 
User can submite the order 
User can track the order 
system receives orders
system validates the order 
 system makes sure the same order is never processed twice
system checks that every item is available and reserves it.
system  prevent overselling
system decides how many robots are needed to collect 
system returns a list of robots with the items assigned to each one
The system sends pick tasks to the assigned robots and follows their progress
system must handle robot failures 
 if order is fully collected he system moves the order to the packing station and then to shipping
 system notifies operators about  low stock, a robot failure, a delayed order, or a robot with a low battery


API




























Non-Functional
POST /auth/ register  ---> user-Id
{ name, email , password}
POST/User/login --->token{
email, password
}
Get/ Items ---> Items[]{id_items  , name,  price }
Post/Items/ ---> item_id {Name ,price , size , weight }
PATCH/Cart/  ---> 200{}
POST/Orders --->OrderId{ id_items []  , location_user }
Get / Order/order_id---> { order_location}
Get/order/ {order id}/ --->id_items []{}
Post/order/ {order id}/ user--->409{order_Id}
Post /Robots/{robot_id} → 200     {item_id}

 



1. low latency : system must process validation the order with rsponse time of 100ms at least 98% of request 
2.   strong consistency : strict ACID in   complain immediate database replacementare required for  validation the order

3. eventaul consistency : asyncrounce  synchronization is allowed for decide robot that select  within maximum windows of4 secondsc to priotize  high avialbiltiy and read speed
Core Entities
User
Order
Items
Location 
Notification
Robots


Message Queue
Notification Service
Location 
GPS
Robot Service
Primary DB
items, robots ,
Data Model
API Gateway
Load Balancer
Routing 
Authentication
SSL terminaion 
Rate Limiting
User
Web/App
Order Service
Items

item_id
name
location_id
size 
weight
price
Search  DB
location, order ,
Order 
order_id
item_id[]
user_id
validation
total_price
order_location
Amazon_
System

Match items
User
ID
Email 
Password 
Order_id
location

Robots
robot_id
location_id
capacity

Cache
vaildation service
Notification
Notification_ID
User_ID
Type
Message

Location
location_id

