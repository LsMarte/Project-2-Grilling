# Project-2-Grilling
Project build in C++.
You will complete a C++ program 
that runs a circulating grill for 
cooking food at a convenience store. 

Circular Singly-Linked List 
Food items are placed on a circulating grill that moves in a single direction. The grill is 
an instance of class Circulator, which is a template class that stores a particular 
type of value (specified by its template parameter) in a circular, singly-linked list: a 
node contains a pointer to the next node and there is no beginning or end.  See an 
example of the linked list holding letters below. 
As there is no beginning or end, a 
single pointer currP points to 
the “current” position from which 
all others can be reached (due to 
the circularity). Another pointer 
prevP is also maintained since 
removing a node requires access to the preceding node. Note that pointers are always to 
the entire node in pictures, not to a field in a node. 
In class Circulator, you must complete 2 member functions: 
• void insertAfter(const T& val): Adds a value to the list.  The value 
should be placed in a new node after the node pointed to by currP and then the new 
node should become the current one (currP). Be sure to also update prevP 
(required for removal).  For example, see how the list evolves from 0→2 elements 
below, which requires altering multiple pointers. 
New node goes after 
current node (pointed 
to by currP). Pointer 
(currP) advances 
when add a new node. 
prevP also updated. 
• bool remove(): Removes current value from the list (i.e., the node pointed to by 
currP). Drawing shows the 
updated pointers (┄). The node 
after the one removed becomes 
the new current node (currP). 
The old node should be 
deallocated. Return whether there was anything to remove. 
For both operations, deal with any special cases. 
There are completed member functions to get the current value [getCurrent()], to 
circulate the list (move currP) to the next node [advance()], etc. Note that 
getCurrent() returns a pointer to the value in the current node so that you can 
mutate that value. 
Page 2 of 3 
CSI218 – Data Structures and Algorithms – Spring 2025 
Main Program 
Food to grill is stored in a fully-inline class named CookableFood containing an order 
#, item name, and the cooking time left (remaining rounds through grill needed to be 
completely cooked). This class also represents a section of the grill (see diagram first 
page), such that if a CookableFood object’s isEmpty() returns true, then it is an 
empty section. EMPTY_SECTION is a useful constant in that case. 
A map holds names of items on the menu and their standardized cooking times. 
To finish the main program, complete the following: 
• Add code to process orders using the queue object provided. I.e., add new orders to 
this FIFO queue. Then, place queued items on the grill when an empty section comes 
around. See behavior in Sample Run. 
• Complete function maintainGrill(). It should: 
o Move all the food items on the grill to the countertop (use a container class from 
the C++ libraries as the countertop). 
o Remove all the sections of the grill. 
o Add new section to the grill (same numbers as originally in grill). 
o Place the food items back on the grill (one section each). 
o Return the number of food items on the grill. 
