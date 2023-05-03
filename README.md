Download Link: https://assignmentchef.com/product/solved-cs1332-homework2-stacks-and-queues
<br>
You are to code the following:

<ol>

 <li>A Stack backed by a singly-linked list without a tail reference.</li>

 <li>A Stack backed by an array</li>

 <li>A Queue backed by a singly-linked list with a tail reference</li>

 <li>A Queue backed by an array</li>

</ol>

A Stack is a last-in, first-out (LIFO) data structure; the last item to be inserted is the first item to be removed. A Queue is a first-in, first-out (FIFO) data structure; the first item inserted is the first item to be removed.

All your data structures must follow the requirements stated in the javadocs of each method you must implement.

Note that the linked versions of the data structures should <strong>NOT </strong>be circular.

<h2>Capacity</h2>

The starting capacity of the array classes should be the constant INITIAL CAPACITY defined in the .java files. Reference the constant as-is. Do <strong>not </strong>simply copy the value of the constant. Do <strong>not </strong>change the constant. If, while adding an element, the array class does not have enough space, you should regrow the backing array to <strong>twice </strong>its old capacity. In other words, after one resize, the backing array’s length should be INITIAL CAPACITY * 2, and after two resizes, it should be INITIAL CAPACITY * 2 * 2. Do <strong>not </strong>resize the backing array when removing elements.

<h2>Removing</h2>

With both array classes, when elements are deleted from the array, the index the element was removed from should be set to null. <strong>All unused positions in the backing array must be set to </strong>null<strong>.</strong>

<h2>Circular Arrays</h2>

The backing array in your ArrayQueue implementation <strong>must behave circularly</strong>. This means the front variable might wraparound to the beginning when you remove to take advantage of empty space while maintaining <em>O</em>(1) efficiency for all operations.

For this assignment, the front variable in ArrayQueue should represent the index that holds the next element to dequeue. <strong>Failure to follow this convention will result in major loss of points.</strong>

For enqueuing, add to the back of the queue. To access the back of the queue, you can add the size to the front variable to get the next index to add to, though you will have to account for the circular behavior yourself. If there are empty spaces at the front of the array, the back of the queue should wrap around to the front of the array and make use of those spaces.

For dequeuing, you should simply treat the next index in the array as the new front. <strong>Do not shift any elements during a remove.</strong>

When resizing the backing array, “unwrap” the data. Realign the queue with the front of the new array during the transfer. The front variable of the queue is once again at index 0.

Additionally, after removing the last element in the queue, move the front variable like you normally would. Do <strong>not </strong>explicitly reset it to 0. This effectively means that going from size 1 to size 0 should not be a special case for your code.

The examples below demonstrate what the queue should look like at various states.

In the example below, the queue begins empty (initial state). An element is added.

In the example below, adding to the back causes the newly added element to wrap around to the front.

In the example below, adding another element causes the queue to resize. The array capacity is doubled and the front element moves to index 0.

In the example below, the last element of the queue is removed, but front moves as expected. The front variable is not explicitly set to 0.