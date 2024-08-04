```java
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