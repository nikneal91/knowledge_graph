- 1. Implement stack using array
- 2. Immediate Smaller Element
- 3. Preorder Traversal
- 4. Stack designer
- 5. Operations on Stack
- 6. Pairwise Consecutive Elements
- 7. Reverse Array Using Stack
-
- ##  Implement stack using array
- ```
  class MyStack {
    private int[] arr;
    private int top;
    
  - public MyStack() {
        arr = new int[1000];
        top = -1;
    }
  - 
    public void push(int x) {
        if ( top ==1000) 
          System.out.println("Stack Overflow");
        else 
           arr[++top]=x;
    }
  - 
    public int pop() {
        if (top==-1)
          return -1; // underflow
        else
           return arr[top--];
    }
  }
  ```
- ## Immediate Smaller Element
- ```
  public void immediateSmaller(int arr[]) {
        Stack<Integer> st = new Stack<>();
        int upd=-1;
        for (int i=arr.length-1 ;i>=0;i--) {
            if ( st.isEmpty() || st.peek() >= arr[i]) 
               upd=-1;
            else  
               upd=st.peek();
            
            st.push(arr[i]);
            arr[i]=upd;
        }
        
    }
  ```
- ## PreOrder Traversal
- ```
  static ArrayList<Integer> preorder(Node root) {
        ArrayList<Integer> result = new ArrayList<>();
        Stack<Node> st = new Stack<>();
        st.push(root);
        
        while ( !st.isEmpty()) {
            Node curr = st.pop();
            result.add(curr.data);
            if ( curr.right!=null)
                st.push(curr.right);
            if ( curr.left !=null) 
                st.push(curr.left);
        }
        return result;
    }
  ```
- ## Stack Designer
- ```
  public static Stack<Integer>_push(ArrayList<Integer> arr,int n)
  {
    Stack<Integer> res = new Stack<Integer>();
    for (int i=0 ; i < n ; i++) {
        res.push(arr.get(i));
    }
    return res;
    
  }
  - public static void _pop(Stack<Integer>s)
  {
    while ( !s.isEmpty()) {
        System.out.print(s.pop()+ " ");
    }
  }
  ```
- ## Operations on Stack
- ```
  class Geeks {
    // Function to push an element into the stack.
    public static void insert(Stack<Integer> st, int x) {
        // Your code here
        st.push(x);
    }
  - // Function to remove top element from stack.
    public static void remove(Stack<Integer> st) {
        if ( !st.isEmpty()) st.pop();
        // Your code here
    }
  - // Function to print the top element of stack.
        
    public static void headOf_Stack(Stack<Integer> st) {
        if ( !st.isEmpty()) 
        System.out.println(st.peek());
        else 
        System.out.println("Stack is Empty");
    }
  - // Function to search an element in the stack.
    public static boolean find(Stack<Integer> st, int val) {
        boolean exists = false;
        Stack<Integer> s2 = new Stack<Integer>();
        while ( !st.isEmpty()) {
            int ele = st.pop();
            s2.push(ele);
            if (ele == val) {
                exists=true;
                break;
            }
        }
        
        while ( !s2.isEmpty()) st.push(s2.pop());
        
        return exists;
    }
  }
  ```
- ## Pairwise consecutive element
- ```
  public static boolean pairWiseConsecutive(Stack<Integer> st) {
        if ( st.size()%2 !=0) 
            st.pop();
        while ( !st.isEmpty()) {
          int first = st.pop();
          int sec = st.pop();
          if ( first-sec != 1) 
             return false;
        }
        return true;   
    }
  ```
- ## Reverse array using Stack
- ```
  void reverseArray(int[] arr) {
        int n = arr.size();
        Stack<Integer> st = new Stack<>();
        for(int i = 0 ; i< n ; i++)
            st.push(arr[i]);
        while(!st.isEmpty()){
            for(int i = 0 ; i<n ; i++){
                arr[i] = st.pop();
            }
        }
  }
  ```