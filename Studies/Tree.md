```java  
  
import java.util.*;  
import java.util.*;  
class BinaryTree{  
    Node  root;  
    BinaryTree(){}  
    class Node{  
        int value;  
        Node right;  
        Node left;  
        Node(int value){  
            this.value = value;  
        }  
    }  
    void populate(Scanner scanner){  
        System.out.println("Enter root");  
        int value =  scanner.nextInt();  
		        root = new Node(value) ;  
        populate(scanner,root);  
    }  
    void populate(Scanner scanner,Node root){  
        System.out.println("Insert Left T or F"+ root.value);  
        boolean left = scanner.nextBoolean();  
        if(left){  
            System.out.print("Insert left value " + root.value +": ");  
            int value = scanner.nextInt();  
            root.left = new Node(value);  
            populate(scanner,root.left);  
        }  
        System.out.println("Insert Right T or F " + root.value);  
        boolean right = scanner.nextBoolean();  
        if(right){  
            System.out.println("Insert right value " + root.value +": ");  
            int value = scanner.nextInt();  
            root.right = new Node(value);  
            populate(scanner,root.right);  
        }  
    }  
    void display(){  
        display(root,"");  
    }  
    void display(Node node,String indent){  
        if(node == null)return;  
        System.out.println(indent + node.value);  
        display(node.left,indent +"\t");  
        display(node.right,indent +"\t");  
    }  
    public void tdisplay(){  
        tdisplay(root, 0);  
    }  
    public void tdisplay(Node root,int level){  
        if(root == null)return;  
        tdisplay(root.right,level + 1);  
        if(level != 0){  
            for(int i=0;i< level - 1;i++){  
                System.out.print("|\t\t");  
            }  
            System.out.println("|------->" + root.value);  
        }else{  
            System.out.println(root.value);  
        }  
        tdisplay(root.left,level + 1);  
    }  
    public static void main(String args[]) {  
        Scanner in = new Scanner(System.in);  
        BinaryTree bt = new BinaryTree();  
        bt.populate(in);  
        bt.tdisplay();  
    }  
  
}
```

```java
public class BST{
    Node root;
    class Node{
        int value;
        Node right;
        Node left;
        int height;
        Node(int value){
            this.value = value;
        }
    }
    BST(){}
    boolean isEmpty(){
        return root == null;
    }
    void insert(int value){
        insert(value,root);
    }
    void populate(int[] nums){
        for(int i=0;i<nums.length;i++){
            insert(nums[i]);
        }
    }
    Node insert(int value,Node node){
        if(node == null){
             node = new Node(value);
             return node;
        }
        if(value<node.value){
            node.left = insert(value,node.left);
        }
        if(value>node.value){
            node.right = insert(value,node.right);
        }
        // node.height = Math.max(node.height(node.left),node.height(node.right)) + 1;
        return node;
    }
    // boolean balanced(){
    //     return balanced(root);
    // }
    // boolean balanced(Node node){
    //     if(node == null)return true;
    //     return Math.abs(node.height(node.left) - node.height(node.right))<=1 && balanced(node.right) && balanced(node.left);
    // }
    void display(){
        display(root,0);
    }
    void display(Node node,int level){
        if(node == null)return;
        display(node.right,level + 1);
        if(level != 0){
            for(int i=0;i<level - 1;i++){
                System.out.print("|\t\t");
            }
            System.out.println("|------->" + node.value);
        }else{
            System.out.println(node.value);
        }
        display(node.left,level + 1);
    }
    public static void main(String args[]){
        int[] nums = {4,2,6,2,1,23,463,325,22};
        BST bst = new BST();
        bst.populate(nums);
        bst.display();
        
    }
}
```


**AVL tree**

