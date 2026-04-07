Implement Stack using Queues
This problem involves implementing a stack using queue operations. 
The solution uses a single queue to simulate stack behavior. When pushing an element,
it is added to the queue, and then all previously existing elements are rotated behind
it. This ensures that the most recently added element is always at the front of the queue
, mimicking the LIFO behavior of a stack. The pop operation simply removes the front element,
and top returns the front element without removing it. The empty method checks if the queue is
empty. This approach achieves correct stack functionality using only queue operations with O(n) push time complexity.

CODE:
import java.util.*;

class MyStack {
    private Queue<Integer> queue;

    public MyStack() {
        queue = new LinkedList<>();
    }

    public void push(int x) {
        queue.offer(x);
        int size = queue.size();
        
        for (int i = 0; i < size - 1; i++) {
            queue.offer(queue.poll());
        }
    }

    public int pop() {
        return queue.poll();
    }

    public int top() {
        return queue.peek();
    }

    public boolean empty() {
        return queue.isEmpty();
    }
}
