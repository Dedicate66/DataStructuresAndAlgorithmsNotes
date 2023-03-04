# Data Structures and Algorithms Notes

1. Basic data structures
2. Big O notation
3. Searching algorithms
4. Sorting algorithms
5. Graphs
6. Trees
   
## 1. What are data structures and algorithms?
**Data Structure:** a named location that can be used to store and organize data.

**Alogorithm:** a collection of steps to solve a problem.

## 2. Stacks
**stack** = LIFO data structure. Last-in First-Out
``` java
// push() to add on the top
// pop() to remove from the top
import java.util.Stack;

public class Main {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();
        stack.push("Minecraft");
        stack.push("Doom");
        stack.push("Boarderlands");
        stack.push("LOl");  // Stack后进先出
        System.out.println(stack);

        for (int i = 0; i < 1000000000; i++) {
            stack.push("Doom");
        }
    }
}

```
### Uses of stacks?
1. undo/redo features in text editors
2. moving back/forward through browser history
3. backtracking algorithms (maze, file directories) // maze迷宫，file directories文档目录
4. calling functions (call stack)
   
## 3. Queues
**Queue** = FIFO data structure. First-In First-Out 
A collection designed for holding elements prior to processing 
**linear data structure**

```java
Queue<String> queue = new LinkedList<String>();
queue.enqueue

// add = enqueue, offer()   // add to the tail
// remove = dequeue, poll()    // remove from the head

import java.util.LinkedList;
import java.util.Queue;
import java.util.Stack;

public class Main {
    public static void main(String[] args) {
        Queue<String> queue = new LinkedList<String>();

        queue.offer("Karen");   // enqueue
        queue.offer("Chad");
        queue.offer("Steve");
        queue.offer("Harold");

        System.out.println(queue.peek());
        queue.poll();   // dequeue
        System.out.println(queue.peek());   // [Chad, Steve, Harold]
        System.out.println(queue.element());    // element() : Retrieves, but does not remove, the head of this queue, or returns null if this queue is empty.
                                                // Returns: the head of this queue, or null if this queue is empty
        System.out.println(queue.isEmpty());
        System.out.println(queue.size());
        System.out.println(queue.contains("Harold"));

    }
}

```

### Where are queues usefull?
1. Keyboard Buffer (letters should appear on the screen in the order they're pressed)
2. Printer Queue (Print jobs should be completely in order)
3. Used in LinkedLists, PriorityQueues, Breadth-first search

## Priority Queues

**Priority Queue** = FIFO(First-In First-Out ) data structure that serves elements with the **highest priority** first before lower priority.

``` java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Queue<String> queue = new PriorityQueue<>(Collections.reverseOrder());
        // 正常是按字母顺序输出 A～Z
        // reverse后 Z～A

        queue.offer("B");
        queue.offer("C");
        queue.offer("A");
        queue.offer("F");
        queue.offer("D");

        while (!queue.isEmpty()){
            System.out.println(queue.poll());

        }


    }
}

```

## 5. LinkedLists
**LinkedList** = stores Nodes in 2 parts (data + address)
Nodes are in non-consecutive memory locations
Elements are linked using **printers**

### Advantages
1. Dynamic Data Structure (allocates needed memory while running)   // allocate 分配
2. Insertion and Deletion of Nodes is easy. O(1)
3. No/Low memory waste

### Disadvantages
1. Greater memory usage (additional pointer)
2. No random access of elements (no index [i])      // to find an element, we need to begin at one end towards the other end
3. Accessing/searching elements is more time consuming. O(n)

### Uses
1. implement stacks/Queues
2. GPS navigation
3. music playlist

### Varieties
#### 1. singly ~
![Alt text](IMG_A00DDFC4443C-1.jpeg)

**Benefits：**
1. ArrayLists: Inserting & Deleting are very difficult
2. 不连续 each node has the address of where the next node resigns
3. Insert node步骤：
   1. 把previous node里的address放到新node里 --> 新node指向了next node
   2. 把previous node的address改成新node的address
4. Delete node步骤：
   1. 把previous node的address指向next node的adress即可

#### 2. doubly ~
![Alt text](Pictures/IMG_63327E029FEB-1.jpeg)
**Benefits:**
1. 从前从后都行（双向）
**Downside**
1. use more memory then singly LinkedList
   
``` java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> linkedList = new LinkedList<String>();   // Doubly
        /*linkedList.push("A");
        linkedList.push("B");
        linkedList.push("C");
        linkedList.push("D");
        linkedList.push("E");
        linkedList.push("F");*/

        linkedList.offer("A");
        linkedList.offer("B");
        linkedList.offer("C");
        linkedList.offer("D");
        linkedList.offer("E");
        linkedList.offer("F");
        // linkedList.poll();

        linkedList.add(4,"HAHA");
        linkedList.remove("E");

        System.out.println(linkedList.indexOf("F"));
        System.out.println(linkedList.peekFirst());
        System.out.println(linkedList.peekLast());
        linkedList.addFirst("First");
        linkedList.addLast("Last");
        
        
        System.out.println(linkedList);





    }
}


```






