# Code Explanation 

This file mimics the course page in which the assembly program of `linked list` is explained.

> Before start of code

A linked list is a simple data structure. The linked list contains elements containing a value (some kind of data) and a pointer to another element. The pointer is the address of the other element. The elements are arranged in a list so that each element has a successor given by the pointer. The head of the list is the pointer to the first element of the list. The end of the list is given by an element without a successor and usually the zero for the pointer. 

Let us consider a list with two elements with values 0ⅹ32 and 0ⅹ12. The first element is located in memory at address 0ⅹ32c0, and the second element is at address 0ⅹ32a0. Each element contains its value and a pointer to the successor or zero. The head of the list points to the first element at address: head = 0ⅹ32c0:


| Address  | Value  | Pointer |
|:---------|:-------|:--------|
| 0x32c0   |  0x32  |  0x32a0 |
| 0x32a0   |  0x12  |  0x0000 |

The easiest way of inserting an element into the list is to push it at the head. The memory for each element has to be allocated. Usually, this is done dynamically using the heap memory. The removal of an element from the head (pop) has to free the allocated memory. The C functions __malloc__ and __free__ can be used for the memory (de)allocation using the heap memory.

An element of the list in assembly language can be achieved by offsets which give access to the value and the next element. This is done in this file:

> __linkedlist_struct.s__

The linked list has three functions in the example. Insert/push an element to the list, remove/pop an element from the list and print the list from head to end. Push generates a new element, the previous head pointer becomes the element’s successor, and the head points to the new element. Pop inverts this, the head pointer becomes the head element’s successor, and the previous head element is removed. The print function moves over each element.

> __linkedlist.s__

The usage of the linked list is shown in the main function. Elements are inserted, removed, and the list is printed. 

> __main.s__


*End of Document*