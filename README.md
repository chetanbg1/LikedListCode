# LikedListCode
1. Create a singly linked list and print its elements
java
Copy
Edit
class Node {
    int data;
    Node next;
    Node(int d) { data = d; next = null; }
}

class LinkedListDemo {
    Node head;

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedListDemo list = new LinkedListDemo();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.printList();  // Output: 1 2 3
    }
}
2. Insert a node at the beginning of a singly linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        newNode.next = head;
        head = newNode;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.insertAtBeginning(3);
        list.insertAtBeginning(2);
        list.insertAtBeginning(1);
        list.printList();  // Output: 1 2 3
    }
}
3. Insert a node at the end of a singly linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = newNode;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.insertAtEnd(1);
        list.insertAtEnd(2);
        list.insertAtEnd(3);
        list.printList();  // Output: 1 2 3
    }
}
4. Insert a node after a given node in singly linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void insertAfter(Node prevNode, int data) {
        if (prevNode == null) {
            System.out.println("Previous node cannot be null");
            return;
        }
        Node newNode = new Node(data);
        newNode.next = prevNode.next;
        prevNode.next = newNode;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(4);
        list.head.next = second;
        second.next = third;

        list.insertAfter(second, 3);
        list.printList();  // Output: 1 2 3 4
    }
}
5. Delete a node by key (value) in singly linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void deleteNode(int key) {
        Node curr = head, prev = null;
        if (curr != null && curr.data == key) {
            head = curr.next; // delete head
            return;
        }
        while (curr != null && curr.data != key) {
            prev = curr;
            curr = curr.next;
        }
        if (curr == null) return; // key not found
        prev.next = curr.next;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.deleteNode(2);
        list.printList();  // Output: 1 3
    }
}
6. Find length of singly linked list (iterative)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    int length() {
        int count = 0;
        Node curr = head;
        while (curr != null) {
            count++;
            curr = curr.next;
        }
        return count;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(10);
        list.head.next = new Node(20);
        list.head.next.next = new Node(30);
        System.out.println("Length: " + list.length());  // Output: Length: 3
    }
}
7. Find length of singly linked list (recursive)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    int length(Node node) {
        if (node == null) return 0;
        return 1 + length(node.next);
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(10);
        list.head.next = new Node(20);
        list.head.next.next = new Node(30);
        System.out.println("Length: " + list.length(list.head));  // Output: Length: 3
    }
}
8. Search for an element in singly linked list (iterative)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    boolean search(int key) {
        Node curr = head;
        while (curr != null) {
            if (curr.data == key) return true;
            curr = curr.next;
        }
        return false;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        System.out.println(list.search(2)); // true
        System.out.println(list.search(4)); // false
    }
}
9. Search for an element in singly linked list (recursive)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    boolean search(Node node, int key) {
        if (node == null) return false;
        if (node.data == key) return true;
        return search(node.next, key);
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        System.out.println(list.search(list.head, 3)); // true
        System.out.println(list.search(list.head, 4)); // false
    }
}
10. Reverse a singly linked list (iterative)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void reverse() {
        Node prev = null;
        Node curr = head;
        Node next;
        while (curr != null) {
            next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        head = prev;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.reverse();
        list.printList(); // Output: 3 2 1
    }
}
11. Reverse a singly linked list (recursive)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node reverseRecursive(Node node) {
        if (node == null || node.next == null) return node;
        Node rest = reverseRecursive(node.next);
        node.next.next = node;
        node.next = null;
        return rest;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.head = list.reverseRecursive(list.head);
        Node curr = list.head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        // Output: 3 2 1
    }
}
12. Detect loop in a singly linked list (Floyd’s Cycle detection)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    boolean hasLoop() {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        list.head.next = second;
        second.next = third;
        third.next = second; // loop here
        System.out.println(list.hasLoop()); // true
    }
}
13. Remove loop from a linked list if present
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void removeLoop() {
        Node slow = head, fast = head;
        boolean loopExists = false;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) {
                loopExists = true;
                break;
            }
        }
        if (!loopExists) return;
        slow = head;
        while (slow.next != fast.next) {
            slow = slow.next;
            fast = fast.next;
        }
        fast.next = null;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        list.head.next = second;
        second.next = third;
        third.next = second; // loop here
        list.removeLoop();
        System.out.println(list.hasLoop()); // false
    }

    boolean hasLoop() {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }
}
14. Find middle element of a linked list (slow and fast pointers)
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    int getMiddle() {
        if (head == null) return -1;
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow.data;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.head.next.next.next = new Node(4);
        list.head.next.next.next.next = new Node(5);
        System.out.println(list.getMiddle()); // 3
    }
}
15. Find nth node from the end of linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    int getNthFromEnd(int n) {
        Node mainPtr = head, refPtr = head;
        int count = 0;
        while (count < n) {
            if (refPtr == null) return -1;
            refPtr = refPtr.next;
            count++;
        }
        while (refPtr != null) {
            mainPtr = mainPtr.next;
            refPtr = refPtr.next;
        }
        return mainPtr.data;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(10);
        list.head.next = new Node(20);
        list.head.next.next = new Node(30);
        list.head.next.next.next = new Node(40);
        list.head.next.next.next.next = new Node(50);
        System.out.println(list.getNthFromEnd(2)); // 40
    }
}
16. Remove duplicates from a sorted linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void removeDuplicates() {
        Node curr = head;
        while (curr != null && curr.next != null) {
            if (curr.data == curr.next.data) {
                curr.next = curr.next.next;
            } else {
                curr = curr.next;
            }
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(10);
        list.head.next = new Node(10);
        list.head.next.next = new Node(20);
        list.head.next.next.next = new Node(30);
        list.head.next.next.next.next = new Node(30);
        list.removeDuplicates();
        list.printList(); // 10 20 30
    }
}
17. Delete alternate nodes in linked list
java
Copy
Edit
class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    void deleteAlternateNodes() {
        Node curr = head;
        while (curr != null && curr.next != null) {
            curr.next = curr.next.next;
            curr = curr.next;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.head.next.next.next = new Node(4);
        list.head.next.next.next.next = new Node(5);
        list.deleteAlternateNodes();
        list.printList(); // 1 3 5
    }
}
18. Convert binary number in linked list to decimal