```java
public class BST {
    Node root;

    class Node {
        int value;
        Node right;
        Node left;
        int height;

        Node(int value) {
            this.value = value;
            this.height = 1; // Initialize height of new node to 1
        }
    }

    BST() {}

    boolean isEmpty() {
        return root == null;
    }

    void insert(int value) {
        root = insert(value, root);
    }

    void populate(int[] nums) {
        for (int num : nums) {
            insert(num);
        }
    }

    Node insert(int value, Node node) {
        if (node == null) {
            return new Node(value);
        }

        if (value < node.value) {
            node.left = insert(value, node.left);
        } else if (value > node.value) {
            node.right = insert(value, node.right);
        }

        // Update height of the current node
        node.height = 1 + Math.max(height(node.left), height(node.right));

        return rotate(node);
    }

    int height(Node node) {
        if (node == null) {
            return 0;
        }
        return node.height;
    }
    Node rotate(Node node){
        if(height(node.left) - height(node.right) > 1){
            if(height(node.left.left) - height(node.right.left)>0){
                return rightRotate(node);
            }
            if(height(node.left.left) - height(node.right.left)<0){
                node.left = leftRotate(node);
                return rightRotate(node);
            }
        }
        if(height(node.left) - height(node.right) < -1){
            if(height(node.right.left) - height(node.right.right)<0){
                return leftRotate(node);
            }
            if(height(node.right.left) - height(node.right.right)>0){
                node.right = rightRotate(node.right);
                return leftRotate(node);
            }
        }
        return node;
    }
    Node rightRotate(Node p){
        Node c = p.left;
        Node t= c.right;
        c.left = p;
        p.left = t;
        p.height = Math.max(height(p.left),height(p.right) + 1);
        c.height = Math.max(height(c.left),height(c.right) + 1);
        return c;
    }
    Node leftRotate(Node c){
        Node p = c.right;
        Node t= p.left;
        p.left = c;
        c.right = t;
        p.height = Math.max(height(p.left),height(p.right) + 1);
        c.height = Math.max(height(c.left),height(c.right) + 1);
        return p;
    }
    boolean balanced() {
        return balanced(root);
    }

    boolean balanced(Node node) {
        if (node == null) return true;

        int leftHeight = height(node.left);
        int rightHeight = height(node.right);

        return Math.abs(leftHeight - rightHeight) <= 1
            && balanced(node.left)
            && balanced(node.right);
    }

    void display() {
        display(root, 0);
    }

    void display(Node node, int level) {
        if (node == null) return;

        display(node.right, level + 1);
        if (level != 0) {
            for (int i = 0; i < level - 1; i++) {
                System.out.print("|\t\t");
            }
            System.out.println("|------->" + node.value);
        } else {
            System.out.println(node.value);
        }
        display(node.left, level + 1);
    }

    public static void main(String[] args) {
        int[] nums = {4, 2, 6, 2, 1, 23, 463, 325, 22};
        BST bst = new BST();
        bst.populate(nums);
        bst.display();
        
        // Check if the BST is balanced
        System.out.println("Is the BST balanced? " + bst.balanced());
    }
}

```

```java
class SGT{
    Node root;
    class Node{
        int data;
        int sinterval;
        int einterval;
        Node left;
        Node right;
        Node(int sinterval,int einterval){
            this.sinterval = sinterval;
            this.einterval = einterval;
        }
    }
    SGT(int[] nums){
        this.root = constructTree(nums,0,nums.length - 1);
    }
    Node constructTree(int[] nums,int start,int end){
        if(start == end){
            Node leaf = new Node(start,end);
            leaf.data = nums[start];
            return leaf;
        }
        Node node = new Node(start,end);
        int mid = (start + end)/2;
        node.left = this.constructTree(nums,start,mid);
        node.right = this.constructTree(nums,mid + 1,end);
        node.data = node.left.data + node.right.data;
        return node;
    }
    void display(){
        display(this.root);
    }
    void display(Node node){
        String str = "";
        if(node.left != null){
            str = str + "Interval [" + node.left.sinterval + "+" +node.left.einterval + "] and data :" + node.left.data + " + => ";
        }else{
            str = str + "No left child";

        }
        str = str + "Interval [" + node.sinterval + "+" +node.einterval + "] and data :" + node.data + " + <= ";
        if(node.right != null){
            str = str + "Interval [" + node.right.sinterval + "+" +node.right.einterval + "] and data :" + node.right.data + " + => ";
        }else{
            str = str + "No right child";
        }
        System.out.println(str);
        if(node.left != null){
            display(node.left);
        }
        if(node.right != null){
            display(node.right);
        }
    }
        int query(int qsi,int qei){
            return this.query(this.root,qsi,qei);
        }
        int query(Node node,int qsi,int qei){
            if(node.sinterval >= qsi && node.einterval <=  qei){
                return node.data;
            }else if(node.sinterval > qei || node.einterval  <qsi){
                return 0;
            }else{
                return this.query(node.left,qsi,qei) + this.query(node.right,qsi,qei);
            }
        }
        void update(int index,int value){
        this.update(this.root,index,value);
        }
        int update(Node node,int index,int value){
            if(index >= node.sinterval && index <= node.einterval){
                if(index == node.sinterval && index == node.einterval){
                    node.data = value;
                    return node.data;
                }else{
                    int leftans = update(node.left,index,value);
                    int rightans = update(node.right,index,value);
                    node.data = leftans + rightans;
                    return node.data;
                }
            }
            return node.data;
        }
    public static void main(String[] args){
        int[] arr = {2,3,1,3,5,6,-2,-3,6};
        SGT sgt = new SGT(arr);
        sgt.display();
    }
}
```