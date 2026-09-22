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
#Non-Functional
#
1. low latency : system must process validation the order with rsponse time of 100ms at least 98% of request 
2.   strong consistency : strict ACID in   complain immediate database replacementare required for  validation the order

3. eventaul consistency : asyncrounce  synchronization is allowed for decide robot that select  within maximum windows of4 secondsc to priotize  high avialbiltiy and read speed
#Core Entities
#User
Order
Items
Location 
Notification
Robots