class LinkedList {
    Node head;

    static class Node {
        int data;  // 0 or 1
        Node next;
        Node(int d) { data = d; next = null; }
    }

    int binaryToDecimal() {
        int num = 0;
        Node curr = head;
        while (curr != null) {
            num = (num << 1) | curr.data;
            curr = curr.next;
        }
        return num;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(0);
        list.head.next.next = new Node(1);
        System.out.println(list.binaryToDecimal()); // 5
    }
}
1. Create and print a Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.printList();  // Output: 10 20 30
    }
}
2. Insert node at the beginning in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head != null) {
            head.prev = newNode;
        }
        newNode.next = head;
        head = newNode;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.insertAtBeginning(30);
        dll.insertAtBeginning(20);
        dll.insertAtBeginning(10);
        dll.printList();  // Output: 10 20 30
    }
}
3. Insert node at the end in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.prev = curr;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.insertAtEnd(10);
        dll.insertAtEnd(20);
        dll.insertAtEnd(30);
        dll.printList();  // Output: 10 20 30
    }
}
4. Delete a node from Doubly Linked List by value
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void deleteNode(int key) {
        Node curr = head;
        while (curr != null && curr.data != key) {
            curr = curr.next;
        }
        if (curr == null) return; // not found

        if (curr.prev != null) {
            curr.prev.next = curr.next;
        } else {
            head = curr.next;  // deleting head
        }
        if (curr.next != null) {
            curr.next.prev = curr.prev;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.deleteNode(20);
        dll.printList();  // Output: 10 30
    }
}
5. Reverse a Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void reverse() {
        Node temp = null;
        Node curr = head;

        while (curr != null) {
            temp = curr.prev;
            curr.prev = curr.next;
            curr.next = temp;
            curr = curr.prev;
        }
        if (temp != null) head = temp.prev;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.reverse();
        dll.printList();  // Output: 3 2 1
    }
}
6. Create and print a Circular Singly Linked List
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        cll.head.next = second;
        second.next = third;
        third.next = cll.head; // Circular link
        cll.printList();  // Output: 1 2 3
    }
}
7. Insert node at end in Circular Singly Linked List
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            head.next = head;
            return;
        }
        Node curr = head;
        while (curr.next != head) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.next = head;
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.insertAtEnd(1);
        cll.insertAtEnd(2);
        cll.insertAtEnd(3);
        cll.printList();  // Output: 1 2 3
    }
}
8. Delete a node from Circular Singly Linked List by key
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    void deleteNode(int key) {
        if (head == null) return;
        Node curr = head, prev = null;

        // If head is to be deleted
        if (head.data == key) {
            // Find last node to update its next pointer
            Node last = head;
            while (last.next != head) {
                last = last.next;
            }
            if (head.next == head) { // only one node
                head = null;
            } else {
                last.next = head.next;
                head = head.next;
            }
            return;
        }

        prev = head;
        curr = head.next;
        while (curr != head && curr.data != key) {
            prev = curr;
            curr = curr.next;
        }
        if (curr.data == key) {
            prev.next = curr.next;
        }
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.insertAtEnd(1);
        cll.insertAtEnd(2);
        cll.insertAtEnd(3);
        cll.deleteNode(2);
        cll.printList();  // Output: 1 3
    }

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            head.next = head;
            return;
        }
        Node curr = head;
        while (curr.next != head) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.next = head;
    }
}
9. Create and print a Circular Doubly Linked List
java
Copy
Edit
class CircularDoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularDoublyLinkedList cdll = new CircularDoublyLinkedList();
        cdll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);

        cdll.head.next = second; second.prev = cdll.head;
        second.next = third; third.prev = second;
        third.next = cdll.head; cdll.head.prev = third;

        cdll.printList();  // Output: 1 2 3
    }
}
1. Create and print a Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.printList();  // Output: 10 20 30
    }
}
2. Insert node at the beginning in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head != null) {
            head.prev = newNode;
        }
        newNode.next = head;
        head = newNode;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.insertAtBeginning(30);
        dll.insertAtBeginning(20);
        dll.insertAtBeginning(10);
        dll.printList();  // Output: 10 20 30
    }
}
3. Insert node at the end in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.prev = curr;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.insertAtEnd(10);
        dll.insertAtEnd(20);
        dll.insertAtEnd(30);
        dll.printList();  // Output: 10 20 30
    }
}
4. Delete a node from Doubly Linked List by value
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void deleteNode(int key) {
        Node curr = head;
        while (curr != null && curr.data != key) {
            curr = curr.next;
        }
        if (curr == null) return; // not found

        if (curr.prev != null) {
            curr.prev.next = curr.next;
        } else {
            head = curr.next;  // deleting head
        }
        if (curr.next != null) {
            curr.next.prev = curr.prev;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.deleteNode(20);
        dll.printList();  // Output: 10 30
    }
}
5. Reverse a Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void reverse() {
        Node temp = null;
        Node curr = head;

        while (curr != null) {
            temp = curr.prev;
            curr.prev = curr.next;
            curr.next = temp;
            curr = curr.prev;
        }
        if (temp != null) head = temp.prev;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.reverse();
        dll.printList();  // Output: 3 2 1
    }
}
6. Create and print a Circular Singly Linked List
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        cll.head.next = second;
        second.next = third;
        third.next = cll.head; // Circular link
        cll.printList();  // Output: 1 2 3
    }
}
7. Insert node at end in Circular Singly Linked List
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            head.next = head;
            return;
        }
        Node curr = head;
        while (curr.next != head) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.next = head;
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.insertAtEnd(1);
        cll.insertAtEnd(2);
        cll.insertAtEnd(3);
        cll.printList();  // Output: 1 2 3
    }
}
8. Delete a node from Circular Singly Linked List by key
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    void deleteNode(int key) {
        if (head == null) return;
        Node curr = head, prev = null;

        // If head is to be deleted
        if (head.data == key) {
            // Find last node to update its next pointer
            Node last = head;
            while (last.next != head) {
                last = last.next;
            }
            if (head.next == head) { // only one node
                head = null;
            } else {
                last.next = head.next;
                head = head.next;
            }
            return;
        }

        prev = head;
        curr = head.next;
        while (curr != head && curr.data != key) {
            prev = curr;
            curr = curr.next;
        }
        if (curr.data == key) {
            prev.next = curr.next;
        }
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.insertAtEnd(1);
        cll.insertAtEnd(2);
        cll.insertAtEnd(3);
        cll.deleteNode(2);
        cll.printList();  // Output: 1 3
    }

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            head.next = head;
            return;
        }
        Node curr = head;
        while (curr.next != head) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.next = head;
    }
}
9. Create and print a Circular Doubly Linked List
java
Copy
Edit
class CircularDoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularDoublyLinkedList cdll = new CircularDoublyLinkedList();
        cdll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);

        cdll.head.next = second; second.prev = cdll.head;
        second.next = third; third.prev = second;
        third.next = cdll.head; cdll.head.prev = third;

        cdll.printList();  // Output: 1 2 3
    }
}
10. Insert node at the beginning in Circular Doubly Linked List
java
Copy
Edit
class CircularDoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            head.next = head;
            head.prev = head;
            return;
        }
        Node last = head.prev;
        newNode.next = head;
        newNode.prev = last;
        last.next = newNode;
        head.prev = newNode;
        head = newNode;
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularDoublyLinkedList cdll = new CircularDoublyLinkedList();
        cdll.insertAtBeginning(3);
        cdll.insertAtBeginning(2);
        cdll.insertAtBeginning(1);
        cdll.printList();  // Output: 1 2 3
    }
}
11. Delete node by key in Circular Doubly Linked List
java
Copy
Edit
class CircularDoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; prev = null; next = null; }
    }

    Node head;

    void deleteNode(int key) {
        if (head == null) return;
        Node curr = head;
        boolean found = false;

        do {
            if (curr.data == key) {
                found = true;
                break;
            }
            curr = curr.next;
        } while (curr != head);

        if (!found) return;

        if (curr.next == curr) {  // only one node
            head = null;
            return;
        }

        curr.prev.next = curr.next;
        curr.next.prev = curr.prev;

        if (curr == head) {
            head = curr.next;
        }
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularDoublyLinkedList cdll = new CircularDoublyLinkedList();
        cdll.insertAtBeginning(3);
        cdll.insertAtBeginning(2);
        cdll.insertAtBeginning(1);
        cdll.deleteNode(2);
        cdll.printList();  // Output: 1 3
    }

    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            head.next = head;
            head.prev = head;
            return;
        }
        Node last = head.prev;
        newNode.next = head;
        newNode.prev = last;
        last.next = newNode;
        head.prev = newNode;
        head = newNode;
    }
}
12. Find length of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    int length() {
        int count = 0;
        Node curr = head;
        while (curr != null) {
            count++;
            curr = curr.next;
        }
        return count;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        System.out.println(dll.length());  // Output: 3
    }
}
13. Search for an element in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    boolean search(int key) {
        Node curr = head;
        while (curr != null) {
            if (curr.data == key) return true;
            curr = curr.next;
        }
        return false;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        System.out.println(dll.search(2));  // true
        System.out.println(dll.search(3));  // false
    }
}
14. Merge two sorted Doubly Linked Lists
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    static Node mergeSorted(Node first, Node second) {
        if (first == null) return second;
        if (second == null) return first;

        if (first.data < second.data) {
            first.next = mergeSorted(first.next, second);
            if (first.next != null) first.next.prev = first;
            first.prev = null;
            return first;
        } else {
            second.next = mergeSorted(first, second.next);
            if (second.next != null) second.next.prev = second;
            second.prev = null;
            return second;
        }
    }

    void printList(Node node) {
        Node curr = node;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll1 = new DoublyLinkedList();
        dll1.head = new Node(1);
        dll1.head.next = new Node(3);
        dll1.head.next.prev = dll1.head;
        dll1.head.next.next = new Node(5);
        dll1.head.next.next.prev = dll1.head.next;

        DoublyLinkedList dll2 = new DoublyLinkedList();
        dll2.head = new Node(2);
        dll2.head.next = new Node(4);
        dll2.head.next.prev = dll2.head;
        dll2.head.next.next = new Node(6);
        dll2.head.next.next.prev = dll2.head.next;

        DoublyLinkedList result = new DoublyLinkedList();
        result.head = mergeSorted(dll1.head, dll2.head);
        result.printList(result.head);  // Output: 1 2 3 4 5 6
    }
}
15. Convert Doubly Linked List to Circular Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void convertToCircular() {
        if (head == null) return;
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = head;
        head.prev = curr;
    }

    void printCircularList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.convertToCircular();
        dll.printCircularList();  // Output: 1 2 3
    }
}
16. Split Circular Singly Linked List into two halves
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; }
    }

    Node head;

    void splitList(Node head, CircularSinglyLinkedList list1, CircularSinglyLinkedList list2) {
        if (head == null) return;

        Node slow = head, fast = head;

        while (fast.next != head && fast.next.next != head) {
            slow = slow.next;
            fast = fast.next.next;
        }

        if (fast.next.next == head) {
            fast = fast.next;
        }

        list1.head = head;
        list2.head = slow.next;

        fast.next = slow.next;
        slow.next = head;
    }

    void printList(Node head) {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        Node fourth = new Node(4);
        Node fifth = new Node(5);
        cll.head.next = second;
        second.next = third;
        third.next = fourth;
        fourth.next = fifth;
        fifth.next = cll.head;

        CircularSinglyLinkedList list1 = new CircularSinglyLinkedList();
        CircularSinglyLinkedList list2 = new CircularSinglyLinkedList();

        cll.splitList(cll.head, list1, list2);

        list1.printList(list1.head);  // Output: 1 2 3
        list2.printList(list2.head);  // Output: 4 5
    }
}
17. Detect loop in singly linked list (for completeness)
java
Copy
Edit
class LinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; next = null; }
    }

    Node head;

    boolean detectLoop() {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }

    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.head = new Node(1);
        list.head.next = new Node(2);
        list.head.next.next = new Node(3);
        list.head.next.next.next = list.head;  // Loop here

        System.out.println(list.detectLoop());  // Output: true
    }
}
18. Reverse a Circular Singly Linked List
java
Copy
Edit
class CircularSinglyLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int d) { data = d; }
    }

    Node head;

    void reverse() {
        if (head == null || head.next == head) return;

        Node prev = null, curr = head, next;
        Node tail = head;

        do {
            next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        } while (curr != head);

        tail.next = prev;
        head = prev;
    }

    void printList() {
        if (head == null) return;
        Node curr = head;
        do {
            System.out.print(curr.data + " ");
            curr = curr.next;
        } while (curr != head);
        System.out.println();
    }

    public static void main(String[] args) {
        CircularSinglyLinkedList cll = new CircularSinglyLinkedList();
        cll.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        cll.head.next = second;
        second.next = third;
        third.next = cll.head;
        cll.reverse();
        cll.printList();  // Output: 3 2 1
    }
}
19. Insert after a node in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void insertAfter(Node prevNode, int data) {
        if (prevNode == null) return;
        Node newNode = new Node(data);
        newNode.next = prevNode.next;
        prevNode.next = newNode;
        newNode.prev = prevNode;
        if (newNode.next != null) {
            newNode.next.prev = newNode;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        Node second = new Node(2);
        dll.head.next = second;
        second.prev = dll.head;
        dll.insertAfter(dll.head, 3);
        dll.printList();  // Output: 1 3 2
    }
}
20. Delete node at position in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void deleteAtPosition(int pos) {
        if (head == null || pos <= 0) return;

        Node curr = head;
        int count = 1;

        if (pos == 1) {
            head = curr.next;
            if (head != null) head.prev = null;
            return;
        }

        while (curr != null && count < pos) {
            curr = curr.next;
            count++;
        }
        if (curr == null) return;

        if (curr.next != null) {
            curr.next.prev = curr.prev;
        }
        if (curr.prev != null) {
            curr.prev.next = curr.next;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);
        dll.head.next = second; second.prev = dll.head;
        second.next = third; third.prev = second;
        dll.deleteAtPosition(2);
        dll.printList();  // Output: 10 30
    }
}
21. Insert node at the end of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = newNode;
        newNode.prev = curr;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.insertAtEnd(1);
        dll.insertAtEnd(2);
        dll.insertAtEnd(3);
        dll.printList();  // Output: 1 2 3
    }
}
22. Reverse a Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void reverse() {
        Node curr = head;
        Node temp = null;
        while (curr != null) {
            temp = curr.prev;
            curr.prev = curr.next;
            curr.next = temp;
            curr = curr.prev;
        }
        if (temp != null) {
            head = temp.prev;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.reverse();
        dll.printList();  // Output: 3 2 1
    }
}
23. Remove duplicates from sorted Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void removeDuplicates() {
        Node curr = head;
        while (curr != null && curr.next != null) {
            if (curr.data == curr.next.data) {
                Node nextNext = curr.next.next;
                curr.next = nextNext;
                if (nextNext != null) nextNext.prev = curr;
            } else {
                curr = curr.next;
            }
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(2);
        dll.head.next.next.prev = dll.head.next;
        dll.head.next.next.next = new Node(3);
        dll.head.next.next.next.prev = dll.head.next.next;
        dll.removeDuplicates();
        dll.printList();  // Output: 1 2 3
    }
}
24. Insert node before a given node in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void insertBefore(Node nextNode, int data) {
        if (nextNode == null) return;
        Node newNode = new Node(data);
        newNode.next = nextNode;
        newNode.prev = nextNode.prev;

        if (nextNode.prev != null) {
            nextNode.prev.next = newNode;
        } else {
            head = newNode;
        }
        nextNode.prev = newNode;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(2);
        Node third = new Node(3);
        dll.head.next = third;
        third.prev = dll.head;
        dll.insertBefore(third, 1);
        dll.printList();  // Output: 1 2 3
    }
}
25. Find the middle node of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    Node findMiddle() {
        if (head == null) return null;
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        Node mid = dll.findMiddle();
        System.out.println(mid.data);  // Output: 2
    }
}
26. Delete last node of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void deleteLast() {
        if (head == null) return;
        if (head.next == null) {
            head = null;
            return;
        }
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.prev.next = null;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.deleteLast();
        dll.printList();  // Output: 1 2
    }
}
27. Delete first node of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void deleteFirst() {
        if (head == null) return;
        head = head.next;
        if (head != null) head.prev = null;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.deleteFirst();
        dll.printList();  // Output: 2 3
    }
}
28. Check if Doubly Linked List is palindrome
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    boolean isPalindrome() {
        if (head == null) return true;
        Node left = head;
        Node right = head;
        while (right.next != null) {
            right = right.next;
        }
        while (left != right && right.next != left) {
            if (left.data != right.data) return false;
            left = left.next;
            right = right.prev;
        }
        return true;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(1);
        dll.head.next.next.prev = dll.head.next;
        System.out.println(dll.isPalindrome());  // Output: true
    }
}
29. Sort a Doubly Linked List using Bubble Sort
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void bubbleSort() {
        if (head == null) return;
        boolean swapped;
        do {
            swapped = false;
            Node curr = head;
            while (curr.next != null) {
                if (curr.data > curr.next.data) {
                    int temp = curr.data;
                    curr.data = curr.next.data;
                    curr.next.data = temp;
                    swapped = true;
                }
                curr = curr.next;
            }
        } while (swapped);
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(3);
        dll.head.next = new Node(1);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(2);
        dll.head.next.next.prev = dll.head.next;
        dll.bubbleSort();
        dll.printList();  // Output: 1 2 3
    }
}
30. Find pairs with given sum in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void findPairsWithSum(int sum) {
        if (head == null) return;
        Node first = head;
        Node second = head;

        // Move second to the last node
        while (second.next != null) {
            second = second.next;
        }

        boolean found = false;

        while (first != null && second != null && first != second && second.next != first) {
            int currSum = first.data + second.data;
            if (currSum == sum) {
                System.out.println("(" + first.data + ", " + second.data + ")");
                found = true;
                first = first.next;
                second = second.prev;
            } else if (currSum < sum) {
                first = first.next;
            } else {
                second = second.prev;
            }
        }

        if (!found) {
            System.out.println("No pairs found");
        }
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.head.next.next.next = new Node(4);
        dll.head.next.next.next.prev = dll.head.next.next;

        dll.findPairsWithSum(5);  
        // Output:
        // (1, 4)
        // (2, 3)
    }
}
31. Clone a Doubly Linked List with random pointer (deep copy)
java
Copy
Edit
import java.util.HashMap;

