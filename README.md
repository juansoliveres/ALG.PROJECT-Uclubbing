# Uclubbing MVP

# Description of the project

This is a repository where we will work in the Uclubbing MVP.
The objective of this project is to design a system which allows to book places at a club, avoiding in that way typical inconvenients or problems experienced by 
people who usually go out, such as long waiting queues to enter the local or realising that the club where you want to enter is completely crowed and the maximum aforum has already been reached. 

# Code description / Usage

In order to design the MVP, we have created a list of possible customers (The clubs contained in the hash table clubs_available) which could use our program. 
We have assigned certain parameters to the clubs chosen. Therefore for each club we will find: total number of tables, price, total capacity (in people) and a user 
grade which has been randomly assigned to each of the clubs.

After creating the hash table and simulating the random user grade the program will welcome the user and ask for some personal information in order to complete the 
reservation (i.e name, time of arrival and number of people in the reservation).
Once the registration is over the program will display the available clubs associated to a number, so the user can choose the club where he wants to do the 
reservation.
Before finishing the reservation the user will have the option to book bottles with the table, which will get a 15% discount in the overall price of the table.
After finishing the process we close the program and thank the user for trusting in Uclubbing. 
