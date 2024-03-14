---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - dsa
Creation Date: 2023-10-08T20:10:00
Last Date: 2024-03-12T12:20:26+08:00
References: 
---
## Abstract
---
- A [[Data Structure#Linear]] collection of elements of the same [[Datatype]] that are stored in [[Data Structure#Continuous Memory]]. The next node is obtained by adding a **constant value** to the [[Memory Address]] of current node
- Can be used to implement [[Hash Map]] when keys are fixed
- [Leetcode questions](https://github.com/youngyangyang04/leetcode-master#%E6%95%B0%E7%BB%84)

>[!caution] Fixed Size
> If we want to expand, we have to create another bigger array & **copy all the elements** to the new array which is very time consuming 

>[!attention] Element Removal
> We can't delete elements in arrays, we can only overwrite

### Time Complexity 
>[!note]- Search
> $O(1)$ to search for a value.

>[!note]- Indexing
> It is $O(1)$  to index any elements in an array. The indexing formula is `elementAddr = firtstElementAddr + elementLength * elementIndex`, `elementIndex` is $0$ when we try to access the first element

>[!note]- Insert, Delete
> $O(1)$ at the 2 ends of the array
> 
> $O(n)$ in the middle of the array
> - For insert, we have to move all the elements next to the new element one step to right
> - For delete, we have move all element next to the deleted element one step to left

>[!info]- Performance comparison with Linked List when going through all elements
> Array is much faster if there is [[CPU Cache]], otherwise it will be slightly slower. Because Array has to calculate the address of the next element, while [[Linked List]] is already calculated.
> 
> The reason why array is faster with CPU Cache is because array is stored in a [[Data Structure#Continuous Memory]] manner. Thus array is able to take advantage of [[CPU Cache#Cache Locality]]

### Contiguous Segment
- A continuous range of [[Array]]


## Dynamic Array
---
- Also known as **List**
- Resizable [[Array]], achieved by building an [[Abstraction (抽象)]] above the Array


>[!tip] Convenient
> Developers don't need to re-write battle-tested logic of re-sizeing Array etc, battery-packed with best practices.

>[!attention] More Resource Intense
> We can't fine tune every Array operations because the implementation details are abstracted away. We only have a limited interface to interact with it.

## Circular Array
---
- Connect the start and end of the [[Array]] to form a loop
- With taking remainder from ``frontIndex % arrayCapacity``, we are able to implement circular array on an array. Take a look at [Visual](https://www.hello-algo.com/chapter_stack_and_queue/queue/#2) for better understanding
- Used to implement [[Queue (FIFO)#Implementation|Queue]]

>[!info] Front Index
> A variable to keep track the index for the start of the circular array.

>[!info] Rear Index
> A variable to keep track the index of the slot after the last element of the circular array, Can be obtained with `frontIndex + arraySize`.