class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next, random;
        Node(int d) { data = d; }
    }

    Node head;

    Node cloneList() {
        if (head == null) return null;
        HashMap<Node, Node> map = new HashMap<>();

        Node curr = head;
        while (curr != null) {
            map.put(curr, new Node(curr.data));
            curr = curr.next;
        }

        curr = head;
        while (curr != null) {
            map.get(curr).next = map.get(curr.next);
            map.get(curr).prev = map.get(curr.prev);
            map.get(curr).random = map.get(curr.random);
            curr = curr.next;
        }

        return map.get(head);
    }

    void printList(Node node) {
        while (node != null) {
            int randomData = node.random != null ? node.random.data : -1;
            System.out.println("Data = " + node.data + ", Random = " + randomData);
            node = node.next;
        }
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node first = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);

        first.next = second;
        second.prev = first;
        second.next = third;
        third.prev = second;

        first.random = third;
        second.random = first;
        third.random = second;

        dll.head = first;

        Node clonedHead = dll.cloneList();
        dll.printList(clonedHead);
    }
}
32. Convert Doubly Linked List to Balanced BST
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    int countNodes(Node head) {
        int count = 0;
        Node temp = head;
        while (temp != null) {
            count++;
            temp = temp.next;
        }
        return count;
    }

    Node sortedListToBSTUtil(int n) {
        if (n <= 0) return null;
        Node left = sortedListToBSTUtil(n / 2);

        Node root = head;
        root.prev = left;

        head = head.next;

        root.next = sortedListToBSTUtil(n - n / 2 - 1);

        return root;
    }

    Node sortedListToBST() {
        int n = countNodes(head);
        return sortedListToBSTUtil(n);
    }

    void preOrder(Node node) {
        if (node == null) return;
        System.out.print(node.data + " ");
        preOrder(node.prev);
        preOrder(node.next);
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.head.next.next.next = new Node(4);
        dll.head.next.next.next.prev = dll.head.next.next;

        Node root = dll.sortedListToBST();
        dll.preOrder(root);  // Output: 3 2 1 4
    }
}
33. Check if two Doubly Linked Lists are identical
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    boolean areIdentical(Node head1, Node head2) {
        Node curr1 = head1, curr2 = head2;
        while (curr1 != null && curr2 != null) {
            if (curr1.data != curr2.data) return false;
            curr1 = curr1.next;
            curr2 = curr2.next;
        }
        return curr1 == null && curr2 == null;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head1 = new Node(1);
        head1.next = new Node(2);
        head1.next.prev = head1;

        Node head2 = new Node(1);
        head2.next = new Node(2);
        head2.next.prev = head2;

        System.out.println(dll.areIdentical(head1, head2));  // true
    }
}
34. Find the intersection point of two Doubly Linked Lists
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    int length(Node head) {
        int len = 0;
        Node curr = head;
        while (curr != null) {
            len++;
            curr = curr.next;
        }
        return len;
    }

    Node getIntersectionNode(Node head1, Node head2) {
        int len1 = length(head1);
        int len2 = length(head2);

        int diff = Math.abs(len1 - len2);

        Node longer = len1 > len2 ? head1 : head2;
        Node shorter = len1 > len2 ? head2 : head1;

        for (int i = 0; i < diff; i++) {
            longer = longer.next;
        }

        while (longer != null && shorter != null) {
            if (longer == shorter) return longer;
            longer = longer.next;
            shorter = shorter.next;
        }
        return null;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node common = new Node(7);
        common.next = new Node(8);
        common.next.prev = common;

        Node head1 = new Node(1);
        head1.next = new Node(2);
        head1.next.prev = head1;
        head1.next.next = common;
        common.prev = head1.next;

        Node head2 = new Node(3);
        head2.next = common;
        common.prev = head2;

        Node intersection = dll.getIntersectionNode(head1, head2);
        System.out.println(intersection != null ? intersection.data : "No intersection");  // Output: 7
    }
}
35. Count nodes in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    int countNodes(Node head) {
        int count = 0;
        Node curr = head;
        while (curr != null) {
            count++;
            curr = curr.next;
        }
        return count;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(3);
        head.next.next.prev = head.next;

        System.out.println(dll.countNodes(head));  // Output: 3
    }
}
36. Split Doubly Linked List into two halves
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node[] splitList(Node head) {
        Node slow = head;
        Node fast = head;
        while (fast.next != null && fast.next.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        Node secondHalf = slow.next;
        slow.next = null;
        if (secondHalf != null) secondHalf.prev = null;
        return new Node[]{head, secondHalf};
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(3);
        head.next.next.prev = head.next;
        head.next.next.next = new Node(4);
        head.next.next.next.prev = head.next.next;

        Node[] halves = dll.splitList(head);
        dll.printList(halves[0]);  // Output: 1 2
        dll.printList(halves[1]);  // Output: 3 4
    }
}
37. Merge two sorted Doubly Linked Lists
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node mergeSorted(Node first, Node second) {
        if (first == null) return second;
        if (second == null) return first;

        if (first.data < second.data) {
            first.next = mergeSorted(first.next, second);
            if (first.next != null) first.next.prev = first;
            first.prev = null;
            return first;
        } else {
            second.next = mergeSorted(first, second.next);
            if (second.next != null) second.next.prev = second;
            second.prev = null;
            return second;
        }
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node first = new Node(1);
        first.next = new Node(3);
        first.next.prev = first;

        Node second = new Node(2);
        second.next = new Node(4);
        second.next.prev = second;

        Node merged = dll.mergeSorted(first, second);
        dll.printList(merged);  // Output: 1 2 3 4
    }
}
38. Rotate Doubly Linked List by n nodes
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void rotate(int n) {
        if (head == null || n == 0) return;

        Node curr = head;
        int count = 1;
        while (count < n && curr != null) {
            curr = curr.next;
            count++;
        }
        if (curr == null) return;

        Node nthNode = curr;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = head;
        head.prev = curr;

        head = nthNode.next;
        if (head != null) head.prev = null;

        nthNode.next = null;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;
        dll.head.next.next.next = new Node(4);
        dll.head.next.next.next.prev = dll.head.next.next;

        dll.rotate(2);
        dll.printList();  // Output: 3 4 1 2
    }
}
39. Merge two Doubly Linked Lists by alternating nodes
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node mergeAlternate(Node first, Node second) {
        if (first == null) return second;
        if (second == null) return first;

        Node head = first;
        Node curr1 = first.next;
        Node curr2 = second;
        Node curr = first;
        boolean takeFromSecond = true;

        while (curr1 != null && curr2 != null) {
            if (takeFromSecond) {
                curr.next = curr2;
                curr2.prev = curr;
                curr = curr2;
                curr2 = curr2.next;
            } else {
                curr.next = curr1;
                curr1.prev = curr;
                curr = curr1;
                curr1 = curr1.next;
            }
            takeFromSecond = !takeFromSecond;
        }

        if (curr1 != null) {
            curr.next = curr1;
            curr1.prev = curr;
        } else if (curr2 != null) {
            curr.next = curr2;
            curr2.prev = curr;
        }
        return head;
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node first = new Node(1);
        first.next = new Node(3);
        first.next.prev = first;

        Node second = new Node(2);
        second.next = new Node(4);
        second.next.prev = second;

        Node merged = dll.mergeAlternate(first, second);
        dll.printList(merged);  // Output: 1 2 3 4
    }
}
40. Convert Binary Tree to Doubly Linked List (Inorder)
java
Copy
Edit
class BinaryTreeToDLL {
    static class Node {
        int data;
        Node left, right;
        Node(int d) { data = d; }
    }

