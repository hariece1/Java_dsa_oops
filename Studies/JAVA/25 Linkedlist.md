Single linked list
https://www.programiz.com/online-compiler/2c2pQ7TUpgw5C
```c
class LL {
    Node head;
    Node tail;
    int size;
    LL(){
        this.size = 0;
    }
    void insertfirst(int value){
        Node node = new Node(value);
        node.next = head;
        head = node;
        
        if(tail == null){
            tail = head;
        }
        size += 1;
    }
    void insertlast(int value){
        if(tail == null) {
            insertfirst(value);
            return;
            }
        Node node = new Node(value);
        tail.next= node;
        tail = node;
        size++;
    }
    void insertatindex(int index, int value){
        if(index == 0){
            insertfirst(value);
            return;
        }
        if(index == size){
            insertlast(value);
            return;
        }
        Node temp = head;
        for(int i=1;i<index;i++){
            temp = temp.next;
        }
         Node node = new Node(value,temp.next);
         temp.next = node;
         size++;
    }
    void deletefirst(){
        head = head.next;
        size--;
        if(head == null){
            tail = null;
        }
    }
    void deletelast(){
        if(size <= 1){
            deletefirst();
            return;
        }
        Node node = get(size - 2);
        tail = node;
        tail.next = null;
        size--;
    }
    void deleteindex(int index){
        if(size <= 1){
            deletefirst();
            return;
        }
        if(index == size - 1){
            deletelast();
            return;
        }
        Node prev = get(index);
        prev.next = prev.next.next;
        size--;
    }
    Node get(int index){
        Node temp = head;
        for(int i = 1;i<index;i++){
            temp = temp.next;
        }
        return temp;
    }
    void display(){
        Node temp = head;
        while(temp != null){
            System.out.print(temp.value + " -> ");
            temp = temp.next;
        }
        System.out.println("END");
    }
    int find(int value){
        Node temp = head;
        int c = 0;
        while(temp != null){
             if(temp.value == value){
                 return c;
             }
             c++;
             temp = temp.next;
        }
        // System.out.println(c);
        //return null;
        return -1;
    }
    
    class Node{
        int value;
        Node next;
        Node(int value){
            this.value = value;
        }
        Node(int value,Node next){
            this.value = value;
            this.next = next;
        }
    }
    public static void main(String[] args) {
        LL list = new LL();
        list.insertfirst(5);
        list.insertfirst(4);
        list.insertfirst(3);
        list.insertfirst(7);
        list.insertlast(9);
        list.display();
        System.out.println("HEAD -> " + list.head.value);
        System.out.println("TAIL -> " + list.tail.value);
        System.out.println("Size -> " + list.size);
        list.insertatindex(4,6);
        list.display();
        System.out.println("HEAD NXT -> " + list.head.next.value);
        System.out.println("TAIL -> " + list.tail.value);
        System.out.println("Size -> " + list.size);
        list.deletefirst();
        list.display();
        System.out.println("HEAD -> " + list.head.value);
        System.out.println("TAIL -> " + list.tail.value);
        System.out.println("Size -> " + list.size);
        list.deleteindex(2);
        list.display();
        System.out.println("HEAD -> " + list.head.value);
        System.out.println("TAIL -> " + list.tail.value);
        System.out.println("Size -> " + list.size);
        System.out.println("Find -> " + list.find(4));
    }
}
```


Double linked list
https://www.programiz.com/online-compiler/4kNyZM7CtAh3R

```java
class DLL {
    Node head;
    Node last = null;//For reverse display used
    
    void insertfirst(int val){
    Node node = new Node(val);
    node.next = head;
    node.prev = null;
    if(head != null){
        head.prev = node;
    }
    head = node;
    }
    void insertlast(int val){
        Node node = new Node(val);
        node.next = null;
        if(head == null){
            node.prev = null;
            head = node;
            return;
        }
        Node elast = head;
        while(elast.next != null){
            elast = elast.next;
        }
        elast.next = node;
        node.prev = elast;
        node.next = null;
    }
    void insertindex(int index,int value){
        Node sindex = get(index);
        Node node = new Node(value);
        Node temp = sindex.next;
        node.prev = sindex;
        sindex.next = node;
        node.next = temp;
        temp.prev = node;
    }
    Node get(int index){
        Node temp = head;
        for(int i = 1;i<index;i++){
            temp = temp.next;
        }
        return temp;
    }
    void display(){
        Node node = head;
        while(node != null){
            System.out.print(node.val + " <-> ");
            last = node;
            node = node.next;
        }
        System.out.println("END");
    }
    void rdisplay(){
        Node node = last;
        while(node != null){
            System.out.print(node.val + " <-> ");
            node = node.prev;
        }
        System.out.println("END");
    }
    
    class Node{
        int val;
        Node next;
        Node prev;
        
        Node(int val){
            this.val=val;
        }
        Node(int val,Node next,Node prev){
            this.val = val;
            this.next = next;
            this.prev = prev;
        }
    }
    
    public static void main(String[] args) {
        DLL ddl = new DLL();
        ddl.insertfirst(3);
        ddl.insertfirst(5);
        ddl.insertfirst(6);
        ddl.insertfirst(7);
        ddl.display();
        ddl.rdisplay();
        ddl.insertlast(4);
        ddl.display();
        ddl.insertindex(2,9);
        ddl.display();
    }
}
```


Circular Linked list
https://www.programiz.com/online-compiler/5pgeTlffEY9qz

```java

class CircularLList{
    Node head;
    Node tail;
    
    CircularLList(){
        this.head = null;
        this.tail = null;
    }
    void insert(int val){
        Node node = new Node(val);
        if(head == null){
            head = node;
            tail = node;
            return;
        }
        tail.next = node;
        node.next = head;
        tail = node;
    }
    void delete(int value){
        Node node = head;
        if(node == null) return;
        if(node.val == value){
            head = node.next;
            tail.next = head;
            return;
        }
        do{
            Node n = node.next;
            if(n.val == value){
                node.next = n.next;
                break;
            }
            node = node.next;
        }while(node != head);
    }
    
    Node get(int index){
        Node temp = head;
        for(int i=1;i<index;i++){
            temp = temp.next;
        }
        return temp;
    }
    void display(){
        Node temp = head;
        if(head != null){
            do{
                System.out.print(temp.val + " -> ");
                temp = temp.next;
            }while(temp != head);
            System.out.println(temp.val);
        }
    }
    
    class Node{
        int val;
        Node next;
        
        Node(int val){
            this.val = val;
        }
        Node(int val,Node next){
            this.val = val;
            this.next = next;
        }
    }
    public static void main(String[] args) {
        CircularLList cll = new CircularLList();
        cll.insert(3);
        cll.insert(9);
        cll.insert(5);
        cll.insert(6);
        cll.insert(2);
        cll.display();
        cll.delete(6);
        cll.display();
    }
}
```

LL using recursion
```java
void insertrec(int value,int index){
        head = insertRec(value,index,head);
    }
    Node insertRec(int value,int index,Node node){
        if(index == 0){
            Node temp = new Node(value,node);
            size++;
            return temp;
        }
        node.next = insertRec(value,--index,node.next);
        return node;
    }
```

Reverse using recursion
```java
void reverse(Node node){
        if(node.next == null){
            head= tail;
            return;
        }
        reverse(node.next);
        tail.next = node;
        tail = node;
        tail.next = null;
    }
```