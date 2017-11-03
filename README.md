# Illumio-Coding-Challenge
My submission for the Illumio Intern Coding Assigment.

# Testing:
For testing my solution, I ran various tests on the given input examples as well additional ones. The main thing that I wanted to test was making sure that the program still worked for the case when there was a range in the port and also the ipAddress. For the other less edge cases, I tested my solution on different inputs. These can be found here.

# Implementation decisions:
For this assigment there were many special implementation decisions that I had to take into account in relations to the space and time complexity. I decided that the most run time efficient way of storing all the different Network rules would be to simply create a Hashtable with all the different unique Network Rules maped to whether they existed or not. This leads to O(1) run time, but severly hurts the space time complexety when there were ranges of ports/ipAddresses. In order to be able to deal with sometimes the port having a range, or the ipAddress sometimes having a range, and not having a clear hash key to uniquely store each value, I decided to create a NetworkRule object. With this object, I created a new HashKey for each of them which utalizes all the different components (direction, protocol, port, ipAddress) and a prime number to create a unique long hash key. This can then be used to store each Network Rule uniquely on the hash map. One thing to note is that this is a long, not an int, as even an ipAddress of 255.255.255.255 would overflow an int hash value.

# More time optimizations/refinements:
If I had more time, I would try to use another data structure/modify a hashmap to store all the Network Rules. With my implementation using a simple hash table, the space complexity increases significantly as the more network rules with ranges of ports/ipAddress are added. Using another data structure, such as a NavigableMap, which can store ranges of numbers as key, would significantly decrease the space complexity, but increase the searching to O(logn). At the same time, making the change to this data structure would mean redefining what a key looks like and how exactly to divide up for a given range. Implementing with this data structure would only yield to be better if space is truly a limiting factor, and the input appeared to have more ranges than just uniques. 

# Teams:
I would be more interested on the Platform team, but they all sound great :)