    Node prev = null, head = null;

    void bToDLL(Node root) {
        if (root == null) return;
        bToDLL(root.left);

        if (prev == null) {
            head = root;
        } else {
            root.left = prev;
            prev.right = root;
        }
        prev = root;

        bToDLL(root.right);
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.right;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        BinaryTreeToDLL tree = new BinaryTreeToDLL();
        Node root = new Node(10);
        root.left = new Node(5);
        root.right = new Node(20);
        root.left.left = new Node(3);
        root.left.right = new Node(7);

        tree.bToDLL(root);
        tree.printList(tree.head);  // Output: 3 5 7 10 20
    }
}
41. Delete a node at a given position in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void deleteAtPosition(int pos) {
        if (head == null || pos <= 0) return;

        Node curr = head;
        int count = 1;

        if (pos == 1) {
            head = head.next;
            if (head != null) head.prev = null;
            return;
        }

        while (curr != null && count < pos) {
            curr = curr.next;
            count++;
        }

        if (curr == null) return;

        if (curr.next != null) curr.next.prev = curr.prev;
        if (curr.prev != null) curr.prev.next = curr.next;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;

        dll.deleteAtPosition(2);
        dll.printList();  // Output: 1 3
    }
}
42. Insert a node at a given position in Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void insertAtPosition(int data, int pos) {
        Node newNode = new Node(data);
        if (pos <= 0) return;
        if (pos == 1) {
            newNode.next = head;
            if (head != null) head.prev = newNode;
            head = newNode;
            return;
        }

        Node curr = head;
        int count = 1;
        while (curr != null && count < pos - 1) {
            curr = curr.next;
            count++;
        }
        if (curr == null) return;

        newNode.next = curr.next;
        if (curr.next != null) curr.next.prev = newNode;
        curr.next = newNode;
        newNode.prev = curr;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        dll.head = new Node(1);
        dll.head.next = new Node(3);
        dll.head.next.prev = dll.head;

        dll.insertAtPosition(2, 2);
        dll.printList();  // Output: 1 2 3
    }
}
43. Reverse a Doubly Linked List (Iterative)
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void reverse() {
        Node temp = null;
        Node current = head;

        while (current != null) {
            temp = current.prev;
            current.prev = current.next;
            current.next = temp;
            current = current.prev;
        }

        if (temp != null) {
            head = temp.prev;
        }
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;

        dll.reverse();
        dll.printList();  // Output: 3 2 1
    }
}
44. Find pairs with given sum in Doubly Linked List
java
Copy
Edit
import java.util.*;

