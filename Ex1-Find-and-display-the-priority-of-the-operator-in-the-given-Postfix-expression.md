1. You are implementing a RecentCounter class that counts the number of recent calls within a sliding window of 3000 milliseconds. Each time you receive a new ping(t) at time t, you need to return the number of calls that occurred in the inclusive range [t - 3000, t]. Calls are guaranteed to be strictly increasing in time
2.  Design a program that: Takes a string input representing a message. Removes all non-alphanumeric characters (e.g., commas, spaces, symbols). Converts all characters to lowercase. Uses a deque to check whether the cleaned string is a palindrome.

3.      In a smart home, each appliance sends power consumption readings to the central controller every minute. The system must detect power surges — defined as a time window of 5 minutes (i.e., 5 readings) where all readings are above a threshold value (say 1000W). If such a surge is detected, an alert must be triggered. Your task is to implement a monitoring system using a deque that: Continuously stores the last 5 readings. Checks after each new reading if all 5 readings in the deque are > threshold.  If so, prints "⚠️ Power Surge Detected". Otherwise, prints "✅ Normal".

4.      You are given a Java program that defines a queue data structure using a singly linked list. The implementation involves two classes:
Node class: Represents a single element in the queue with two fields:
data: stores the integer value
next: points to the next node
Queue class: Provides methods to perform the following operations:
enqueue(int new_data): To perform insertion of a new element at the rear of the queue.
dequeue(): To perform deletion of the front element from the queue.
isEmpty(): To check if the queue is empty.
printQueue(): To display the current elements of the queue after every enqueue or dequeue operation.


## program 1

```
    import java.util.*;

class RecentCounter {
    Queue<Integer> q;

    public RecentCounter() {
        q = new LinkedList<>();
    }

    public int ping(int t) {
        q.add(t);
        // Remove pings older than t - 3000
        while (q.peek() < t - 3000) {
            q.poll();
        }
        return q.size();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        RecentCounter rc = new RecentCounter();
        int n = sc.nextInt(); // number of pings
        for (int i = 0; i < n; i++) {
            int t = sc.nextInt();
            System.out.println(rc.ping(t));
        }
    }
}
```

## program 2:
```
  import java.util.*;

public class PalindromeChecker {
    public static boolean isPalindrome(String s) {
        Deque<Character> deque = new ArrayDeque<>();

        // Remove non-alphanumeric and convert to lowercase
        for (char c : s.toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                deque.add(Character.toLowerCase(c));
            }
        }

        // Check palindrome using deque
        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast()) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();

        if (isPalindrome(input))
            System.out.println("Palindrome");
        else
            System.out.println("Not Palindrome");
    }
}
```

## program 3:

```
import java.util.*;

public class PowerSurgeMonitor {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Deque<Integer> readings = new ArrayDeque<>();

        int threshold = 1000;
        int windowSize = 5;
        int n = sc.nextInt(); // total readings

        for (int i = 0; i < n; i++) {
            int reading = sc.nextInt();
            readings.addLast(reading);

            // Maintain only the last 5 readings
            if (readings.size() > windowSize) {
                readings.removeFirst();
            }

            // Check for surge
            if (readings.size() == windowSize && allAboveThreshold(readings, threshold)) {
                System.out.println("⚠️ Power Surge Detected");
            } else {
                System.out.println("✅ Normal");
            }
        }
    }

    // Helper method to check if all readings exceed threshold
    private static boolean allAboveThreshold(Deque<Integer> readings, int threshold) {
        for (int r : readings) {
            if (r <= threshold) {
                return false;
            }
        }
        return true;
    }
}
```

## program 4:

```
import java.util.*;

class Node {
    int data;
    Node next;

    Node(int d) {
        data = d;
        next = null;
    }
}

class Queue {
    Node front, rear;

    Queue() {
        front = rear = null;
    }

    // Check if queue is empty
    boolean isEmpty() {
        return front == null;
    }

    // Enqueue operation — insert at rear
    void enqueue(int new_data) {
        Node newNode = new Node(new_data);

        if (rear == null) {
            front = rear = newNode;
        } else {
            rear.next = newNode;
            rear = newNode;
        }
        System.out.print("After Enqueue " + new_data + ": ");
        printQueue();
    }

    // Dequeue operation — remove from front
    void dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot dequeue.");
            return;
        }

        int removed = front.data;
        front = front.next;

        if (front == null)
            rear = null;

        System.out.print("After Dequeue " + removed + ": ");
        printQueue();
    }

    // Print all elements in the queue
    void printQueue() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return;
        }

        Node temp = front;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class LinkedListQueueDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Queue q = new Queue();

        int n = sc.nextInt(); // number of operations
        for (int i = 0; i < n; i++) {
            String op = sc.next();
            if (op.equals("enqueue")) {
                int val = sc.nextInt();
                q.enqueue(val);
            } else if (op.equals("dequeue")) {
                q.dequeue();
            }
        }
    }
}
```