class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    void findPairs(Node head, int sum) {
        Node first = head;
        Node second = head;

        while (second.next != null) {
            second = second.next;
        }

        boolean found = false;

        while (first != null && second != null && first != second && second.next != first) {
            int currSum = first.data + second.data;
            if (currSum == sum) {
                System.out.println("(" + first.data + ", " + second.data + ")");
                found = true;
                first = first.next;
                second = second.prev;
            } else if (currSum < sum) {
                first = first.next;
            } else {
                second = second.prev;
            }
        }

        if (!found) {
            System.out.println("No pairs found");
        }
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(4);
        head.next.next.prev = head.next;
        head.next.next.next = new Node(5);
        head.next.next.next.prev = head.next.next;
        head.next.next.next.next = new Node(6);
        head.next.next.next.next.prev = head.next.next.next;

        dll.findPairs(head, 6);  
        // Output: (1, 5) (2, 4)
    }
}
45. Remove duplicates from a sorted Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node removeDuplicates(Node head) {
        if (head == null) return null;

        Node curr = head;

        while (curr.next != null) {
            if (curr.data == curr.next.data) {
                curr.next = curr.next.next;
                if (curr.next != null) curr.next.prev = curr;
            } else {
                curr = curr.next;
            }
        }
        return head;
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(2);
        head.next.next.prev = head.next;
        head.next.next.next = new Node(3);
        head.next.next.next.prev = head.next.next;

        head = dll.removeDuplicates(head);
        dll.printList(head);  // Output: 1 2 3
    }
}
46. Find the middle node of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node findMiddle(Node head) {
        if (head == null) return null;

        Node slow = head;
        Node fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(3);
        head.next.next.prev = head.next;
        head.next.next.next = new Node(4);
        head.next.next.next.prev = head.next.next;

        Node middle = dll.findMiddle(head);
        System.out.println(middle != null ? middle.data : "List is empty");  // Output: 3
    }
}
47. Check if Doubly Linked List is palindrome
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    boolean isPalindrome(Node head) {
        if (head == null) return true;

        Node tail = head;
        while (tail.next != null) {
            tail = tail.next;
        }

        while (head != tail && head.prev != tail) {
            if (head.data != tail.data) return false;
            head = head.next;
            tail = tail.prev;
        }
        return true;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(1);
        head.next.next.prev = head.next;

        System.out.println(dll.isPalindrome(head));  // Output: true
    }
}
48. Convert Sorted Doubly Linked List to Balanced BST
java
Copy
Edit
class DLLToBST {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    int countNodes(Node head) {
        int count = 0;
        Node temp = head;
        while (temp != null) {
            count++;
            temp = temp.next;
        }
        return count;
    }

    Node sortedListToBSTHelper(int n) {
        if (n <= 0) return null;

        Node left = sortedListToBSTHelper(n / 2);

        Node root = head;
        root.prev = left;

        head = head.next;

        root.next = sortedListToBSTHelper(n - n / 2 - 1);

        return root;
    }

    Node sortedListToBST(Node head) {
        this.head = head;
        int n = countNodes(head);
        return sortedListToBSTHelper(n);
    }

    void inorder(Node root) {
        if (root == null) return;
        inorder(root.prev);
        System.out.print(root.data + " ");
        inorder(root.next);
    }

    public static void main(String[] args) {
        DLLToBST obj = new DLLToBST();

        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(3);
        head.next.next.prev = head.next;
        head.next.next.next = new Node(4);
        head.next.next.next.prev = head.next.next;
        head.next.next.next.next = new Node(5);
        head.next.next.next.next.prev = head.next.next.next;

        Node root = obj.sortedListToBST(head);
        obj.inorder(root);  // Output: 1 2 3 4 5
    }
}
49. Clone Doubly Linked List with random pointers
java
Copy
Edit
import java.util.*;

class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next, random;
        Node(int d) { data = d; }
    }

    Node cloneList(Node head) {
        if (head == null) return null;

        Node curr = head;

        // Step 1: Create new nodes after each original node
        while (curr != null) {
            Node newNode = new Node(curr.data);
            newNode.next = curr.next;
            curr.next = newNode;
            newNode.prev = curr;
            curr = newNode.next;
        }

        // Step 2: Copy random pointers
        curr = head;
        while (curr != null) {
            if (curr.random != null) {
                curr.next.random = curr.random.next;
            }
            curr = curr.next.next;
        }

        // Step 3: Separate the lists
        curr = head;
        Node newHead = head.next;
        while (curr != null) {
            Node newNode = curr.next;
            curr.next = newNode.next;
            if (newNode.next != null) {
                newNode.next = newNode.next.next;
                if (newNode.next != null) newNode.next.prev = newNode;
            }
            curr = curr.next;
        }
        if (newHead != null) newHead.prev = null;
        return newHead;
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            int randomData = (curr.random != null) ? curr.random.data : -1;
            System.out.print("[" + curr.data + ", random=" + randomData + "] ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(3);
        head.next.next.prev = head.next;

        head.random = head.next.next;        // 1's random points to 3
        head.next.random = head;             // 2's random points to 1
        head.next.next.random = head.next;  // 3's random points to 2

        Node cloned = dll.cloneList(head);

        dll.printList(head);
        dll.printList(cloned);
    }
}
50. Sort a Doubly Linked List using Merge Sort
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node split(Node head) {
        Node fast = head, slow = head;
        while (fast.next != null && fast.next.next != null) {
            fast = fast.next.next;
            slow = slow.next;
        }
        Node second = slow.next;
        slow.next = null;
        if (second != null) second.prev = null;
        return second;
    }

    Node merge(Node first, Node second) {
        if (first == null) return second;
        if (second == null) return first;

        if (first.data < second.data) {
            first.next = merge(first.next, second);
            if (first.next != null) first.next.prev = first;
            first.prev = null;
            return first;
        } else {
            second.next = merge(first, second.next);
            if (second.next != null) second.next.prev = second;
            second.prev = null;
            return second;
        }
    }

    Node mergeSort(Node head) {
        if (head == null || head.next == null) return head;

        Node second = split(head);

        head = mergeSort(head);
        second = mergeSort(second);

        return merge(head, second);
    }

    void printList(Node head) {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head = new Node(4);
        head.next = new Node(3);
        head.next.prev = head;
        head.next.next = new Node(1);
        head.next.next.prev = head.next;
        head.next.next.next = new Node(2);
        head.next.next.next.prev = head.next.next;

        head = dll.mergeSort(head);
        dll.printList(head);  // Output: 1 2 3 4
    }
}
51. Find the length of Doubly Linked List
java
Copy
Edit
class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    int length(Node head) {
        int count = 0;
        Node curr = head;
        while (curr != null) {
            count++;
            curr = curr.next;
        }
        return count;
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        Node head = new Node(1);
        head.next = new Node(2);
        head.next.prev = head;
        head.next.next = new Node(3);
        head.next.next.prev = head.next;

        System.out.println(dll.length(head));  // Output: 3
    }
}
52. Swap nodes in Doubly Linked List without swapping data

class DoublyLinkedList {
    static class Node {
        int data;
        Node prev, next;
        Node(int d) { data = d; }
    }

    Node head;

    void swapNodes(Node node1, Node node2) {
        if (node1 == node2) return;

        Node prev1 = node1.prev;
        Node next1 = node1.next;
        Node prev2 = node2.prev;
        Node next2 = node2.next;

        if (prev1 != null) prev1.next = node2;
        if (next1 != null) next1.prev = node2;
        if (prev2 != null) prev2.next = node1;
        if (next2 != null) next2.prev = node1;

        node1.prev = prev2;
        node1.next = next2;
        node2.prev = prev1;
        node2.next = next1;

        if (head == node1) head = node2;
        else if (head == node2) head = node1;
    }

    void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;

        dll.swapNodes(dll.head, dll.head.next.next);
        dll.printList();  // Output: 3 2 1
    }
}
